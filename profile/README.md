# Introduction to the Cellular-Nanoscience-Group GitHub Organisation
#### Hi everybody 👋
Welcome to the Cellular-Nanoscience-Group GitHub organisation! 
<br>This is where we collaborate on code, data analysis, and other computational tools for our various research projects and setups.
The purpose of this platform is to transform our current code chaos into a structured form with better version control, 
so please take a minute to familiarise yourself with GitHub and try your best to keep order in the individual repositories.
<br><br>Here's a first little tip: For every little difficulty in using GitHub, ChatGPT is always ready to guide you through it step by step :)
<br><br>This document explains the basic structure and functions of our organisation and the rules to ensure smooth collaboration. 

---

## Organisation structure 
Each setup has its own repository: 
- **Shenlong** 
- **Gleipnir** 
- **ASWAD** 
- **Skadi**
- **Aalo**

In addition, the repository **General** is intended for all scripts or data analysis-related files used across different setups (for example, PyOTic for all optical tweezers)
or that would be useful for other lab members independent of their project (feel free to share your ideas!).
<br>**.github** is a special repository immediately visible to all members of the GitHub organisation. It will contain information on how to use this platform.
<br>In general, everybody here has at least write permission, so you can not only download or update code but also adjust/optimise the structure of repositories and folders over time.

## Repository structure (suggestion)
A first approach for the folder structure of a repo would be:
- **README.md**: Repository-specific guidelines, setup instructions, and more.
- **`/cfg/`:** Configuration files for the individual setups.
- **`/src/`:** Source code folder, organised by programming languages or applications (e.g., `/src/python/`, `/src/matlab/`, `/src/r/`, `/src/imagej/`).
  <br>Each of these folders could contain:
  - **`/<project-related-subfolder>/`:** Collection of scripts, package, documentation...
  - **`/sample_data/`:** Sample data for any scripts if helpful?
  - ...
- ...

This is just a suggestion — feel free to set it up according to your needs. 

---
## Guidelines for contributing
### General Rules
1. **Version Control**: The main purpose of using Git is version control and collaboration, so make sure to upload your scripts and push changes regularly.
2. **Main Branch**: Always keep the `main` branch stable. Only tested and stable code should be pushed here.
3. **Branching**: For new features or fixes, always create a new branch. Use descriptive names, e.g., `feature-optical-tweezers-signal-filtering` or `fix-mass-photometry-calibration`.
4. **Forking**: Fork a repository if you're experimenting with scripts or doing extensive changes for yourself that won’t directly merge into the main repo because they are not relevant for everyone.
5. **Commits**: Write clear commit messages describing your changes, e.g., `Added new script for saving analysed RIOs as hdf5` or `Fixed bug in optical tweezers height calibration script`.
6. **Pull Requests**: Before merging changes into the `main` branch, open a Pull Request. Team members will review and approve it.


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
