---
title: "Naming Files and Folders"
author: 'JA Moggridge'
date: "2022-07-31T17:36:54-07:00"
excerpt: If you're naming your files for your research work my_script.R or manuscript.docx or similar then we need to have the talk (about filenames).
subtitle: "Turn chaos to order across your work-space"
draft: no
series: null
tags: null
categories: null
layout: single
---

**If you're naming your files for your research work `my_script.R` or `manuscript.docx` or similar then we need to have *the talk* (about filenames).**

### Naming things is really hard

Using vague names creates a massive amount of completely unnecessary *cognitive load* for yourself and your collaborators. Assigning informative names to your projects, files, folders, and all other computational resources is a learned skill but focusing some effort here will often help lubricate your path to success. Developing and sticking to a systematic way of naming files can be difficult, so this post tries to outline a set of basic principles for naming things. It's not perfect, but we have to start somewhere.

### One goal

**Make it easy for anyone to figure out what is going on with your files.**

<div style="padding-top:56.250%;position:relative;"><iframe src="https://gifer.com/embed/3fkt" width="100%" height="100%" style='position:absolute;top:0;left:0;' frameBorder="0" allowFullScreen></iframe></div>


### Admit there's a problem

First, let's pretend we created something and we want to close the document and still be able to find it later. We need to come up with a name memorable enough that we'll recall 'what that file was for' in the days, weeks, months, or possibly years that we'll keep it hanging around. What do we call it?

Some of the most brutal names are the most generic terms: file, manuscript, text, results, report, temp *etc*... If we give it one of these names, it will be very difficult to keep track of that specific one amid a sea of files with similarly vague names from other forgotten projects. No one even wants to accept a file named like this when you share it; I don't want this on my computer.

Equally bad are the names assigned by random using some services. How do you propose to remember the website you need is hosted at *'purple-clover-unicorn-68at2.cloud_service.com'*, exactly? How is anyone else supposed to? A random name not optimal either.

The worst though, are the names that completely misrepresents the contents of their bearers. For example, I once worked on a web app that the maintainer had named *specific_framework app*. 'specific_framework' refers to a particular framework for apps that shall remain unnamed. However, the app in question used not just a different framework and had no <this_framework> code, but used an entirely different language than the one that supports specific_framework. Let me tell you, the mental friction I experienced dealing with that contradiction never subsided; every time I went to work on the app, I couldn't find it. My eyes would gloss right over it multiple times. Can you blame me? The name was the opposite of what the code did!

### Encode purpose into names

Information about the work should guide the naming for anything we might create. At a bare minimum, your names should be able to tell your future self or a collaboratorator what the contents are about. Here is a basic scheme: `<project>_<task>.xyz`

### Project-oriented workflow

I'm a huge fan of a project-oriented structure for files, mostly because this works well for coding and version control with `git`. I do think this mentality extends well to no-code projects too though. Basically, all your files for a given project are kept in the same folder and that folder is named after your project.

### Code-based projects

Some languages enforce file structure, but if you don't have that then you're going to have to develop your own way to organize and enforce it on yourself. Personally, I always use a project-based workflow with different subdirectories for inputs, outputs, and code. For example, this is the file-tree (created with the cli tool `tree`) of an Rproject that runs script, `Emailer.R` that sends an automated report when new data arrives in a cloud storage bucket.

Look at these beautiful names! I mean, sure they might not tell you everything about how the project works but I assure you their contents are related to their names, which are very informative. I am so very proud of these names.

    .
    ├── data
    │   └── db.rds
    ├── results
    │   ├── analyzer_gt_summary.rds
    │   ├── analyzer_gt_individual_summary.rds
    │   ├── analyzer_plot_summary.rds
    │   └── analyzer_plot_individuals.rds
    ├── R
    │   ├── Emailer.R
    │   ├── analyzer.R
    │   ├── controller.R
    │   ├── email.Rmd
    │   ├── monitor.R
    │   └── reporter.R
    ├── README.md
    ├── Emailer.log
    ├── Emailer.Rproj
    └── scheduler.R
