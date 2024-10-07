==============================================================================
Integrated Hydrological Modeling Practices and Uncertainty Analysis Curriculum
==============================================================================

| Seonggyu Park
| Texas A&M AgriLife Research
| July 24-26, 2024


Overview
========
This workshop aims to provide a better understanding of the principles of hydrologic cycle and water budgets and to teach the fundamental principle and structure of a widely used integrated hydrologic model, SWAT-MODFLOW, with hands-on exercises for use in assessing spatio-temporal patterns of water resources and fluxes. It will also cover general procedures of model development, implementation, evaluation, and optimization.

Course Objectives
=================
Upon successful completion of this workshop, students will be able to (1) understand the fundamental principles of each model (SWAT, MODFLOW, and SWAT-MODFLOW); (2) construct a SWAT-MODFLOW model; (3) perform a simulation with various configurations; (4) evaluate and visualize simulation results; and (5) perform model optimization. Students will learn to work with a graphical user interface, QSWATMOD, and an automatic optimization framework with Jupyter notebooks.

Course Preparation
==================
Please bring a laptop running Windows OS (higher than Windows 10, preferably) to use for the workshop exercises. You will be contacted by the instructor with files to download prior to the course.

* Pre-requisites (nice to have; not required):
  * Basic understanding of Python
  * Basic understanding of Jupyter Notebook 
  * Basic understanding of SWAT and MODFLOW

* Introductions:
  * The mathematics and theory
  * Learning by doing
  * Please speak up! Everyone learns from discussion
  * Work in pairs
  * Python, GUIs, and all that

Session content and schedule
============================
* Day 1 - First Session – Integrated hydrologic model
  * Introduction to Hydrogeology
  * Hydrologic cycle and water budgets
  * Introduction to SWAT-MODFLOW-RT3D
    * Background & Case studies
    * SWAT
    * MODFLOW & RT3D
    * SWAT-MODFLOW-RT3D linking process 
  * Setting up simulation
    * Set up, run, view 
  * QGIS & QSWAT & QSWATMOD installations (if necessary)
  * Q&A session
* Day 2 - Second Session – QSWAT and QSWATMOD
  * Create SWAT model with QSWAT
  * Exercise with QSWATMOD (5 hours)
    - Description of QSWATMOD
    - Create a MODFLOW model
    - Create an RT3D model
  - Link 3 different models
  - Set up the configuration of the model simulation and run the model
  - Visualize and analyze hydrology outputs
  - Visualize and analyze water quality outputs
  - SWAT-MODFLOW scenarios and additional QSWATMOD functions
    - Irrigation pumping
  - SWAT-MODFLOW model evaluation
  - Q&A Session (30 mins)
- Day 3 - Third Session - Optimization Framework
  - Anaconda & swatmf python package Installations
  - Introduction to Jupyter notebook and Python language (skipped if not necessary)
  - Introduction to Uncertainty analysis (Bayes’ theorem) and Parameter ESTimation utility (PEST)
  - Construct PEST interface
    - pre-processing (template files)
    - post-processing (instruction files)
    - control file
- Run PEST & parallel processing
- Analyze results
- Q&A Session







swatmf
======

.. image:: https://img.shields.io/pypi/v/swatmf?color=blue
   :target: https://pypi.python.org/pypi/swatmf
   :alt: PyPI Version
.. image:: https://img.shields.io/pypi/l/swatmf
   :target: https://opensource.org/licenses/BSD-3-Clause
   :alt: PyPI - License
.. image:: https://zenodo.org/badge/304147230.svg
   :target: https://zenodo.org/badge/latestdoi/304147230



`swatmf` is a set of python modules for SWAT-MODFLOW model (Bailey et al., 2016) parameter estimation and uncertainty analysis with the open-source suite PEST (Doherty 2010a and 2010b, and Doherty and other, 2010).

Uncertainty Analysis for SWAT-MODFLOW model
===========================================


Get data and jupyter notebooks
------------------------------

You essentially have 2 options:

Easy way
--------

- `Download the data zip file <https://github.com/spark-brc/swatmf_wf/archive/refs/heads/main.zip>`_
- Unzip `swatmf_tut-main.zip` to a prefered location.


Hard way (Dev mode)
-------------------

- You will need to install Git if you don't have it installed already. Downloads are available at [the link](https://git-scm.com/download). On windows, be sure to select the option that installs command-line tools  
- For Git, you will need to set up SSH keys to work with Github. To do so:
    - Go to GitHub.com and set up an account
    - On Windows, open Git Bash (on Mac/Linux, just open a terminal) and set up ssh keys if you haven't already. To do this, simply type ssh-keygen in git bash/terminal and accept all defaults (important note - when prompted for an optional passphrase, just hit return.)  
- Follow the `instructions <https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/>`_ to set up the SSH keys with your GitHub account.
- Clone the materials from GitHub.
    - Open a git bash shell from the start menu (or, on a Mac/Linux, open a terminal)
    - Navigate to the folder you made to put the course materials
    - Clone the materials by executing the following in the git bash or terminal window:


.. code-block:: bash

   git clone https://github.com/spark-brc/swatmf_wf.git


Installation
============

To execute jupyter notebook, we need the Miniconda environment.

1. Miniconda Python:
--------------------

- If you don't already have conda installed, please download Miniconda for your operating system from https://conda.io/en/latest/miniconda.html (choose the latest version for your operating system, 64-bit). You should not need elevated rights to install this.
- Run the installer and select "only my user" when prompted. This will allow you to work with your python installation directly.

2. Set Environment and install libraries:
-----------------------------------------

- After installation, go to the START menu and select "Miniconda Prompt" to open a DOS box.
- Using the `cd <https://www.computerhope.com/issues/chusedos.htm>`_ command in the Miniconda DOS box, navigate to the location where you have `environment.yml` the file and type: 

.. code-block:: bash

   conda env create -f environment.yml

and hit ENTER.

After your virtual environment setup is complete, change the environment to `swatmf_wf`:  

.. code-block:: bash

   conda activate swatmf_wf

- Launch jupyter notebook 

.. code-block:: bash

   jupyter notebook


A browser window with a Jupyter notebook instance should open. Yay!


.. rubric:: Brief overview of the API

.. code-block:: python

   from swatmf import swatmf_pst_utils

   >>> prj_dir = "project directory"
   >>> swatmfwd = "SWAT-MODFLOW model"
   >>> swatwd = "SWAT model"
   >>> swatmf_pst_utils.init_setup(prj_dir, swatmfwd, swatwd))

   Creating 'backup' folder ... passed
   'Absolute_SWAT_Values.txt' file copied ... passed
   'pestpp-glm' file copied ... passed
   'pestpp-ies.exe' file copied ... passed
   'pestpp-ies.exe' file copied ... passed
   'forward_run.py' file copied ... passed

