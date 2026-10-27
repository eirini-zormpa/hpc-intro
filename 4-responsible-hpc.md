---
title: "How to use HPC resources responsibly"
teaching: 30
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- What considerations are important for sharing resources with others?
- What is the environmental impact of HPC?
- What steps can limit the environmental impact of HPC use?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- TBA

::::::::::::::::::::::::::::::::::::::::::::::::

HPC and other computing facilities are free at the point of access, but they do come with significant monetary and environmental costs.
This is something that both the people running and using those facilities need to be mindful of.

## Sharing resources

HPC facilities are used by a large number of people.
Like with all shared resources, it's important that all users are mindful of how their actions impact other users.

In the following paragraphs, you will learn about some common considerations when using HPC facilities.
These have been adapted from the [Using resources effectively](https://carpentries-incubator.github.io/hpc-intro/18-resources.html) and [Using shared resources responsibly(https://carpentries-incubator.github.io/hpc-intro/19-responsibility.html) episodes of the HPC Carpentry lesson [Using High-Performance Computing Systems](https://carpentries-incubator.github.io/hpc-intro/index.html) and you can find more detail there.

### Make code efficient
Code efficiency essentially means running that code for as few resources as possible.
Efficient code will generally run faster, saving costs on expensive compute time and freeing up the resource for others to use.
It generally also uses less electricity, which helps keep the environmental impact of HPC as low as possible (more on this in the following section).

Writing efficient code is often tied to using good software engineering practice; if you are not sure how to do this, consider getting help from your local Research Software Engineering team.

Once the code has been made as efficient as possible, it is important to be accurate in requesting resources to run it.
That is, if the code runs in 2 hours over 4 nodes, it is important that this (or slightly more) is how much resource you request.

### Don't clog up the login nodes

Login nodes are shared across multiple (or even all) cluster users and are reserved for specific actions, most importantly launching jobs.
Running resource-intensive jobs (like doing heavy computations) should be avoided as it could negatively affect others' ability to use the cluster.

### Test code before scaling

Make sure your code runs (both locally and on the cluster) before dedicating a lot of resource on it.
On busy HPC facilities, you may have to wait for days before there is enough resource to run your job, so you want to make sure your code will run successfully, or give you useful information even if it fails.
Having code fail within a few seconds when it has been allocated hours of compute time is both frustrating for you and wasteful for others who aren't able to use the resources while they are sitting idle.

Testing your code on a small subset of data (or in a similarly scaled-down manner) helps avoid glaring errors that cause the code to fail.
Most systems will provide a way to test code before running the whole job.

## Environmental impact of HPC

Before we focus on how HPC and large-scale computing fit into this, the main point to establish is that human activity has had catastrophic impacts on the Earth and the climate.
One contributing factor is the increase in the emission of greenhouse gases, e.g. carbon dioxide (CO2), primarily through the burning of fossil fuels.
These emissions have risen steadily since the Industrial Revolution in the late 18th century and have led to long-term heating of Earth's climate system.
Without urgent and radical action, the Earth's average temperature will rise by 4-5 degrees Celsius by the end of the 21st century.
This xkcd comic illustrates how extraordinary that is.

![](https://imgs.xkcd.com/comics/4_5_degrees.png)

Credit: Randal Munroe of xkcd comics (https://xkcd.com/1379/), reshared under a [CC-BY-NC licence](https://creativecommons.org/licenses/by-nc/2.5/).

Although CO2 emissions are only part of the problem, they are what is most relevant to HPC and, as such, will be the focus of this section.

::::::::::::::::::::::::::::::::::::: callout

## Net zero and carbon neutral

Eliminating emissions is more important and more impactful than neutralising them.

::::::::::::::::::::::::::::::::::::::::::::::::

We can think about emissions as they relate to different stages of HPC usage:

- embodied emissions
- operational emissions
- downstream emissions

Starting with *embodied emissions*, these relate to emissions associated with the creation of the HPC facility.
These include emissions from mining and transporting rare-earth minerals, manufacturing and transporting hardware and construction of the building housing the HPC facility.
That is, all the emissions that needed to happen for the HPC facility to exist in the first place.

*Operational emissions* relate to emissions associated with the everyday running of the HPC facility.
These include emissions from producing electricity to power and cool the hardware that make up the facility and transport for the staff that operate the facility.
If one were to include long-haul flights for staff to attend international conferences, this would be the largest contribution to CO2 emissions.

*Downstream emissions* relate to emissions associated with products of the HPC facility.
For example, a software application that is developed using an HPC facility and is adopted by other users; emissions associated with its use would be downstream emissions.

### Limiting emissions
It is important to keep in mind that the best thing to do is to stop emissions as much as possible.
The environmental crisis we are facing will not be solved purely through individual action, but it is important to acknowledge that we each have a part to play.
The most impactful think you can do is to mobilise - talk to people at your institution to raise awareness and to change institutional practices in a way that minimises environmental cost.

When it comes to embodied emissions, the people who can effect the most change are ones making decisions about how the facility is built.
Some things to consider are:

- Using refurbished hardware or hardware made with recycled materials to avoid emissions associated with mining. Note that mining is also very polluting and harmful to the people living near mining sites, predominantly in the Global South.
- Building HPC facilities in areas that have plentiful clean and/or renewable energy and that require as little cooling (or in rare cases heating) as possible.
- Keeping hardware in use for as long as they are functional and repairing instead of replacing them.

In terms of operational emissions, you can:

- Educate researchers about what applications would benefit from the use of HPC and for which it is not necessary.
- Signpost researchers to training on how to make their code efficient.
- Advocate for your facility to get the [Green DiSC certification](https://www.software.ac.uk/GreenDiSC).

The content presented in this section was inspired by the [Digital Research Sustainability lesson](https://imperialcollegelondon.github.io/digital_research_sustainability_training/index.html) created at Imperial College London and the [Green Software Use on HPC lesson](https://epcced.github.io/2026-10-02_green-hpc_cambridge/instructor/index.html) created at EPCC.
