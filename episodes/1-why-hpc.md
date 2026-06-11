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

Scientific research is becoming increasingly computational [(Foster, 2011)](https://doi.org/10.7208/9780226038322-002).
Think, for example, of huge text datasets that comprise the entirety of Wikipedia or Reddit, or of sensor data from structures like bridges and tunnels, containing information on vibrations, seismic activity etc.
To make this more concrete, let's look at some studies that have tried to quantify this change:
One study looking at the size of medical image datasets used for research found that the median dataset size in 2018 was up to 10 times larger compared to 2011 ([Kiryati & Landau, 2021](https://doi.org/10.3390/jimaging7080155)).
Another study looking at big data in industry and academia, reports that the data that CERN records in a year is projected to increase from 160 petabytes in 2018 to 800 petabytes in 2026 ([Clissa, Lassnig, & Rinaldi, 2023](https://doi.org/10.3389/fdata.2023.1271639)).
Or, think of the hugely complicated climate models that scientists run to predict the impacts of the climate crisis.
Processing huge datasets or running calculations of this complexity requires a lot of computing power, more than an individual laptop or work station can provide.

To get around this problem, researchers may turn to High-Performance Computing (HPC) which refers to the use of powerful computers and programming techniques to solve computationally-intensive tasks.
HPC can refer to custom-built *supercomputers* or groups of individual computers that are connected together in a network and work as a unified system, forming a *cluster*.
We call these individual computers of a cluster *nodes*.
To give a taste of the benefit of using HPC over a regular computer, let's look at an example:
A PhD student wants to cross-validate a statistical model 1,000 times.
Running the model once on a laptop once takes one hour, meaning that cross-validating it 1,000 times would take over a month!
However, if all of the model runs happen in parallel on 1,000 nodes of an HPC cluster, the cross-validation would be complete in one hour.
How much research can be sped up is highly dependent on how efficient the code is and how parallelisable the problem.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

The information presented here has been copied and lightly adapted from:

- **[Working on HPC clusters using SLURM](https://cambiotraining.github.io/hpc-intro/materials/01-intro.html)**
- **[Introduction to High Performance Computing with Raspberry Pi](https://scw-aberystwyth.github.io/Introduction-to-HPC-with-RaspberryPi/01-HPC-intro/)**

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

## Case studies

Let's now look at some specific cases in which the use of an HPC cluster enabled impactful research.

### Case study 1: Physics

Most of us will remember the excitement that surrounded the release of the first image of a black hole, located in the centre of the M87 galaxy, captured in 2019.
Although not as widely publicised, an image of SgrA*, the black hole in the centre of our own galaxy, was also captured in 2022.
HPC underlies multiple of the steps involved in creating these images,
images which provide strong evidence for Einstein's theory of general relativity and have implications for our understanding of the universe.

#### Why does it matter?

Black holes are extreme regions of space, where it would appear that both general relativity and quantum physics play a role.
As such, they can serve as laboratories for testing these fundamental theories that explain how the universe works on the largest and on the smallest scales.
At the moment, both theories work well in their respective scopes, but physicists currently do not understand how to create a single theory that would be universal and, hence, explain the physics of black holes in detail.
With the Event Horizon Telescope (EHT) results, scientists are able to directly resolve the conditions of spacetime at the black hole boundary.

There are also ways in which these achievements matter beyond their contributions to the field of astrophysics.
Black holes tend to capture the public imagination in a way that not many scientific fields can.
The palpable excitement around these developments can engage the public with science and help foster a trust in experts that has been declining.

#### How did HPC contribute?
HPC was essential at every stage of the project.
EHT is a global network of radio observatories operating together through a technique called very-long-baseline interferometry (VLBI).
By synchronising telescopes across the Earth with atomic clocks, the EHT effectively created a virtual telescope the size of the Earth, capable of achieving the extraordinary resolution needed to image the black holes at the centre of M87 and our own Milky Way.
This generated petabytes of raw data that were transported to and processed by highly specialised supercomputers.
HPC systems combined and calibrated the data from multiple telescopes, reconstructed images from sparse and noisy measurements, and compared the results against extensive libraries of astrophysical simulations that modeled black holes, magnetic fields, and relativistic plasma flows.
Independent teams also used different computational imaging methods to verify that the observed ring structure was real and not an artifact of processing.
To bring to life the magnitude of computing power required for this, one of the analyses presented for SgrA* required 100 CPU hours, spread across two supercomputers.

#### Sources and further reading
- Why is it important to study black holes? What is there to learn from the EHT observations? ([link to the Event Horizon Telescape FAQ](https://eventhorizontelescope.org/faq/why-it-important-study-black-holes-what-there-be-learned-eht-observations))
- Press release (April 10, 2019): Astronomers Capture First Image of a Black Hole ([link to press release on EHT website](https://eventhorizontelescope.org/press-release-april-10-2019-astronomers-capture-first-image-black-hole))
- HPC supports first black hole image ([link to Partnership for Advanced Computing in Europe (PRACE)) website](https://prace-ri.eu/hpc-supports-first-black-hole-image/)
- Event Horizon Telescope Technology ([link to the EHT website on Technology topics](https://eventhorizontelescope.org/technology))
- We got it! Astronomers reveal first image of the black hole at the heart of our galaxy ([link to NSF website](https://www.nsf.gov/news/we-got-it-astronomers-reveal-first-image-black-hole-heart))


### Case study 3: Biology
Another well-publicised piece of research that made heavy use of HPC is AlphaFold.
AlphaFold is an AI programme that is highly accurate in predicting the 3D structure of proteins.

#### Why does it matter?
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

#### How did HPC contribute?
The use of HPC was fundamental in the development of AlphaFold and remains important for its use.
In developing AlphaFold, both large amounts of data and complex resource-intensive software was required.
Starting with data, AlphaFold was trained on very large biological datasets, including experimentally determined structures and extensive protein-sequence databases, such as UniProt.
An innovation that contributed to the success of AlphaFold was the use of evolutionary covariation data.
Evolutionary covariation is based on the observation that after one amino acid in a protein becomes mutated over evolutionary time, a compensatory mutation in another amino acid often occurs to maintain the structure or restore the function of the protein.
This can indicate that these two amino acids are in direct physical contact in the folded protein, giving clues to the protein's overall 3D structure.
Finding these correlations requires multiple sequence alignments of related proteins, and large-scale comparisons between pairs of amino acids.

The system that this data was used to train is a deep neural network, a type of machine learning model.
This neural network consists of hundreds of layers arranged as a two-dimensional residual architecture with dilated convolutions, allowing it to capture relationships between amino acids that may be far apart in the sequence but close in three-dimensional space.
Training such a model requires processing large biological datasets and iteratively updating millions of parameters using stochastic gradient descent.
In practice, this meant running training jobs across 8 GPUs in parallel over hundreds of thousands of training steps.
Even with this level of parallelism, a single training run took about 5 days to complete.

#### Sources and further reading

- Improved protein structure prediction using potentials from deep learning ([link to academic publication on AlphaFold 2](https://doi.org/10.1038/s41586-019-1923-7))
- AlphaFold uses open data and AI to discover the 3D protein universe ([link to blog post on EMBL.org](https://www.embl.org/news/science/alphafold-using-open-data-and-ai-to-discover-the-3d-protein-universe))
- Open access to predicted proteins via AlphaFold Protein Structure Database ([link to EMBL-EBI database](https://alphafold.ebi.ac.uk/))
- Online training on AlphaFold ([link to EMBL-EBI training](https://www.ebi.ac.uk/training/online/courses/alphafold/))

### Case study 4: Digital Humanities
Living with Machines was a research project studying the first industrial revolution, which took place in Britain roughly in the 19th century.
The project used massive digitised historical collections and computational analytical tools to examine the human, social and cultural consequences of this historical movement.

#### Why does it matter?
The Industrial Revolution is a period of history that is hugely important to Britain, but also had world-wide consequences.
Gaining more insight into how it affected people and places is valuable historical work.

The central theme of the Living with Machines project is the mechanisation of work practices.
This is a topic that speaks directly to present debates about how society can accommodate the revolutionary consequences of AI.
To understand the fraught co-existence of human and machine, this project contends that we need research methods that combine technological innovation and human expertise.

The tools that the Living with Machines project created can be used in other areas within and outside of Digital Humanities.
These include tools for parsing maps, matching "fuzzy" words that have been scanned, and models that can read 19th-century English.

#### How did HPC contribute?

Living with Machines encompassed a large number of projects, many of which used HPC and some that did not.
Below we explore three tools that were developed as part of the project which did use HPC.

##### MapReader

The first tool we'll look at is `MapReader`, a free open-source Python library using computer vision methods to analyse scanned or born-digital maps.
One of the innovations introduced by this tool is that annotation was carried out not at the level of the pixel, but rather of the "patch", a flexible and meaningful semantic unit. 

HPC was already used in the creation of the dataset that was used to train and evaluate the model.
This data is 16,439 scanned Ordnance Survey map sheets at 1:10,560 scale, surveyed between ca. 1890 and the beginning of WWI.
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
Adding to that changes and inconsistencies in spelling  and the use of characters have since fallen out of favour and the picture becomes very complex.

`DeezyMatch` uses different types of deep neural networks, the hyperparameters of which can be configured without the code needing to be modified.
It also does not require a model to be trained from scratch, but rather finetune a model that has already been trained, which is useful in cases where limited training examples are available.
HPC was used to preprocess data and train models (28 GPU or 54 CPU minutes) and to generate and combine candidate vectors (39 GPU or 204 CPU minutes).

##### Neural language models for 19th century English

Living with Machines also released four types of neural language models trained on 19th century English.
The data used for this was 47,685 books published between 1760 and 1900.
The text of the books was preprocessed, separated into sentences and tokenised into 5.1 billion tokens (essentially words).
The model we will look at here was BERT, which was trained on 4 NVIDIA Tesla K80 GPUs in parallel.

One of the models that was trained, BERT, was used in a range of tasks later on.
One of these tasks was detecting atypical animacy, i.e. exploring how animate people considered machines.
The method went as follows:
1. extract high-quality sentences from a varied and representative corpus of texts from the long 19th century that use the word "machine".
2. mask the word "machine" and use a neural language model trained in 19th century English to predict the masked word
3. calculate an animacy score for the masked word from the predictions of the language model

Variants of this approach include annotating sentences for "humanness" (an attribute related to, but distinct from animacy) and comparing the predictions that models trained on texts from different times make (i.e. from pre 1850, 1850-1875, 1875-1890, 1890-1900, and contemporary).

On a basic level, this line of inquiry can capture the implicit and changing attitudes to who is expected to do different types of work and the changing senses of ambiguous words across time.
On a deeper level, it can tell us about how animate and/or human machines were perceived to be, with implications about how much empathy people might extend to them.
Interestingly, but perhaps not surprisingly, in contexts that were annotated as high in animacy but low in humanness, the 19th century models would sometimes predict the word "slave" instead of "machine" or "man".

#### Sources and further reading

- Living with Machines ([link to the Living with Machines 'About' page](https://livingwithmachines.ac.uk/about/))
- MapReader: A Computer Vision Pipeline for the Semantic Exploration of Maps at Scale ([link to publication](https://doi.org/10.48550/arXiv.2111.15592))
- DeezyMatch: A Flexible Deep Learning Approach to Fuzzy String Matching ([link to publication](https://aclanthology.org/2020.emnlp-demos.9.pdf))
- Neural Language Models for Nineteenth-Century English ([link to publication](https://doi.org/10.48550/arXiv.2105.11321))
- Living Machines: A study of *atypical* animacy ([link to publication](https://aclanthology.org/2020.coling-main.400.pdf))
- The Living Machine: A Computational Approach to the Nineteenth-Century Language of Technology ([link to publication](https://muse.jhu.edu/pub/1/article/903976))
- When Time Makes Sense: A Historically-Aware Approach to Targeted Sense Disambiguation ([link to publication](https://aclanthology.org/2021.findings-acl.243.pdf))

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


::::::::::::::::::::::::::::::::::::: callout

High-Performance Computing and Artificial Intelligence

::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- Research is becoming more computational and, as such, requires more powerful computers.
- HPC enables research in various disciplines.
- AI is a field that often requires HPC resources.

::::::::::::::::::::::::::::::::::::::::::::::::
