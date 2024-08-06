---
title: 'Learning Rust'
date: 2024-07-23T13:08:18-07:00
draft: false
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'Learning Rust'
images: 
- "/posts/.../....png"
tags: []
categories: []
resources:
- name: "foo"
  src: "foo.png"
math:
  enable: true
---

#### &#127793; draft &#127793;
One of my 2024 batch goals at [Recurse](https://recurse.com) is to learn Rust. 

## The plan
- work through three introductory Rust resources
  - [The Rust Book](https://doc.rust-lang.org/book/)
  - [Rustlings](https://rustlings.cool/)
  - [Yet Another Rust Resource](https://yarr.fyi/)
- implement a small project in Rust

## Progress
- [msyvr/rusty](https://github.com/msyvr/rusty)
- [msyvr/rustlings](https://github.com/msyvr/rustlings)
- [msyvr/yarry](https://github.com/msyvr/yarry)

---

## Notes: Working through YARR
### Control flow
if-else
- no ternary (`?`) operator: as in Go, `if`-`else` is idiomatic
- syntax: parentheses around the condition are optional and usually considered un-idiomatic
- return the value of the last expression in each branch
  - corollary: if used thus, all branch return types must be the same

loop expressions: `loop`, `while`, `for`
- loop body must result in ()
- emit values via `break`
- assign a loop-generated value using `loop`
  - `while` and `for` aren't guaranteed to hit the `break` statement

_compiler won't like:_
```rust
let x = for count in 0..3 {
    if count > 1 {
        break count * 2;
    }
};
```
_compiler fine with:_
```rust
let mut count = 0;

let x = loop {
    if count > 1 {
        break count * 2;
    }

    count += 1;
};
```

### Functions

```rust
fn name-of-function(args) -> <return-type> {...}
```
- omitting the return type is equivalent to `-> ()` and the function returns the `unit` type
  - similar to returning `void` in C
- final expression in the function body becomes the returned value; the expression ends without any punctuation, normally `;` or `,`
  - if no such expression evaluated, `()` returned

Fibonacci example:
```rust
fn main() {
  let n = 10;
  let x = fibonacci(n);
  println!("Fibonacci({n}) = {x}");
}

fn fibonacci(n: u32) -> u32 {
  if n < 2 {
    return n
  }

  fibonacci(n-1) + fibonacci(n-2)
}
```

### Memory management

- no runtime garbage collector
- no default reference counting
  - can explicitly request it to, though
- you control allocation and deallocation
  - modulo safety rules: can't deallocate and then reuse

Stack and Heap

_stack: push on, pop off (first in, last out)_
- but! also referenced from the middle of the stack

_heap: open field of memory (not a traditional heap data structure)_

Stack: Controlled by program's execution:
- call frames (pushed on for function calls) + the local variables of those functions

Once the function ends, its call frame is popped off the stack and its local variables can no longer be referenced.

Heap: Like an open field; essentially unbounded. Variables 
can live as long as they're not deallocated.
Memory that's allocated on the heap MUST be deliberately 
deallocated later.
- A bit less efficient than memory allocated on the stack: the TL;DR is that variables on the stack are likely in the CPU cache when related code is executed; not true for heap memory, where a slow fetch is required since the CPU's ability to predict what you'll need in that scenario is limited.

In relation to memory management of other languages, Rust sits between `C` and `Go` or `Python`.
- C: `malloc`, `free`, `realloc`
  - can get buffer overflows and use-after-free issues
- Go: automated (tracing) garbage collection
- Python: automated reference counting

Rust: the power without the pain :) via "ownership" tracking and "lifetimes" plus automatic deallocation.

References
- reference to variable `x`: `&x`
- to access the underlying value, dereference `x`: `*x`
  - Rust will automatically dereference references so, usually, can omit `*`

Here, the output for each call to `println!` will be the same:
```rust
let x = 10;
let ref_x: &u32 = &x;
println!("x = {}", *ref_x);
println!("x = {}", ref_x);
```

Pointers
- underlying representation same as reference
- but! a pointer is just a memory address and doesn't reference another variable
  - as a result, Rust doesn't make guarantees about what a pointer can do, so **unsafe Rust** is required to use pointers
- not used for general purposes in Rust but can use unsafe Rust if needed for specific task

### Heap allocation

Examples where needed:
- size unknown at compile time
- define independently of scope

Allocation methods: boxed values, vecs, other collection types

Boxed values
- generic: `Box<u32>` is a `u32` that's heap-allocated
- constructor: `Box::new`
- compiler can often infer type, else use type annotations:
```rust
let x: Box<u32> = Box::new<42>;
let y = Box::<f64>::new(4.2);
```
- to move a value back onto the stack, out of the box, dereference it:
```rust
let x: Box<u32> = Box::new(42);
let y = *x // y is on the stack
```

Vecs
- list, dynamically sized
  - Rust's _arrays_ are of fixed size
- iterables
```rust
let parrots = vec!["Shivers", "Tweety", "Dinner"];
for parrot in parrots.iter() {
    println!("{} says hi.", parrot);
}
```

Other collection types
- see [std::collections docs](https://doc.rust-lang.org/stable/std/collections/index.html) for all available types and when to use each
  - sample: Vec, HashMap, BTreeMap, HashSet, BTreeSet

### Ownership and lifetimes

Ownership and the borrow checker distinguish the Rust language from other languages, generally.

Recall that Rust has no garbage collector. The compiler tracks when memory should be allocated and deallocated to ensure that *references remain valid*. It does so by tracking variables' lifetimes and ownership.

- a value has a unique owner at any given time
  - ownership tracks when memory is valid and when it is dropped
- lifetime is the time during which references to the variable are valid

Gedanken experiments:
- What happens if variable `x` is defined in an outer scope, then initialized in an inner scope where a reference to `x` is assigned to a new variable `y`?
  - Spoiler: The compiler will not be happy. Why? 
- What happens if a function where a variable `x` is defined and initialized attempts to return a reference to `x`: `&x`.
  - Spoiler: The compiler will not be happy. Why?

In the above scenarios, the borrow checker comes into play. In C, the examples would compile, then lead to use-after-free errors. So, let's talk about a concept integral to the borrow checker: lifetimes.

### Lifetimes

- every reference is a borrow
- each borrow has a lifetime: variable creation to destruction
- lifetimes can be named; generally as `'a` but descriptive names okay, too

```rust
fn example<'a>(x: &'a u32) {
  let y: &'a u32 = &x;
}
```

- `<'a>` is for generics
- here, the parameter `x` is a reference of the lifetime `<'a>`
- the lifetime only becomes known according to the parameter of the generic function
  - `'static` means the lifetime is the duration of the program, often used for string constants:
  ```rust
  let msg: &'static str = "hello, world";
  ```
- a lifetime can be explicitly provided anywhere a type annotation is provided for a reference
  - usual for structs, enums, and other data structures containing references
  - generally, not usual for other functions because of lifetime ellision
- lifetime elision: whenever it's permissible to let the compiler make a rules-based guess at the lifetime
  - eg, the above would idiomatically be:
  ```rust
  fn example(x: &u32) {
    let y: &u32 = &x;
  }
  ```
- getting started with lifetimes:
  - omit by default
  - compiler will complain if needed, then try adding them

### Ownership

A variable gets a new owner when it's passed by value, unless the variable type implements the Copy trait. For example, a `Vec<i32>` used as the iterable of a `for` loop cannot be used after the for loop.

Checking whether a type `is_copy`:
```rust
is_copy::<u32>();
``` 

[Generally](https://stackoverflow.com/questions/41413336/do-all-primitive-types-implement-the-copy-trait), primitive types "are Copy", and both tuples and arrays whose elements "are Copy" are also Copy.
- re [docs re Copy trait](https://doc.rust-lang.org/std/marker/trait.Copy.html) and [omission from docs re whether primitive types implement Copy trait](https://github.com/rust-lang/rust/issues/25893)

### Closures

Rust closures enable anonymous functions. Examples for annotated and inferred types of inline closures:
```rust
    let y: u32 = 10;
    let annotated = |x: u32| -> u32 { x + y };
    let inferred = |x| x + y;
```
Syntax notes:
- pipes around the parameter list, followed by
- the expression for the desired return value,
- where a no-arg closure (||) is an empty param list

Closures can reference values from their outer scope. They can also capture the outer values and use them; the captured var remains valid in its original scope. Example:

```rust
    let mut count = 0;
    let mut increment = || {
        count += 1;
        count
    };

    println!("count is {}", increment());
    println!("count is {}", increment());
    println!("count is {}", increment());
    println!("count after calling increment 3x is {}", count); // still valid!
```

Closures can be returned from functions. If any outer scope variables are captured by such a returned closure, they'll need to be moved into the closure.

Returned closure functions return an `impl` of a trait. _More about traits later._ For now, consider a trait an interface: defines what can be done, but doesn't specify the type to which it applies.

Returned closure functions can `impl` one of three traits: `Fn`, `FnMut`, `FnOnce`. These traits have a hierarchy of sorts: `Fn` can be used as `FnMut` or `FnOnce`; likewise, `FnMut` can be used as `FnOnce`. The inverse is not true.

***Examples: functions returning closures***

Print message:
```rust
fn print_msg<'a>(msg:&'a str) -> impl Fn() + 'a {
    let printer = move || { // move ownership of msg to printer closure
        println!("{msg}");
    };
    printer
}

fn main() {
  let f = print_msg("msg: hello, world"); // nothing printed yet
  f(); // invoke the function, ie the closure returned by print_msg
}
```
nb: the lifetime must be assigned explicitly in `print_msg` (string slice, `&str`), but not in `make_counter` (primitive type, `u32`)

Make counter:
```rust
fn make_counter() -> impl FnMut() -> u32 {
    let mut count = 0;
    let increment = move || {
        count += 1;
        count
    };
    increment
}

fn main() {
  let mut counter = make_counter();

  println!("count is {}", counter());
  println!("count is {}", counter());
  println!("count is {}", counter());
}
```



---

## Notes: Working through Rustlings

### Options

[Option type](https://doc.rust-lang.org/std/option/index.html)
- a structure with Some and None fields
  - notice the None field: a value is pattern-matched against valid options/variants; if invalid, return a well defined, unambiguous type (vs null or 0, etc)
- a common implementation: query the presence of a value and take action based on pattern-matching the value to valid options/variants; no match triggers the action associated with the None case

To illustrate (from rust docs):

```rust
fn divide(numerator: f64, denominator: f64) -> Option<f64> {
    if denominator == 0.0 {
        None
    } else {
        Some(numerator / denominator)
    }
}

// The return value of the function is an option
let result = divide(2.0, 3.0);

// Pattern match to retrieve the value
match result {
    // The division was valid
    Some(x) => println!("Result: {x}"),
    // The division was invalid
    None    => println!("Cannot divide by 0"),
}
```


