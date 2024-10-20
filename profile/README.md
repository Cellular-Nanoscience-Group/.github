# Introduction to the Cellular-Nanoscience-Group GitHub Organisation
#### Hi everybody 👋
Welcome to the Cellular-Nanoscience-Group GitHub organisation! 
<br>This is where we collaborate on code, data analysis, and other computational tools for our various research projects and setups.
The purpose of this platform is to transform our current code chaos into a structured form with better version control, 
so please take a minute to familiarise yourself with GitHub and try your best to keep order in the individual repositories.
<p>As a first little hint: For every difficulty in using GitHub, ChatGPT is always ready to guide you through step by step :)
<p>This document explains the basic structure and functions of our organisation and the rules to ensure smooth collaboration. 
<br>First, you need to download and [install Git](https://git-scm.com/downloads) locally on your machine to sync your work with remote GitHub repositories.
<p>Additionally, if you haven't already done so, please create your own GitHub account [here](https://github.com/). You will then be invited to become a member of the organisation. This is the only way we can manage the onboarding and offboarding of individuals, the soon-to-be mandatory 2FA, as well as the security of all repositories and the Cellnano GitHub account. Thank you!

---

## Organisation structure 
Each setup has its own repository: 
- **Shenlong** 
- **Gleipnir** 
- **Aswad** 
- **Skadi**
- **Aalo**

In addition, the repository **General** is intended for all scripts or data analysis-related files used across different setups (for example, PyOTic for all optical tweezers) or that would be useful for other lab members independent of their project (feel free to share your ideas!).
<br>**.github** and **.github-private** are special repositories that create a landing page for the public and members of the GitHub organisation, respectively. Once you have signed up with your account, **.github-private** will provide you with further information on how to use this platform.
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
1. **Version Control**: The main purpose of using Git is version control, backups and collaboration, so make sure to upload your scripts and push changes regularly.
2. **Main Branch**: Always keep the `main` branch stable. Only tested and stable code should be pushed here.
3. **Branching**: For new features or fixes, always create a new branch. Use descriptive names, e.g., `feature-optical-tweezers-signal-filtering` or `fix-mass-photometry-calibration`.
4. **Forking**: Fork a repository if you are experimenting with scripts or making extensive changes for yourself that will not directly merge into the main repo because they are not relevant to everyone.
5. **Commits**: Write clear commit messages describing your changes, e.g., `Added new script for saving analysed RIOs as hdf5` or `Fixed bug in optical tweezers height calibration script`.
6. **Pull Requests**: Before merging changes into the `main` branch, open a Pull Request. Team members will review and approve it.

### Basic Git commands:
This is just a quick first guide. Detailed explanations and instructions will be provided in separate files in this repo (or, again, ask ChatGPT 😉).

- **Clone a repository**: Download a repository locally. You can do this directly from GitHub (as a ZIP file) or using any command line or terminal of your system (the command will be the same in all environments)
  ```
  cd C:/path/to/your/local/repository/copy/
  git clone https://github.com/username/repository.git
  ```
- Before making any changes, **pull the latest changes** from the remote GitHub repository. This ensures your local copy is up to date.
  ```
  cd C:/path/to/your/local/repository/copy/
  git pull origin main
  ```
  **main:** Refers to the stable main branch.
  <br>**origin:** Refers to the remote URL of the repository you cloned from (`origin` is a default alias that does NOT need to be changed to the actual repository  name).
  <br>To check what the current remote the `origin` alias is pointing to, use:
  ```
  git remote -v
  ```
  If you ever need to rename or change the remote, you can do so with:
  ```
  git remote rename origin newname
  ```
  If you need to update the remote URL, use:

  ```
  git remote set-url origin https://github.com/your-username/your-repo.git
  ```
- **Stage your changes:** Prepare changes to be included in the next commit and select which changes to commit if multiple files have been modified.
  ```
  cd C:/path/to/your/local/repository/copy/
  git add file.py
  ```
- **Commit your changes:** Save the staged changes without pushing them to the remote yet.
  ```
  git commit -m "Your commit message"
  ```
Careful. At this point, you must decide whether your changes should be merged with the main branch or in a separate branch or whether the code has been modified and tailored so specifically to your application that you might want to fork the repository. Read up on branching and forking.

- **Branching:** If you are working on a new feature that might be interesting to others, consider creating a new branch. The following shorthand command creates a new branch called new-feature-branch and immediately switches to it.

  ```
  git checkout -b new-feature-branch
  ```
  Afterwards, you can follow the same steps to push changes to the new branch. 
- **Forking:** Go to the original repository on GitHub and click the Fork button to create your own fork. This will create a copy of the original repository under your GitHub account. First, check your current remote setup with `git remote -v`.
  <br>Right now, your local clone is probably still linked to the original repository (not your new fork). You need to change the origin remote to point to your fork. You will see something like:
  ```
  origin  https://github.com/lauramuras99/DwellTimeAnalysis.git (fetch)
  origin  https://github.com/lauramuras99/DwellTimeAnalysis.git (push)
  ```
  To change the `origin` alias to point to your new fork, run:
  ```
  git remote set-url origin https://github.com/your-username/forked-repo.git
  ```
  and verify the change again with `git remote -v`.

- **Push your changes:** Upload those changes to the remote repository so others can access and collaborate on them.
  ```
  git push origin main
  ```
- After working on a fork for quite some time, you might want to cleanly integrate all updates from the main branch without overwriting your own work. This is achieved by **rebasing**.
  To rebase a forked repository onto the latest version of the main repository to integrate new changes while keeping your own modifications, run 
  ```
  git fetch origin
  git rebase origin/main
  ```
  
  ---

### Do I always have to update my code with all changes from the main branch?
No :) Git has a really nice cherry-picking feature that allows you to incorporate only specific commits from the updated main branch or even another fork without merging everything.
<br>Selective merging from the main branch without affecting other custom modifications:
```
git fetch origin
git cherry-pick <commit-hash>
  ```
  
