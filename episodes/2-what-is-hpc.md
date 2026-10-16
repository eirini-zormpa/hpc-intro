---
title: 'What is HPC?'
teaching: 40
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How does a basic HPC cluster work?
- What does an HPC cluster look like?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- List the components of a basic HPC system.

::::::::::::::::::::::::::::::::::::::::::::::::

<!-- 
The hardware that makes up the cluster. often dedicated to efficiently support different kinds of computing
all clusters need processors - there are different kinds of processors - traditionally CPUs which are very flexible etc but at a cost i.e. resource (space on the chip etc)
people looked at accelerators, e.g. GPU traditionally focused on graphics etc.
data centre GPUs don't even have the parts that would allow you to display stuff on screen

software
doing computation efficiently - tghtly coupled vs embarassingly parallel (most AI things)
-->

## HPC clusters 101
Now that we have a better idea of how HPC can be deployed to answer questions in different scientific fields, let's take a closer look at the software and hardware that make up a cluster.

The previous episode already established that HPC clusters are made up of computers, called nodes, which are connected through a network, typically a high-speed one.
Let's now dig into the different components of an HPC cluster and see how they work together.

HPC clusters will generally require the following basic components:

- interactive (or login) nodes, used to access the cluster
- compute nodes, used to run jobs
- storage, where data are stored
- a switch, which connects the login, compute, and storage nodes allowing them to act as a seamless unit. These are usually InfiniBand or other high-speed Ethernet to meet the low-latency, high-bandwidth requirements of HPC clusters.
- cables connecting the different nodes

Let's see how some of these components look like in our own mini HPC cluster:

![Anatomy of our mini HPC cluster.](files/cluster-infographic-small.png)

<!--
explain PoE HATs/CPU/RAM and perhaps how the power distribution unit fits in
-->

The components listed until now are all hardware.
A very important piece of software when working on an HPC cluster is the _job scheduler_.
A job scheduler is essential because the resources of an HPC cluster are finite and the demand on those resources is usually very high.
When submitting a job, users have to specify how many resources (RAM and CPUs or GPUs) they require and how long they expect their job to take.
The scheduler uses this information to prioritise jobs and make as efficient use of the resources as possible.
One of the most commonly used job schedulers is Slurm.
There will be more information on Slurm in the following episode.

<!-- add more information on filesystems and memory -->

## Different types of HPC

<!--material on HPC types: https://www.hpc-carpentry.org/hpc-python/06-parallel/index.html, https://train.rse.ox.ac.uk/material/HPCu/high_performance_computing/hpc_parallel_intro/01_introduction -->

We've talked about the different hardware components of an HPC cluster that determine the system's computing power, bandwidth and memory storage.
These can be configured in bespoke ways to suit the type of problem at hand.
For example, some problems require a lot of storage space but little CPU, while others may require the opposite.

### Embarassingly parallel

Some scientific problems require running the same programme multiple times, but with different parameters.
Each run of the programme is completely independent from the rest, i.e. its run does not rely on the outcome of any other run.
In this case, all runs can happen in parallel on separate CPUs and everything is combined at the very end.
This would be an example of an "embarassingly parallel" task.

This relates to the concept of *high-throughput computing*, which not only runs multiple jobs in parallel and independently, but does so on *ordinary computers*.
This means that the nodes used in these systems are not specialised, but very similar to what you would use in your own laptop.

For embarassingly parallel tasks, priority is on a large number of CPUs, with a high-speed low-latency interconnect being less important.

<!--
### Shared memory parallelism

A different kind of scientific question might rely on the analysis of very large datasets.
Here, CPUs are able to work on tasks independently, but they all need access to the same dataset.

For this kind of tasks, all CPUs need to be part of the same node and have access to the same RAM.
-->

### Tightly coupled parallelism

Sometimes, jobs can be parallelised to an extent but cannot be run completely independently of each other, but need to exchange information.
Generally this is the case because the different chunks of the task that needs to be completed can only be in a certain order.

In those cases, a high-speed low-latency interconnect is much more important compared to an embarassingly parallel task.

<!--

CPUs (flexible, resource-intensive) versus accelerators (do something repetitive very efficiently). e.g. for ML you need linear algebra where you need to do a lot of the same kind of calculation. These are simpler in some way because they are able to do fewer things but they are very efficient at doing the thing it was created to do.
    flexibility vs speed
-->


::::::::::::::::::::::::::::::::::::: challenge 

## Parallelisation scenarios

For each of the following cases, consider how independent the constituent tasks are:
- Number addition
- Search in a database
- Analysis pipeline: read in data, clean, and model it

:::::::::::::::::::::::: solution 

## Solution
 
- Completely independent, as numbers can be added in any order and the outcome is the same
- Fairly independent, but dependent on goal. If the goal is just finding a keyword, a database can be split into multiple chunks that can be searched independently.
- Each individual step may be parallelised, but the steps themselves need to happen sequentially

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## Visible HPC

A lot of the things we have been discussing can feel a bit abstract.
What does a node look like?
Where is a process happening?
How do these computers communicate to each other?

Below you can see a picture from the Slough Data Centre hosting Imperial's High Performance Computing facilities.

<!--

Photographer
Dave Guttridge

-->

![Imperial's HPC facilities.](files/230620_DG_ICL_Slough_Data-057.jpg){alt='Image of two people standing next to large servers.'}

<!--

Importance of visible HPC - the importance of the thing being there
this is representative of the real world
-->

For better or worse, it is quite rare for researchers and research supporters to visit these facilities and get first-hand experience of what this equipment looks like.

That's where mini HPC clusters like ours come in!
They provide an opportunity for a wider audience to interact with this kind of infrastructure.

Here is a picture of our own mini cluster.

![Mini cluster!](files/mini-cluster.jpg){alt='Image of a little cluster.'}

Clearly, these are very different beasts!
Our cluster is much smaller and, at least somewhat, portable.
However, the design of our cluster is realistic and can help build a visual connection to the real thing.
Let's look at how:

- the rack is 19 inches in width, which is the industry standard
- at only 12U, our cluster is rather short but stack four of them and you get a typical full size rack (48U)!

If we take a closer look at Imperial's HPC facilities, we again see nodes connected by cables!

![Detail of Imperial's HPC facilities.](files/230620_DG_ICL_Slough_Data-211.jpg){alt='Image of a close up of the cluster nodes.'}

This is all about how our cluster _looks_, but let's now talk about what is inside it.
The workhorse of our cluster are 36 Raspberry Pi 5 computers.
Thirty-two of them are used as compute nodes, one as the interactive login node and three as a distributed memory system.
Raspberry Pi computers are a convenient choice for this mini cluster because they are easily available, relatively inexpensive and have a suite of compatible hardware and software, due to their popularity.
The Pis are powered over Ethernet cables, which again are easy to obtain.
In many HPC systems, the nodes will be more high powered than a Raspberry Pi and the interconnects will be more specialised than an Ethernet cable.
In that sense, this system is more closely related to the high-throughput computing type of HPC, not using any specialised equipment.

This is not true of our network switch which is enterprise-level and very similar to what you would see in a real data centre.

::::::::::::::::::::::::::::::::::::: keypoints 

- HPC clusters typically consist of nodes, used for user login, computation and storage, and interconnects.
- Different types of research questions may be best tackled by different types of HPC, e.g. depending on how interdependent the calculations are and how much data there is.

::::::::::::::::::::::::::::::::::::::::::::::::

