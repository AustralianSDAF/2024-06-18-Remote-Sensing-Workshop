---
layout: page
title: Getting your computer ready for the workshop.
root: ..
---
---




# Preamble <a name="preamble"></a>

This workshop requires several pieces of software to be set up on your computer to participate.  
The workshop organisers do however note that due to institutional limitations, this may not be possible on your machine due to a lack of adminstrative permissions.  
We therefore present you with a preferred local installation method, and a web-based method that only requires a Google account. Please attempt the local setup, but if you are unable to complete it, please complete the online setup.  
  
If you run into issues, please email the organisers (contact link on main workshop page) for assistance. 

There will also be an additional 30 minutes before the workshop where we will be able to help with installation issues. If you need additional help, please come early!

---


# Table of Contents
1. [Preamble](#preamble)
2. [Local Setup](#local-setup)
3. [Online Setup](#online-setup)

---

# Local Installation Overview <a name="local-setup"></a>
This workshop will be run using Python [jupyter notebooks](https://jupyter.org/). For simplicity, we will run these using [Visual Studio Code ("VSCode")](https://code.visualstudio.com/) (not to be confused with Visual Studio).  

The steps will be:
1. Download and install VSCode.
2. Download workshop material.
3. Set up the environment using conda.
4. Link VSCode with the environment.

## Requirements
The requirements to set up a local installation are:
1. Adminstrative access to your machine, or **VSCode** and **miniforge** already having been installed.
2. Atleast a gigabyte of free space. It would be prudent to have at least 10GB of free space for data downloaded during the workshop.



## Download and Initial Setup

1. Download the VSCode installer from the [website](https://code.visualstudio.com/).

2. Run the installer with default settings. 

3. Once installed, launch VSCode, and click on the "Extensions" button on the left hand side, which looks like a few blocks (leave your mouse stationary over an icon for a second for its name to pop up.).

4. Search for the following extensions and install each of them. The author of the packages will be listed alongside the name. To install a package, after searching for it, click the name, then click the "install" button and it will begin installing.  The packages to install are:
  - Python - "Microsoft"
  - Jupyter - "Microsoft"

## Environment Setup
When creating software to process data or writing code in general, it's a good idea to make what you do reproducible. This makes it so if you need to run your code in 6 months, a year, or even further down the line, everything still works. For example, if you originally installed version 3.5 of a library when processing data, but 6 months later one of the libraries introduced a breaking change, without a record of which versions of which libraries you were using, it will take a lot of work to get your code working again. Even subtler changes in libraries can simply make the *output* change, without much indication. 

For these reasons, we have created an **environment** for this workshop - a set of software including python and any libraries you used all held at specific versions to ensure compatibility. This is recorded in an **environment file**.   

You will need to install the environment described by the environment file using the a piece of software called "conda" (from "Anaconda").

1. Download the files for this workshop as a .zip file the [github repository](https://github.com/AustralianSDAF/ASDAF_Workshop_Materials_Remote_Sensing_Intro). To do this, click the green "<> Code" icon in the top-right, and click "download ZIP" in the dropdown menu.
 Save this to a location that makes sense to you, such as your documents folder or your desktop. Try not to save this to a locally mounted OneDrive, as that can cause issues later. Extract the .zip folder downloaded into a regular folder (right click>extract to).

2. Download the Miniforge3 installer. This means for windows you should download [this file](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Windows-x86_64.exe). For Mac or linux, download the installer that matches your architecture (x86_64 vs arm64) from [its github repository](https://github.com/conda-forge/miniforge).

3. Run the installer with default settings.

4. Open the start menu. Search for and launch "Anaconda Prompt (miniconda3)".

5. In the command prompt that opens, navigate to the workshop materials folder you downloaded earlier using the "Change directory" command "cd". E.g if you saved it in your documents, run: 
  ```sh
  cd C:/Users/<your username>/Documents
  ```
6. In the command prompt, run:
```sh
conda config --set channel_priority strict
conda env create --file environment.yml
```

7. To activate the enviornment, run:
```
conda activate asdaf-workshop
```

Your environment should now be installed.

## Enabling enviornment in VSCode
Now that you have your environment, we need to set it up in VSCode.

1. Exit VSCode if it's open, then Launch VSCode

2. Click "Open File" and navigate to the workshop materials you downloaded earlier (e.g. In your Documents), then click "Open").

3. You should see several folders and files in the sidebar, including "notebooks". Click on the "notebooks folder" to expand the contents, and then double-click on "00 - Testing Notebook.ipynb"

4. Run the first cell. You should get ouput like below, listing the package names and versions.

If you see that, you're all set up!


---

# Online Setup <a name="online-setup"></a>

## Introduction
If you have difficulty setting up the local installation, you should be able to use [Google Colab](https://colab.google/) for the workshop. 

## Requirements
Google Colab provides free access to CPU's to use with a notebook, but does require a Google account and sufficient storage. This shouldnt be a problem unless you've already stored a lot of data on your Google Drive. In this case, please backup these files appropriatly and make at least 10GB, preferably 20GB of space.

## Setup steps
 
1. Create or log in to your Google account in a web browser at [google.com](https://google.com) (click the "sign-in" button in the top-right).

2. Go to [colab.google](collab.google)

3. Accept the terms and test that you can make an empty colab notebook by clicking on the "New notebook" button.

4. Go to the [Workshop Materials Page](https://github.com/AustralianSDAF/ASDAF_Workshop_Materials_Remote_Sensing_Intro) and scroll down to the README. Click on "00_Testing Notebook_colab.ipynb"

5. Read through and follow the instructions in the notebook. In particular, run the cell that includes:
  ```py
  from google.colab import drive
  drive.mount('/content/drive')
  ```
  and follow the promps in the window that pops up. Make sure "See, edit, create and delete any of your Google Drive documents" is ticked.   
  This will let you access your Google Drive in the notebook.

6. If everything in the 00_testing notebook works without issue, congradulations you're set up! 🎉 

7. During the workshops, you will need to open notebooks from the links at the [Workshop Materials Page](https://github.com/AustralianSDAF/ASDAF_Workshop_Materials_Remote_Sensing_Intro). You will also need to mount your Google Drive each time you open a new notebook, and access your ensure your data paths start with `'/content/drive/(other folder as applicable)'`. Make sure not to run the cell that says "Do not run if you are using collab", or you will need to re-run a cell at the start to re-define that variable. Help on this will be available in the workshop.


