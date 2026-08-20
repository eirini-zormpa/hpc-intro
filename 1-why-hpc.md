---
title: "Why use HPC?"
teaching: 30
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- What are good use cases for a High-Performance Computing (HPC) cluster?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain when using an HPC cluster is a good idea.

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

::::::::::::::::::::::::::::::::::::: challenge 

## Icebreaker questions

What Digital Research Infrastructure facilities are you aware of in your institution?

:::::::::::::::::::::::::::::::::

Scientific research is becoming increasingly computational, relying on large datasets and advanced computing power [(Foster, 2011)](https://doi.org/10.7208/9780226038322-002).
This feels intuitively true, but it has also been verified by studies which have tried to quantify this change:
One study looking at the size of medical image datasets used for research found that the size of the median dataset in 2018 was up to 10 times larger compared to 2011 ([Kiryati & Landau, 2021](https://doi.org/10.3390/jimaging7080155)).
Another study, looking at big data in industry and academia, expects the data that CERN records in a year to increase from 160 petabytes in 2018 to 800 petabytes in 2026, a more than fourfold increase of an already huge amount of data ([Clissa, Lassnig, & Rinaldi, 2023](https://doi.org/10.3389/fdata.2023.1271639)).
In addition to ever-growing dataset size, scientists are also increasingly turning to computational methods.
For example, biology used to be a discipline based exclusively in a wet lab, but bioinformatics over the last few decades has become a substantial percentage of biological research.
Or, think of meteorology - people have been trying to predict the weather for millenia, but doing so as accurately as we can now is only possible because of big data and highly complex models.
These advances in data size and calculation complexity require _a lot_ of computing power, certainly more than an individual laptop or work station can provide.

To get around this problem, researchers may turn to High-Performance Computing (HPC) which refers to the use of powerful computers and programming techniques to solve computationally-intensive tasks.
HPC can refer to custom-built *supercomputers* or to groups of individual computers that are connected together in a network and work as a unified system, forming a *cluster*.
We call these individual computers of a cluster *nodes*.
To give a taste of the benefit of using HPC over a regular computer, let's look at an example:
A PhD student wants to cross-validate a statistical model 1,000 times.
Running the model on a laptop once takes one hour, meaning that cross-validating it 1,000 times would take over a month!
However, if all of the model runs happen in parallel on 1,000 nodes of an HPC cluster, the cross-validation would be complete in one hour.
How much research can be sped up is highly dependent on how efficient the code is and how parallelisable the problem.

::::::::::::::::::::::::::::::::::::: challenge 

## What kind of resources does this researcher need?

- Analyse survey responses from 300 human participants.
- Run a climate model simulation at high spatial resolution.
- Train a Large Language Model.
- Run a simple regression on CSV data (50 MB).

:::::::::::::::::::::::: solution 

## Solution
 
- Analyse survey responses from 300 human participants.
  - Answer: laptop
- Run a climate model simulation at high spatial resolution.
  - Answer: HPC
- Train a Large Language Model.
  - Answer: HPC
- Run a simple regression on CSV data (50 MB).
  - Answer: laptop

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## Case studies

Let's now look at some specific cases in which the use of an HPC cluster enabled impactful research.

### Case study 1: Physics

Most of us will remember the excitement that surrounded the release of the first image of a black hole, captured in 2019.
That was the black hole in the centre of the M87 galaxy; although not as widely reported on, an image of SgrA*, the black hole in the centre of our own galaxy, was also captured in 2022.
The existence of black holes was first posited over a century ago but, while they had been previously observed *indirectly*, 2019 was the first visual confirmation that black holes actually exist.
HPC underlies multiple of the steps involved in creating these images,
images which provide strong evidence for Einstein's theory of general relativity and have implications for our understanding of the universe.

#### Why study black holes?

Black holes are extreme regions of space, where it appears that both general relativity and quantum physics play a role.
General relativity does a good job of explaining the gravitation of very large objects and led to the discovery of the Big Bang.
This applies to black holes because of the vast gravitational pull they exhibit.
Quantum physics does a good job of explaining the behaviour of very small objects, specifically subatomic particles (like photons and electrons).
This applies to black holes because of the unknown nature of matter as it is pulled in.
Physicists currently do not have a way to reconcile the two, but black holes, where both general relativity and quantum physics play a role, can serve as laboratories for testing these fundamental theories.

Directly observing and taking a picture of a black hole is really difficult.
Part of the problem is that black holes are so massive and so dense that almost nothing can escape them, not even light.
That is because when something enters the boundary of the black hole (the _event horizon_), the velocity it would need to escape exceeds the speed of light, which is as fast as anything can move.
As such, the black hole is essentially dark - there is almost nothing to photograph.
Around the black hole is a structure called an _accretion disk_, a hot disk of gas which is the fuel and main light source of the black hole.
The gas swirls around the black hole and gradually moves from the outer part of the disk to its inner edge, where it falls into the event horizon.
The dark zone produced by this is known as the event horizon _shadow_ which is what we see in the images of the M87* and SgrA*.

Notably these are not photographs.
They are radiolight **images**, the result of complex observational and computational interpretation.
To create them, data were collected using eight pre-existing radio telescopes located across the Earth and connected with a technique called very-long-baseline interferometry.
This technique synchronises the telescopes and exploits the rotation of the Earth to form a virtual, Earth-size telescope called the Event Horizon Telescope.
This size is required to be able to achieve the extraordinary resolution needed to image the black holes at the centre of M87 and our own Milky Way.
The data used in the creation of these pictures were collected in 2017, but the image of M87* was not released until 2019, meaning it took two years for researchers to process the data and generate the image.
The image of SgrA* took even longer at five years.
The research teams involved in these projects were international and numbering 200+ specialists.

These images are an impressive feat of engineering, computing and international collaboration and, arguably, their impact extends beyond their contributions to the field of astrophysics.
Black holes, shrouded in mystery, can capture the public imagination in a way that is rare for scientific inquiry.
As a quick way to gauge the interest the 2019 black hole image generated, we can look at trends in Google searches for the term "black hole".
April 2019, when the M87* image was published, is the peak in worldwide searches for "black hole" since 2004, with the relative search interest being 5 times that of the second highest peak.
This is an imperfect tool, but it does show the impact the story had on the public.
Perhaps the thrill surrounding such discoveries can help engage the public with science and foster a trust in experts that has been declining.
It should also be mentioned that the face tied to this discovery was that of Dr Katie Bouman, now a Professor of Computing and Mathematical Sciences at Caltech, which feels significant given the general underrepresentation of women in STEM.

![Image of the black hole SgrA*, from the [Event Horizon Telescope website.](https://eventhorizontelescope.org/blog/astronomers-reveal-first-image-black-hole-heart-our-galaxy)](files/black-hole-sgra.png)

#### How did HPC contribute?
HPC was essential at every stage of this project.
First of all, the data involved in generating these images is incredibly large.
Remember that the Event Horizon Telescope is a global network of radio observatories operating together through very-long-baseline interferometry.
Depending on instrument setup, weather and other factors, a five-day observation campaign generates about a petabyte (PB) of raw data per observatory.
The total amount of raw data recorded in April 2017 is about 3.5 PB.
Processing this amount of raw interferometric data to transform it into an image required vast amounts of compute, provided by highly specialised supercomputers.

HPC systems combined and calibrated the data from multiple telescopes, reconstructed images from sparse and noisy measurements, and compared the results against extensive libraries of astrophysical simulations.
As mentioned previously, these images are not direct photographs - they require theoretical work, e.g. simulating how superheated, electrically-charged gas swirls around the black hole, from its outer part to its inner edge and finally falling into the event horizon to generate the shadow we see.
Independent teams also used different computational imaging methods to verify that the observed ring structure was real and not an artifact of processing.
The calculations supporting such theoretical work was undertaken using supercomputers located around the world, such as the German Tier-0 systems SuperMUC in Garching and the American NSF Frontera supercomputer and Open Science Grid.
A statistic that does a great job of illustrating the magnitude of computing power necessary for this work is that a single analysis, done as part of verifying the SgrA* image, required 100 million CPU hours, spread across the two aforementioned NSF supercomputers.

#### Sources and further reading
- Press release (April 10, 2019): Astronomers Capture First Image of a Black Hole ([link to press release on EHT website](https://eventhorizontelescope.org/press-release-april-10-2019-astronomers-capture-first-image-black-hole))
- Why is it important to study black holes? What is there to learn from the EHT observations? ([link to the Event Horizon Telescape FAQ](https://eventhorizontelescope.org/faq/why-it-important-study-black-holes-what-there-be-learned-eht-observations))
- How much data is recorded during an observation and how is it transferred to the central processing facilities? ([link to the Event Horizon Telescape FAQ](https://eventhorizontelescope.org/faq))
- HPC supports first black hole image ([link to Partnership for Advanced Computing in Europe (PRACE)) website](https://prace-ri.eu/hpc-supports-first-black-hole-image/)
- Event Horizon Telescope Technology ([link to the EHT website on Technology topics](https://eventhorizontelescope.org/technology))
- We got it! Astronomers reveal first image of the black hole at the heart of our galaxy ([link to NSF website](https://www.nsf.gov/news/we-got-it-astronomers-reveal-first-image-black-hole-heart))
- Anatomy of a Black Hole (link to [NASA website](https://science.nasa.gov/universe/black-holes/anatomy/))

### Case study 2: Biology
Another well-publicised piece of research that made heavy use of HPC is AlphaFold.
AlphaFold is a machine learning model that is highly accurate in predicting the 3D structure of proteins.

#### What do proteins do?
Proteins underpin life.
Although proteins can be represented as a linear sequence of amino acids, their function depends on how they fold, i.e. their precise 3D structure.
Insights into the structure, and thus the function of a protein is critical for understanding biological processes, from diseases that affect humans to bacteria that are found in our environment.
Understanding these processes can then be used in a wide range of applications, from drug discovery to fighting environmental pollution.
Indeed, the scientific breakthroughs that AlphaFold has enabled have contributed to combatting antibiotic resistance, developing malaria treatments, and creating enzymes to fight plastic pollution.

The first time a protein's structure was determined was back in 1958.
Since then, scientists have used experimental methods to uncover protein structure.
Although highly accurate, these methods are slow.
By 2020, the structure of approximately 200,000 proteins was uncovered using these techniques.
This may sound like a large number, but it pales in comparison to the number of known proteins - 200 million!
Naturally, computational prediction of protein structure had also been attempted; an international competition was even set up in 1994 with the goal of advancing the methods of identifying protein structure from sequence.
At the 14th iteration of the competition, in 2020, there was a breakthrough.
The AlphaFold 2 system was announced as being equally accurate to experimental methods.

![An artist's illustration of AI used in protein folding [Google DeepMind on Unsplash.](https://unsplash.com/photos/an-image-of-a-cell-phone-with-a-blue-background-htMw1CbMUIk)](files/ai-protein.jpg)

#### How did HPC contribute?
The use of HPC was fundamental in the development of AlphaFold and remains important for its use.
In developing AlphaFold, both large amounts of data and complex resource-intensive software was required.
Starting with data, AlphaFold was trained on very large biological datasets: Specifically on the experimentally-determined 3D structures of proteins in the [Protein Data Bank](https://www.wwpdb.org/) and their corresponding amino acid sequences in [UniProt](https://www.uniprot.org/).
An innovation that contributed to the success of AlphaFold was the use of evolutionary covariation data.
Evolutionary covariation is based on the observation that after one amino acid in a protein becomes mutated over evolutionary time, a compensatory mutation in another amino acid often occurs to maintain the structure or to restore the function of the protein.
This can indicate that these two amino acids are in direct physical contact in the folded protein, giving clues to the protein's overall 3D structure.
Finding these correlations requires multiple sequence alignments of related proteins, and large-scale comparisons between pairs of amino acids.
To give an idea of scale, the data provided in the AlphaFold repository is approximately 3.2TB.

All of this data was used to train a machine learning model, machine learning being a type of Artificial Intelligence able to learn patterns from very big, often very messy, datasets.
Specifically, AlphaFold is a deep neural network.
Neural networks were inspired by the human brain, where the connections between units become strengthened or weakened through training (analogous to neurons and synapses).
Deep neural networks consist of multiple *layers* of these artificial neurons - hundreds in the case of AlphaFold!
During training, AlphaFold learnt how to predict a protein's 3D structure from its amino acid sequence, a task that required the iterative updating of millions of parameters.
In practice, this meant running training jobs across 8 GPUs in parallel over hundreds of thousands of training steps.
Even with this level of parallelism, a single training run took about 5 days to complete.
Even after it's trained, AlphaFold typically requires HPC to generate predictions of protein structure.
For example, the installation instructions on the AlphaFold GitHub repository assume the existence of multiple GPUs. 

#### Sources and further reading

- Improved protein structure prediction using potentials from deep learning ([link to academic publication on AlphaFold 2](https://doi.org/10.1038/s41586-019-1923-7))
- AlphaFold uses open data and AI to discover the 3D protein universe ([link to blog post on EMBL.org](https://www.embl.org/news/science/alphafold-using-open-data-and-ai-to-discover-the-3d-protein-universe))
- Open access to predicted proteins via AlphaFold Protein Structure Database ([link to EMBL-EBI database](https://alphafold.ebi.ac.uk/))
- Online training on AlphaFold ([link to EMBL-EBI training](https://www.ebi.ac.uk/training/online/courses/alphafold/))
- AlphaFold GitHub repository ([link](https://github.com/google-deepmind/alphafold))

### Case study 3: Digital Humanities
Although HPC is most commonly used within the physical and engineering sciences, it also has the potential to make huge contributions in the fields of arts and humanities.
An example of a large-scale project that used advanced computing in the digital humanities is *Living with Machines*, a collaboration between the British Library, the Alan Turing Institute, Queen Mary University of London, University of East Anglia, University of Exeter, University of Cambridge and King's College London and funded by the UKRI Arts and Humanities Research Council.

Living with Machines brough together huge datasets of digitised historical documents and computational tools to study the Industrial Revolution which took place in Britain from the late 18th to the early 20th century.

#### Why is the Industrial Revolution important?
The Industrial Revolution is a hugely important historical period, the consequences of which were felt around the world, though it impacted Britain and other Western countries first.
Gaining a better understanding of this period, for example studying the impacts of technological advancement and mechanisation on people and places, is valuable historical work in and of itself.
Doing so at a time when AI is, depending on your perspective, promising or threatening to change the way we work and create art is especially pertinent.

The tools that the Living with Machines project created, e.g. for parsing maps, combine technological innovation with human expertise and can be used to study other questions within and outside of Digital Humanities.

![D. Napier & Son Ltd, 'Aero Engine in the Making', England, circa 1918. [Shared by Museums Victoria on Unsplash](https://unsplash.com/photos/grayscale-photography-of-man-facing-mechanical-machine-9Prj6M-JAaA)](files/industrial-revolution.jpg)

#### How did HPC contribute?

Living with Machines encompassed a large number of projects, many of which used HPC and some that did not.
Below we explore three tools that were developed as part of the project which did use HPC.

##### MapReader

The first tool we'll look at is `MapReader`, a free open-source Python library using computer vision methods to analyse scanned or born-digital maps.
One of the innovations introduced by this tool is that annotation was carried out not at the level of the pixel, but rather of the "patch", a flexible and meaningful semantic unit. 

HPC was already used in the creation of the dataset that was used to train and evaluate the model.
This dataset includes 16,439 scanned Ordnance Survey map sheets at 1:10,560 scale, surveyed between ca. 1890 and the beginning of World War I.
The size of the dataset was about 600Gb and it took about 32 hours on 6 cores to slice it into 30.5 million patches.

Of interest to the researchers in this case was the categorisation of patches as containing rail infrastructure versus buildings.
A subset of 62,020 manually annotated patches was used to train, validate, and test different models.
After a model was selected and finetuned, it was used for model inference on all 30,490,411 patches in the UK.
This took four NVIDIA Tesla K80 GPUs approximately 172 GPU hours.

##### DeezyMatch

`DeezyMatch` is also a free open-source Python library, this one used for string matching in historical documents.
*String matching* refers to the process of matching strings (words) to a knowledge base to facilitate Natural Language Processing (NLP).
This can be difficult to do well in historical documents because of the diversity in the appearance of the same word in different contexts.
For example, scans of a word handwritten in cursive or printed on degraded paper will look different to how that word is stored in a database.
Add to that changes and inconsistencies in spelling and the use of characters which have since fallen out of favour and the picture becomes very complex.

`DeezyMatch` uses different types of deep neural networks, the hyperparameters of which can be configured without the code needing to be modified.
It also does not require a model to be trained from scratch, but rather finetunes a pre-trained model; this is really useful in cases where only limited training examples are available.
A test case presented for `DeezyMatch` is its ability to correctly identify place names.
In this case, HPC was used to preprocess the data and train the models (28 GPU or 54 CPU minutes) and then to generate and combine the candidate vectors, meaning the places likely referred to in the text (39 GPU or 204 CPU minutes).

##### Neural language models for 19th century English

Living with Machines also released four types of neural language models trained on 19th century English.
The data used for this was 47,685 books published between 1760 and 1900.
The text of the books was preprocessed, separated into sentences and tokenised into 5.1 billion tokens (essentially words).
The model we will look at here was BERT, which was trained on 4 NVIDIA Tesla K80 GPUs in parallel.

BERT was used in a range of tasks, including detecting atypical animacy, i.e. exploring the degree to which people considered machines to be animate.
The method went as follows:
1. extract high-quality sentences from a varied and representative corpus of texts from (roughly) the 19th century that use the word "machine".
2. mask the word "machine" and use a neural language model trained in 19th century English to predict the masked word
3. calculate an animacy score for the masked word from the predictions of the language model

Variants of this approach include annotating sentences for "humanness" (an attribute related to, but distinct from animacy) and comparing the predictions made by models trained on texts from different times (i.e. from pre 1850, 1850-1875, 1875-1890, 1890-1900, and contemporary).

On a basic level, this line of inquiry can capture the implicit and changing attitudes to who is expected to do different types of work and the changing senses of ambiguous words across time.
On a deeper level, it can tell us about how animate and/or human machines were perceived to be, with implications about how much empathy people might extend to them.
Interestingly, but perhaps not surprisingly, in contexts that were annotated as high in animacy but low in humanness, the 19th century models would sometimes predict the word "slave" instead of "machine".

#### Sources and further reading

- Living with Machines ([link to the Living with Machines 'About' page](https://livingwithmachines.ac.uk/about/))
- MapReader: A Computer Vision Pipeline for the Semantic Exploration of Maps at Scale ([link to publication](https://doi.org/10.48550/arXiv.2111.15592))
- DeezyMatch: A Flexible Deep Learning Approach to Fuzzy String Matching ([link to publication](https://aclanthology.org/2020.emnlp-demos.9.pdf))
- Neural Language Models for Nineteenth-Century English ([link to publication](https://doi.org/10.48550/arXiv.2105.11321))
- Living Machines: A study of *atypical* animacy ([link to publication](https://aclanthology.org/2020.coling-main.400.pdf))
- The Living Machine: A Computational Approach to the Nineteenth-Century Language of Technology ([link to publication](https://muse.jhu.edu/pub/1/article/903976))
- When Time Makes Sense: A Historically-Aware Approach to Targeted Sense Disambiguation ([link to publication](https://aclanthology.org/2021.findings-acl.243.pdf))

::::::::::::::::::::::::::::::::::::: callout

## High-Performance Computing and Artificial Intelligence

Before we get into how HPC and AI relate to one another, let's establish what we mean by "AI".
Since ChatGPT was publicly launched in November 2022, the term "AI" tends to refer to generative AI chatbots, like ChatGPT and Claude.
More generally, AI is a field of computer science working on developing start machines that can perform tasks that would normally require human intelligence.
As such, "AI" is used to refer to the most advanced algorithms that can perform such tasks.

Before 2022, AI usually referred to Machine Learning.
Machine Learning is a subset of artificial intelligence that automatically enables a machine or system to learn and improve from experience.
Instead of explicit programming, machine learning uses algorithms to analyse large amounts of data, learn from the insights, and then make informed decisions. 
Machine learning algorithms improve performance over time as they are trained—exposed to more data.
Machine learning models are the output, or what the program learns from running an algorithm on training data.
The more data used, the better the model will get. 

*Source: [Google Cloud](https://cloud.google.com/learn/artificial-intelligence-vs-machine-learning)*

At the time of writing (in 2026), the prevailing meaning of AI is generative AI.
Generative models are used to, as the name suggests, generate - that can be text, images, videos etc.
Generative AI became possible with the creation of deep neural networks (a type of machine learning) and particularly Large Language Models (LLMs) which rely on the transformer architecture.

Modern AI methods (be it machine learning models or generative models) tend to be both data- and compute-intensive, requiring appropriate infrastructure.
Often, this infrastructure is an HPC cluster.
As such AI and HPC are in a symbiotic relationship, where AI methods require HPC infrastructure to be implemented on the scale we see today and HPC is experiencing growth due to the pervasiveness and large compute demands of AI.

::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- Research is becoming more computational and, as such, requires more powerful computers.
- HPC enables research in various disciplines.
- AI is a field that often requires HPC resources.

::::::::::::::::::::::::::::::::::::::::::::::::
