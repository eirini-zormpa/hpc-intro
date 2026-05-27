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
We call these indivisual computers of a cluster *nodes*.
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
images which provide strong evidence for Einstein's theory of general relativity and have implications for understanding of the universe.

#### Why study black holes in the first place?

Black holes are extreme regions of space, where it would appear that both general relativity and quantum physics play a role.
As such, they can serve as laboratories for testing these fundamental theories that explain how the universe works on the largest and the smallest scales.
At the moment, each of these theories works well in its respective regime, but physicists currently do not understand how to create a single physical theory that would be universal and, hence, explain the physics of black holes in detail.
With the Event Horizon Telescope (EHT) results, scientists are able to directly resolve the conditions of spacetime at the black hole boundary.

There are also ways in which these achievements matter on top of their contributions to the field of astrophysics.
Black holes tend to capture the public imagination in way that not many scientific fields can.
The palpable excitement around these developments can engage the public with science and help foster a trust in experts that has been declining.
It is also reassuring to see large-scale collaborations of an international scale: this work involved over 200 researchers and 8 telescopes across the globe.

#### How did HPC contribute?
HPC was essential at every stage of the project.
EHT is a global network of radio observatories operating together through a technique called very-long-baseline interferometry (VLBI).
By synchronising telescopes across the Earth with atomic clocks, the EHT effectively created a virtual telescope the size of the Earth, capable of achieving the extraordinary resolution needed to image the black holes at the centre of M87 and our own Millky Way.
This generated petabytes of raw data that were transported to and processed by highly specialised supercomputers.
HPC systems combined and calibrated the data from multiple telescopes, reconstructed images from sparse and noisy measurements, and compared the results against extensive libraries of astrophysical simulations that modeled black holes, magnetic fields, and relativistic plasma flows.
Independent teams also used different computational imaging methods to verify that the observed ring structure was real and not an artifact of processing.
To bring to life the magnitude of computing power required for this, one of the analyses presented for SgrA* required 100 CPU hours, spread across two supercomputers

#### Sources and further reading
- Why is it important to study black holes? What is there to learn from the EHT observations?[Linke to the Event Horizon Telescape FAQ](https://eventhorizontelescope.org/faq/why-it-important-study-black-holes-what-there-be-learned-eht-observations)
- Press release (April 10, 2019): Astronomers Capture First Image of a Black Hole [link to press release on EHT website](https://eventhorizontelescope.org/press-release-april-10-2019-astronomers-capture-first-image-black-hole)
- HPC supports first black hole image [link to Partnership for Advanced Computing in Europe (PRACE) website](https://prace-ri.eu/hpc-supports-first-black-hole-image/)
- Event Horizon Telescope Technology [Link to the EHT website on Technology topics](https://eventhorizontelescope.org/technology)
- We got it! Astronomers reveal first image of the black hole at the heart of our galaxy [link to NSF website](https://www.nsf.gov/news/we-got-it-astronomers-reveal-first-image-black-hole-heart)

### Case study 2: Engineering
Researchers from Queen's University Belfast are using HPC to model the performance of offshore and coastal structures.
This work places special emphasis on the behaviour of floating wind turbines, which are used to generate renewable energy.
Wind turbines that are further away from the coast benefit from, for example, stronger and more consistent wind, but their stability can suffer from the more adverse weather.
Modelling the various factors and their interactions that can affect their stability would be impossible without HPC infrastructure.

[Source](https://ni-hpc.ac.uk/CaseStudies/WindTurbineModelling/#d.en.1380908)

### Case study 3: Biology
Another well-publicised piece of research that made heavy use of HPC is AlphaFold.
AlphaFold is an AI programme that is highly accurate in predicting the 3D structure of proteins.

#### Why does it matter?
Proteins underpin life.
Although proteins can be represented as a linear sequence of amino acids, their function depends on how they fold, i.e. their precise 3D structure.
Insights into the structure, and thus the function of a protein is critical for understanding biological processes, from diseases that affect humans to bacteria that are found in our environment.
Understanding these processes can then be used in a wide range of applications, from drug discovery to fighting environmental pollution.

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

In this context, HPC was not simply accelerating an existing workflow; it enabled a fundamentally more powerful modelling approach.
Without access to parallel GPU computing and large-scale training infrastructure, it would not have been practical to train such deep, data-intensive networks or to iterate on their design.
This level of computational capability was a key factor in allowing AlphaFold to reach near-experimental accuracy and move protein structure prediction from a long-standing challenge to a routinely solvable problem.
The scientific breakthroughs that AlphaFold has enabled have contributed to combatting antibiotic resistance, developing malaria treatments, and creating enzymes to fight plastic pollution

#### Sources and further reading
- Improved protein structure prediction using potentials from deep learning ([link to academic publication on AlphaFold 2](https://doi.org/10.1038/s41586-019-1923-7))
- AlphaFold uses open data and AI to discover the 3D protein universe ([link to blog post on EMBL.org](https://www.embl.org/news/science/alphafold-using-open-data-and-ai-to-discover-the-3d-protein-universe))
- Open access to predicted proteins via AlphaFold Protein Structure Database ([link to EMBL-EBI database](https://alphafold.ebi.ac.uk/))
- Online training on AlphaFold ([link to EMBL-EBI training](https://www.ebi.ac.uk/training/online/courses/alphafold/))

### Case study 4: Archaelogy
Researchers at the University of Bradford used their local HPC cluster to recreate 3D models of degraded sites.

[Source](https://www.techmonitor.ai/technology/data/university-of-bradford-hpc?cf-view)

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
