---
title: 'Picture Perfect: AI + Medical Imaging'
date: 2018-05-25T18:03:52-07:00
draft: false
author: "Monica Spisar"
authorLink: "https://monicaspisar.com"
description: 'Picture Perfect 2017'
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

## Picture perfect: AI + medical imaging
_Caveat emptor! Written in November 2017. Progress in AI is astonishingly rapid: this is inevitably out of date._

## Radiology's inevitable evolution

Artificial intelligence (AI) in medical imaging is a controversial topic - up for debate are questions regarding its implementation (from both technical and regulatory standpoints), ultimate potential (presuming it has the theoretical potential to do better, will it do better in practice, and how might it alter clinical processes?), and impact on t​he future role of clinicians [^1].

Google's Geoffrey Hinton - an AI pioneer, now heading up the Vector Institute for Artificial Intelligence - once ​stated​ [^2] that "​People should stop training radiologists now. It's just completely obvious that, within 5 years, deep learning is going to do better than radiologists because it's going to be able to get a lot more experience.​" Somewhat less sensationally, ​in a subsequent conversation with Siddhartha Mukherjee​ [^3], Hinton clarified that "​The role of radiologists will evolve from doing perceptual things that could probably be done by a highly trained pigeon to doing far more cognitive things…". ​Constraining predictions regarding AI's immediate-future uses in radiology to reading X-rays, CT scans, and MRIs, Hinton pulled back expectations by offering the hypothesis that, at some point, "​learning algorithms will make pathological diagnoses.​" In other words, artificial intelligence might facilitate the work of clinicians, but it won't eradicate their necessity. "​Early and accurate diagnosis is not a trivial problem. We can do better. Why not let machines help us?​"

Indeed - why not? Both excitement and fear are audible in the buzz around AI that's created a narrative of machines potentially rendering humans unnecessary for various tasks. Yet, the fact remains that even relatively routine tasks delegated to AI continue to require a high degree of human influence and supervision.

## Shades of AI

The dominant popular narrative regarding AI is rife with misunderstanding about the degree to which AI operates independently of human influence. Simply put, AI requires comprehensive instructions from humans - it does not operate independently at all. Yes, much speculation exists regarding whether and when that will change, but we're not there yet.

AI software comprises a complete instruction set for taking an input and ultimately rendering an output which represents a claim regarding that input. Constraints on the form and format of the input are set by humans. The complete details of how to arrive at the output are determined and coded into the AI software by humans. The functions governing the decision-making processes leading to the output are constructed by humans, and humans encode instructions as to how parameter space will be traversed during the iterative process of stepping toward an output. Humans also construct and encode the threshold functions which contribute to the AI's "decision-making" process.

Every decision critical to how the AI performs is made by humans.

What, then, does the AI contribute 'independently'? In reality, nothing. It does the grunt work, applying its computational speed to evaluate parameter combinations to identify that which most closely approaches the human-supplied criteria for success.

The fact that humans do not have the cognitive computational power to follow along in real time as the algorithm traverses parameter space doesn't quite support the idea that the algorithms work in a mysterious fashion. Given the time, a mathematician could walk that same path and arrive at the same result. It would just take longer. The AI is a man-made means to an end, with all the limitations, biases, and potential for error inherent in that.

This form of AI, known as 'narrow AI', is strong and fast but, arguably, not very intelligent at all.

One aspect that's key to most forms of narrow AI is the necessity to train the algorithm to perform the relatively narrowly defined task by telling the AI what the 'right' answer is for particular inputs and allowing the AI to adjust itself to become an expert with regard to such inputs - similarly to how a human might train for a standardized test.

Let's take a moment to address the datasets selected to train algorithms. In order to acquire the ability to handle input variations (not all cats are posed identically in the training data photographs), AI requires a variety of examples on which to train. (In tech speak, this is known as avoiding overfitting. Overfitting is when a model gives a great result for the training data, but tends to perform poorly otherwise - the model isn't generally useful.) For each datapoint in the training dataset, the AI's performance is measured, a loss function computed (how badly did it do?), and that loss function fed back to the AI to guide the parameter changes to try on the next training pass. This repeats until humans deem the AI successful.

Training datasets are critically important. Without training data that's sufficiently representative of the likely range of inputs, the outputs may be problematic. This is known as bias, which has the potential to generate outputs which represent something other than what was intended by the AI developers. Also important are exceptional cases. In medical diagnostics, the signal is often an anomaly, and training data ultimately help identify commonalities, not exceptions.

Again, the preceding collectively addresses narrow​ AI - ​ the driver behind technologies such as Google's AlphaGo and IBM's Watson - where a combination of training data and processing algorithms are optimized to perform well on a specific task. While remarkable, the applicability of each instance of narrow AI is highly constrained.

There's an enormous gap between narrow AI & artificial general intelligence (AGI). For the moment, AI bears little semblance to AGI, and this is true in radiology as well. A distant cousin to narrow AI, AGI has no agreed-upon definition. The Machine Intelligence Research Institute at Berkeley offers four ​operational definitions for AGI​ [^4], in which the AGI has the ability to:
1. Pass the Turing test: The Turing test, developed by Alan Turing in 1950, is a test of a machine's ability to exhibit intelligent behavior equivalent to, or indistinguishable from, that of a human. [^5]
2. Pass the 'coffee test' (Goertzel et al. (2012)): "go into an average American house and figure out how to make coffee, including identifying the coffee machine, figuring out what the buttons do, finding the coffee in the cabinet, etc."
3. Pass the 'robot college student test' (Goertzel (2012)): "when a robot can enrol in a human university and take classes in the same way as humans, and get its degree, then I'll [say] we've created [an]… artificial general intelligence."
4. Pass the 'employment test', proposed by Nils Nisson in ​[^6]:​ "Machines exhibiting true human-level intelligence should be able to do many of the things humans are able to do. Among these activities are the tasks or "jobs" at which people are employed. I suggest we replace the Turing test by something I will call the "employment test." To pass the employment test, AI programs must… [have] at least the potential [to completely automate] economically important jobs."

Radiologists perform myriad complex tasks not at all suited to narrow AI. ​Dr. Paul Chang​ [^7] notes that radiologists adapt to new technologies and are continuously reinventing themselves. Undertaking any substantial subset of radiologists' responsibilities would necessitate AGI capabilities which aren't yet on the horizon in any realm of AI application.

## The 'sudden' evolution of AI

Why the recent spotlight on AI in radiology? In medical imaging, AI research has been ongoing for decades, with applications spanning image processing, segmentation, and analysis. The references of a ​1992 review article on neural networks in medical imaging​ [^8] include topics such as supervised and unsupervised learning, ​self-organising neural pattern recognition machine​ [^9] (1987), ​self-learning neural networks in electrocardiography​ [^10] (1990), and training of ECG signals in neural network pattern recognition​ [^11] (1990).

Moving forward, in recent years there's been an explosion of effort on all things AI - in medical imaging and beyond. This phenomenon has been made possible by two things: abundance of available training data, and advances in GPU technology​ [^12] which facilitate low-cost, widespread access to computational power. Access to data has greatly increased with the advent of infrastructure to facilitate collection, processing, and sharing of large data sets, automation of information storage systems, and the ever greater quantity of data open sourced as a matter of course.

AI algorithms are computationally expensive, hence processing speeds are key to practical implementation. The challenges of computation rates which impeded progress in AI decades ago are no longer deal breakers. As access to large datasets and powerful computers became a non-issue, a renewal of interest in AI research was natural. In medical imaging, algorithms - such as computer aided diagnosis (CAD) algorithms pioneered in the 1980s - had been necessarily optimized to work on those slow(er) computers; techniques more closely aligned with machine learning couldn't be implemented in real time. Advances in GPU technology lifted that constraint.

## Deep learning & GPUs

The need for GPU power is closely linked to advances in AI algorithms - specifically, those falling into the category of deep learning with convolutional neural networks (CNNs). Deep learning systems based on CNNs still fall into the category of narrow AI, identifying patterns in new data after having been trained to identify patterns of interest in annotated data. The training set will include, for example, labelled images of tumors. The AI algorithm thus trained evaluates a new image, investigating whether the patterns identified in the training data have a likely match therein. If the evaluation done by the AI algorithm indicates a statistical likelihood of a match with the training data, the new image will receive the label associated with the matching pattern in the training data set - in this case, 'tumor.'

Convolution - the C in CNN - is, essentially, a method of weighting input data to achieve a desired output; an intricate relationship between AI parameters drives the algorithm's evaluation process. Convolution is a means for avoiding the overly simplistic situation of weights between layers (or steps in the AI decision-making process) acting in isolation. In the case of CNNs, the convolutions are performed on neural nets - weight maps assigned to layer elements of the CNN. A greater quantity and variety of inputs seem to better inform the algorithm's intuition. Unfortunately, that complexity fuels the perception that AI is, in a sense, beyond human control - a black box. But humans design the algorithms, write the code, and generate the training data; AI is a deterministic system. For every input, the output could be calculated by a fast enough human.

So back to the question of why the computational expense? Deep learning with CNNs involves iterative fine tuning of the high numbers (typically millions +) of parameters via training on many (tens of thousands +) well-characterized, detailed datapoints in training datasets. Until recently, computation times for deep learning with CNNs were entirely impractical. The advent of rapid-processing GPUs has solved that issue, enabling a new focus on - and progress with - deep learning techniques which have proven highly successful for many applications, including radiology.

The key difference between an AI approach and a CAD approach to medical imaging? In CAD, humans provided instructions on ​what​ to look for. In AI, humans provide instructions on ​how to look. In either case, the algorithms are based entirely on human instruction so, although their performance characteristics may differ, neither one is more 'intelligent' than the other.

Today's medical imaging AI software is provided with examples of the element of interest and given a computational map for evaluating 'success.' The AI is trained to associate individual examples with their specific labels or annotations (outcomes). Armed with a sufficiently large training set, the AI algorithms guide the process of characterizing the element in comparison to previously characterized - ​by a human - i​nstances of other images/data. The image to be classified doesn't need to be a pixel-for-pixel match to an image present in the training data; rather, patterns are sought which correspond to, for example, the labels 'lesion' or 'no lesion' per the model developed with the training data. The likelihood of whether these patterns of interest are present feeds into a decision on whether or not the image includes lesions. If so, boundaries can be produced from this decision data, labels generated, and quantification can proceed based on the code/instructions provided.

## Reality check

Realistically, AI in the near-term is expected to to reduce the time radiologists spend on repetitive, low-level tasks. For example, ​Lee et al. predict​ [^13] it will deliver "quantitative analysis of suspicious lesions, and may also enable a shorter time for reading due to automatic report generation and voice recognition." Such quantitative analysis might extend to organ volume, specific angles, ratios, etc.

Otherwise obscured information may be detectable with AI. It can also serve as a second set of eyes, and provide opportunities for experts to extend the reach of their accumulated wisdom. This last point is reflected in a ​report​ [^14] regarding IBM's work toward deep learning systems intended to multiply expert influence. "The goal is to scale the expertise of the clinician," says John Smith, an IBM research fellow and manager of multimedia and vision at IBM Thomas J. Watson Research Center. "The computer can see a lot more data than any clinician can ever see." Charles Koontz, chief digital officer of GE Healthcare, s​hares a similar perspective​[^14], "What we're developing is a suite of applications to make them [people] more effective."

## The robots aren't coming (yet)

Concerns regarding AI overextending its own influence to 'take over' are poorly supported. The fact remains that generalized AI is not yet here and we're still well in the realm of narrow AI. Kai-Fu Lee, a former Google China CEO, ​discussed narrow vs general AI​ [^15], stating that "​…General AI isn't here. There are simply no known engineering algorithms for it. And I don't expect to see them any time soon. The "singularity" hypothesis extrapolates exponential growth from the recent boom, but ignores the fact that continued exponential growth requires scientific breakthroughs that are unlikely to be solved for a hundred years, if ever."

The state of the art in the realm of medical imaging supports the idea that we are still some ways off from automated systems which work seamlessly and intelligently to take over human roles in the clinic. As Mukherjee ​reports​ [^3]: "Some of the most ambitious versions of diagnostic machine-learning algorithms seek to integrate natural-language processing (permitting them to read a patient's medical records) and an encyclopedic knowledge of medical conditions gleaned from textbooks, journals, and medical databases. Both I.B.M.'s Watson Health, headquartered in Cambridge, Massachusetts, and DeepMind, in London, hope to create such comprehensive systems. I watched some of these systems operate in pilot demonstrations, but many of their features, especially the deep-learning components, are still in development."

## Access to data

Deep learning systems in medical imaging applications​ [^16] almost exclusively utilize convolutional neural networks (CNNs). CNNs require large amounts of labeled data and ​the availability of large, appropriately annotated medical data sets is hampered by privacy concerns and proprietary use​ [^17]. And, naturally, rare conditions are, by their very nature, underrepresented in the data.

Techniques such as ​transfer learning​ [^18] pose potential solutions, but sufficient data is still required to fine tune from generalized learning on large scale, annotated natural datasets (such as ImageNet) to specific learning on datasets including the actual features of interest. Aiming to provide guidance on the quantity of training data required, Researchers at Massachusetts General Hospital and Harvard Medical School developed a method for evaluating performance as a function of number of training sets; in practice, however, researchers determine the minimum required training cycles via trial and error.

Which brings us to the question of available data for training cycles, which is a particular struggle in medical imaging as specialized equipment and environment are required to generate images. Also, privacy is an important consideration for any form of patient data, and appropriately labeled training data is ill suited for posting in a public repository without extensive preparation of the data to ensure it is both anonymized and appropriately annotated. Kohli et al.​ [^19] note that "everyone participating in medical image evaluation with machine learning is data starved". Of benefit to deep learning researchers, Andrew Beam of Harvard maintains a GitHub repository with a curated list of Medical Data for Machine Learning with links to data. So, while ImageNet and Beam's repository are first steps toward a solution, access to sufficient and appropriate data continues to be a substantial challenge.

## The role of the human in radiology's future

In regard to the goal of automating processes, it is worth noting that there is no single, definitive deep learning architecture or corresponding parameter set for medical imaging generally, nor even for specific imaging applications. Moreover, new advances, such as ​implementation of fully convolutional networks (FCNs)​ [^20], will further crowd the playing field. It's not guaranteed that there will ever be a complete eradication of the human component in deep learning systems as applied to radiology.

Currently, deep learning systems for medical imaging require considerable human input to function as intended, even in cases where such input is being minimized. As an example, consider a recent ​automated muscle segmentation study​ [^21] carried out by researchers from Massachusetts General Hospital and Universitaetsmedizin Berlin. The researchers demonstrated promising results for automated muscle segmentation on CT images for body morphometric analysis, with segmentation time reduced from 30 minutes to 0.17 seconds and the introduction of an average error of less than 3.68%. They concluded that "The fully automated segmentation system can be embedded into the clinical environment to accelerate the quantification of muscle to provide advanced morphometric data on existing CT volumes and possible expanded to volume analysis of 3D datasets." Of note, however, the methods section details the researchers' tweaks to standard FCN algorithms (variations on the fusion of layers) prior to deployment, as well as their empirical determination of both the optimal learning rate and weight decay parameters. These modifications and optimizations are key to the success of such techniques - rendering them hardly ready for deployment in an average clinic.

Still, the promise of automated systems streaming relevant, reliable data to clinicians is an exciting one, as is the promise of automated - and improved - imaging. The ultimate potential for deep learning in medical imaging is as yet unknown, but can reasonably be expected to evolve to incorporate state of the art AI capabilities as they emerge.

## Roots of AI in medical imaging

The ​May 2016 IEEE Transactions on Medical Imaging​ [^22] special edition on deep learning noted that neural networks were applied to lung nodule detection as early as 1993, and ​Erik Ridley of Aunt Minnie reported​ [^23] that "The use of AI in radiology actually isn't new; thousands of papers on computer-aided detection (CAD) and image analysis algorithms have been published in journals and presented at meetings over the past 30 years."

Such CAD systems, however, tended not to be "learning systems" with dynamically and iteratively adaptive computational algorithms aimed at achieving recognition without relying on deterministic models; rather, the standard approach was to optimize image data fit to such a priori models. The distinction is important to grasp as medical imaging CAD efforts in recent decades have yielded numerous disappointing results, and almost none have been widely adopted.

Deep learning techniques applied to medical imaging will help move the needle toward the goal of truly intelligent imaging; ​further computational advances by researchers on the bleeding edge, such as Hinton​ [^24], will accelerate the process. In anticipation of this, startups in the space are plentiful. Diagnostic Imaging ​highlights three machine learning startups​ [^25] focused on medical applications and, along similar lines, nanalyze published a t​wo​-p​art​ [^26][^27] series on startups focused on AI for medical imaging.

Startup Arterys - "the AI assistant for radiologists" - uses its cloud-based platform to bring "deep learning to medical imaging, starting with cardiac analysis." A segmentation feature is currently available, while prediction, tracking, classification, and detection are in development. Cloud-based solutions pose special challenges for data privacy, and Arterys' technology addresses security concerns by ensuring that "patient data stays within the hospital and is accessible by physicians from anywhere."

The major players in radiology are also deeply invested in AI efforts. GE coordinates research efforts with several academic and clinical research collaborators. G​E's partnership with UCSF [^28] aims to develop "deep learning algorithms aimed at delivering information to clinicians faster" while ​a GE partnership with PartnersHealth​ [^29] (Massachusetts General and Brigham & Women's) is "pinpointing what's been holding AI back and developing the business model, platform and tools to ensure clinicians and patients can benefit from its potential." IBM's Watson needs no introduction and has its toes in the healthcare pool, as well. According to nanalyze​ [^30]: "While best known for playing Jeopardy, Watson has applications across many industries including healthcare. "Watson Health Imaging" is a key part of Watson Health, and something which has been built over the years with some very strategic acquisitions of medical data."

IBM has a team developing its Cognitive Radiology Assistant, a system which "…analyzes medical images and then combines this insight with information from the patient's medical records to offer clinicians and radiologists support for decision-making."
Ultimately, it is still very early days for deep learning in radiology, though. There is, in fact, little in the way of deep learning powered offerings for widespread clinical use from the major medical imaging technology providers. For now.

## Regulatory hurdles

It is impossible to consider the future of deep learning in radiology without acknowledging the fact that it will need to earn its place in a highly regulated environment; with ​deep learning's 'black box' nature​ [^31], one other obstacle to clinical implementation will be satisfying the FDA of a new device or clinical software platform's safety and efficacy. Although we have yet to see how that will play out, new (or risky) medical devices have previously been successful in gaining FDA approval, and the groundwork is being laid; the ​first FDA approval for a clinical tool employing machine learning​ [^32] was awarded at the beginning of 2017 for Arterys' Cardio DL.

## Do no harm

As noted in Stanford's ​100 Year study on artificial intelligence​ [^33], "For decades, the vision of an AI-powered clinician's assistant has been a near cliché" and the goal of deploying AI to support - not replace - radiologists seems to be guiding the way forward. Armed with this perspective on the role of artificial intelligence in medical imaging, we might assess the radiologist's evolving role somewhat more positively than might be expected in view of Geoffrey Hinton's (original) remarks on the matter.

It remains to be seen how, exactly, artificial intelligence will permeate not only medical imaging, but also clinical workflow and coordination of disparate sources of data. In the highly complex and highly regulated world of medical devices, AI is a tool at the disposal of engineers and clinicians - and its tremendous potential to contribute to the continual improvement of medicine in its ultimate goal of effectively and efficiently diagnosing and treating patients is starting to be realized.

In addition to the time freed up for cognitively intense work once AI kicks in to perform the mundane tasks still required of many radiologists, potentially exciting developments include a tremendous volume of new data-knowledge (previously out of reach due to computational expense), the extended reach of expert opinion via contributions to ubiquitously employed training sets, and mitigation of clinical errors via the first fundamental theorem of probability - the law of large numbers.

With appropriate human oversight, AI in radiology has a good shot at remaining on the right side of Do No Harm… but do we even know what 'appropriate human oversight' looks like? ​That is likely to be the ultimate challenge for AI - and not just in radiology.

#### Originally published on [Medium](https://msyvr.medium.com/picture-perfect-ai-medical-imaging-f57eeb2b4b32) in 2017

---

## References

[^1]: [https://www.nejm.org/doi/full/10.1056/NEJMp1606181](https://www.nejm.org/doi/full/10.1056/NEJMp1606181)
[^2]: [https://www.youtube.com/watch?v=2HMPRXstSvQ](https://www.youtube.com/watch?v=2HMPRXstSvQ)
[^3]: [https://www.newyorker.com/magazine/2017/04/03/ai-versus-md](https://www.newyorker.com/magazine/2017/04/03/ai-versus-md)
[^4]: [https://intelligence.org/2013/08/11/what-is-agi/](https://intelligence.org/2013/08/11/what-is-agi/)
[^5]: [https://en.wikipedia.org/wiki/Turing_test](https://en.wikipedia.org/wiki/Turing_test)
[^6]: [http://ai.stanford.edu/~nilsson/OnlinePubs-Nils/General%20Essays/AIMag26-04-HLAI.pdf](http://ai.stanford.edu/~nilsson/OnlinePubs-Nils/General%20Essays/AIMag26-04-HLAI.pdf)
[^7]: [https://www.youtube.com/watch?v=4b0t7TzjRZE&feature=youtu.be](https://www.youtube.com/watch?v=4b0t7TzjRZE&feature=youtu.be)
[^8]: [https://link.springer.com/article/10.1007%2FBF02457822](https://link.springer.com/article/10.1007%2FBF02457822)
[^9]: [https://zbmath.org/0634.68089](https://zbmath.org/0634.68089)
[^10]: [https://www.jecgonline.com/article/0022-0736(90)90102-8/pdf](https://www.jecgonline.com/article/0022-0736(90)90102-8/pdf)
[^11]: [https://ieeexplore.ieee.org/abstract/document/691841](https://ieeexplore.ieee.org/abstract/document/691841)
[^12]: [https://www.engineering.com/nvidias-artificial-intelligence-boom-what-makes-ai-and-gpus-so-compatible/](https://www.engineering.com/nvidias-artificial-intelligence-boom-what-makes-ai-and-gpus-so-compatible/)
[^13]: [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5447633/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5447633/)
[^14]: [https://www.wsj.com/articles/ai-holds-promise-of-improving-doctors-diagnoses-1505226566#comments_sector](https://www.wsj.com/articles/ai-holds-promise-of-improving-doctors-diagnoses-1505226566#comments_sector)
[^15]: [https://www.wired.com/story/a-blueprint-for-coexistence-with-artificial-intelligence/](https://www.wired.com/story/a-blueprint-for-coexistence-with-artificial-intelligence/)
[^16]: [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5375621/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5375621/)
[^17]: [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094)
[^18]: [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4890616/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4890616/)
[^19]: [https://link.springer.com/article/10.1007/s10278-017-9976-3](https://link.springer.com/article/10.1007/s10278-017-9976-3)
[^20]: [https://link.springer.com/article/10.1007/s10278-017-9988-z](https://link.springer.com/article/10.1007/s10278-017-9988-z)
[^21]: [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094)
[^22]: [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7463094)
[^23]: [https://www.auntminnie.com/index.aspx?sec=ser&sub=def&pag=dis&ItemID=117221](https://www.auntminnie.com/index.aspx?sec=ser&sub=def&pag=dis&ItemID=117221)
[^24]: [http://www.cs.toronto.edu/~hinton/absps/Outrageously.pdf](http://www.cs.toronto.edu/~hinton/absps/Outrageously.pdf)
[^25]: [http://www.diagnosticimaging.com/pacs-and-informatics/how-radiologists-are-using-machine-learning](http://www.diagnosticimaging.com/pacs-and-informatics/how-radiologists-are-using-machine-learning)
[^26]: [https://www.nanalyze.com/2017/02/artificial-intelligence-medical-imaging/](https://www.nanalyze.com/2017/02/artificial-intelligence-medical-imaging/)
[^27]: [https://www.nanalyze.com/2017/08/12-startups-diagnosing-medical-images-ai/](https://www.nanalyze.com/2017/08/12-startups-diagnosing-medical-images-ai/)
[^28]: [https://www.ge.com/reports/software-please-doctors-looking-ai-speed-diagnosis/](https://www.ge.com/reports/software-please-doctors-looking-ai-speed-diagnosis/)
[^29]: [http://newsroom.gehealthcare.com/the-team-behind-the-future-of-ai-in-healthcare/](http://newsroom.gehealthcare.com/the-team-behind-the-future-of-ai-in-healthcare/)
[^30]: [https://www.nanalyze.com/2017/08/ibm-dominate-radiology-ai/](https://www.nanalyze.com/2017/08/ibm-dominate-radiology-ai/)
[^31]: [https://www.quantamagazine.org/new-theory-cracks-open-the-black-box-of-deep-learning-20170921/](https://www.quantamagazine.org/new-theory-cracks-open-the-black-box-of-deep-learning-20170921/)
[^32]: [https://www.forbes.com/sites/bernardmarr/2017/01/20/first-fda-approval-for-clinical-cloud-based-deep-learning-in-healthcare/#5c699b7a161c](https://www.forbes.com/sites/bernardmarr/2017/01/20/first-fda-approval-for-clinical-cloud-based-deep-learning-in-healthcare/#5c699b7a161c)
[^33]: [https://ai100.stanford.edu/2016-report/section-ii-ai-domain/healthcare/clinical-setting](https://ai100.stanford.edu/2016-report/section-ii-ai-domain/healthcare/clinical-setting)
