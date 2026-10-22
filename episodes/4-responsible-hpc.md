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

these resources are free at the point of access but they do have significant costs

### The challenge

### Steps to mitigate impact

See: https://imperialcollegelondon.github.io/digital_research_sustainability_training/index.html
