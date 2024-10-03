---
title: "Google Summer of Code 2024 Final Report"
date: 2024-10-02
draft: false
tags:
  - GSoC
  - Synfig
  - Open Source
  - University
  - DevOps
  - Automation
  - C++
  - GitHub Actions
  - Linux
  - AppImage
  - Bash
image: /images/gsoc-2024-final-report/intro.png
description: ""
toc:
---

This report outlines my work and learning experiences during Google Summer of Code 2024 with Synfig. Over the course of more than four months, I contributed to Synfig, a powerful open-source 2D animation software, starting from the application phase in March to April through the main project period from July to October.<br>
I worked using C++, Bash scripting, DevOps, GitHub Actions, Linux, AppImage, and Virtual Machines.

## Glossary

- **Release Notes** A summary that is uploaded when a new update of a software is launched, this summary includes new features, bug fixes, etc.
- **AppImage** A technology that allows Linux applications to be packaged into a single file, similar to a Windows .exe, making it easy for users to run the application without installation. Software engineers can create these single files with scripts, allowing the application to be easily distributed on Linux and run by simply double-clicking.
- **Contributors and Pull Requests** A contributor is a software engineer who works on open-source projects by making improvements or adding features. They submit these changes to the project's codebase by creating a pull request, which describes the changes made, and why they are beneficial.

## Project Goals
This summer I worked on 2 projects, I will state their goals below.

### Automating Release Notes Generation

1. Free up software engineers' valuable time by removing the burden of modifying release notes manually by creating a software that automatically generates release notes.
2. Improve the looks and structure of the release notes to help Synfig users better understand the changes made.
3. Enhance the pull requests and release notes' descriptions by automatically showing contributors how their pull requests will affect the release notes.

### Simplifying Linux Download Experience
1. Currently, Synfig is bundled to work on Linux using AppImage v1.0 **complicated** scripts. AppImage v1.0 is outdated and has the critical issue that it doesn't work smoothly on newer systems (Ubuntu v22.04 and others); the AppImage scripts will be updated to use the latest AppImage version to run smoothly on old as well as newer Linux distributions.

## What Was Done
1. Created a detailed technical [<font color="007bff">proposal</font>](https://drive.google.com/file/d/18hf-o3tthEjumvrjy0H9CNSoODKcc1n5/view) that got me accepted into Google Summer of Code with Synfig.
2. Automated the generation of release notes when a new GitHub release is created, eliminating manual effort for
release notes creation by creating the [<font color="007bff">Release Notes Manager</font>](https://github.com/Ahmed-Khaled-dev/release-notes-manager) using C++, GitHub Actions, Git, and GitHub API.
3. Significantly improved the looks and structure of the release notes which will help Synfig users better understand the changes made.
4. Transferred the release notes to the GitHub releases' descriptions, increasing their visibility and professionalism.

Example of automatically generated release notes from git commit messages.

![Automatically Generated Release Notes](/images/gsoc-2024-final-report/release_notes.png)

5. Automated showing contributors how their pull requests will affect the release notes, this aims to enhance the
pull requests and release notes descriptions and give Synfig’s pull requests a more professional feel to attract
more contributors.

![Demo Pull Request](/images/gsoc-2024-final-report/demo_pr.png)

![Showing contributors how their pull requests will affect the release notes](/images/gsoc-2024-final-report/github_bot_comment_on_new_pr.png)

6. Integrated the above features into Synfig by creating 2 pull requests that are still under review, [<font color="007bff">PR1</font>](https://github.com/synfig/synfig/pull/3392), and [<font color="007bff">PR2</font>](https://github.com/synfig/synfig/pull/3393).
7. Improved accessibility for users by making Synfig easy to use on any Linux distribution by packaging it into the latest
AppImage using simple and easy to understand [<font color="007bff">bash scripts</font>](https://github.com/Ahmed-Khaled-dev/synfig-appimage) and testing it on 6 Linux distributions.

Synfig on Debian 10            |  Synfig on Pop!_OS 22.04            | Synfig on Fedora 40            
:-------------------------:|:-------------------------:|:-------------------------:
![Synfig working on Debian 10](/images/gsoc-2024-final-report/synfig_on_debian_10.png)  |  ![Synfig Working on Pop OS](/images/gsoc-2024-final-report/synfig_on_popos.png) | ![Synfig working on Fedora 40](/images/gsoc-2024-final-report/synfig_on_fedora.png)

8. Ensured code quality, maintainability, and clear communication by adding Unit tests (doctest), detailed Code
documentation (doxygen) and sending [<font color="007bff">weekly status updates</font>](https://github.com/synfig/synfig/issues/3377).

## What's Left to Be Done
1. Thoroughly test the generated 64-bit AppImage to confirm it functions correctly on all targeted Linux distros.
2. Automate the generation of the AppImage based on a trigger, e.g. when a new GitHub release is created.

## Optional Enhancements for the Future
1. Test and confirm the ability of the AppImage script to generate AppImages that run on 32-bit systems.
2. Fix the formatting issues with bullet points, numbered lists, and to-dos in the generated release notes.
3. Add the ability to customize the messages the GitHub bot sends to show contributors how their pull requests will affect the release notes.
4. Address the limitation of generating complete release notes for the first release in a new repository, as the first commit is excluded.
5. Add the ability to customize the looks of the generated release notes.
6. Make the [<font color="007bff">Release Notes Manager</font>](https://github.com/Ahmed-Khaled-dev/release-notes-manager) a GitHub Action in the GitHub Actions marketplace.
7. Improve the structure of the Release Notes Manager code into folders.
8. Refactor my code to improve its readability and maintainability, making it easier for future contributors to navigate and build upon.
9. Create scripts to package Synfig as Debian and Flatpak packages, providing Linux users with more options beyond AppImages.
10. Work on the extra ideas in my [<font color="007bff">proposal</font>](https://drive.google.com/file/d/18hf-o3tthEjumvrjy0H9CNSoODKcc1n5/view).

## Important Things I Learnt
1. **Anything** that seems incredibly hard at first, given enough time and effort becomes extremely easy.
2. Stress comes from not taking action over things we should be doing, [<font color="007bff">great short video</font>](https://youtu.be/SQHmeRIhNtw) by Jeff Bezos.
3. First, try to solve problems independently; if a thorough attempt doesn't succeed, seek help.

Thank you for taking the time to read my Google Summer of Code report, if you have any questions or would like to chat, please feel free to [<font color="007bff">contact me</font>](https://ahmed.khaled.yousry.org/#contact)!