# Workflows for Programmatically Accessing, Processing, and Visualizing USGS 3DEP Data

## Background
The 3D Elevation Program (3DEP), managed by the U.S. Geological Survey (USGS), is acquiring quality level 2 or better light detecting and ranging (lidar) data over the conterminous United States, Hawaii, and US Territories to meet the growing need for high-resolution 3-D representations of Earth's surface, vegetation, and other constructed features. Since its operational start in 2015, over 1800 3DEP projects have been acquired, amounting to > 42 trillion lidar points covering an area > 6.5 million sq. km. The resulting data are publicly and freely available in Entwine Point Tile (EPT) format hosted in Amazon Web Services (AWS) S3 bucket. While the volume of available 3DEP lidar data is substantial, documented workflows and best practices for most effectively utilizing these cloud-hosted resources are underdeveloped. <a href="https://opentopography.org/">OpenTopography</a>, supported by the USGS <a href="https://www.usgs.gov/centers/community-for-data-integration-cdi">Community for Data Integration (CDI)</a>, is developing well-documented and customizable Jupyter Notebook-based Python workflows for programmatically accessing, processing, and visualizing 3DEP data products for a variety of use-cases geared toward USGS applications and for users of point cloud data across the geospatial community. 

## Contents
This repository contains a suite of Python workflows for programmatically accessing, processing, and visualizing U.S. Geological Survey (USGS) 3D Elevation Program (3DEP) lidar point cloud data and creating derivative products (DEMs, topographic difference maps, colorized point clouds, etc.). The workflows are in Jupyter Notebook format, with each notebook documenting a standalone workflow designed for a specific use-case. This suite of Jupyter Notebooks were developed in collaboration with and funded by the USGS Community for Data Integration (CDI (URL)), and as a result several of the notebooks provide workflows designed to address specific needs of the USGS. However, these workflows are designed for general users of topographic datasets and for those who may not have extensive experience. Each notebook will run with no additional user modification, but can be customized for specific use-cases and based on the user's. Please direct questions, comments, or suggestion related to these workflows to Cole Speed (<cole.speed@beg.utexas.edu>). 

## Dependencies and Depolyment
Two options exist for accessing and using these notebooks. (1) Install the required Python dependencies, clone, and execute the notebooks locally; or (2) Execute the notebooks on <a href="https://colab.research.google.com/">Google Collaboratory</a>, Google's cloud platform (Requires Google account with Google Drive access).

**Dependencies**
* PDAL
* GDAL
* Geopandas
* Ipyleaflet
* Matplotlib
* python-pdal
* Requests
* GDAL
* Pyproj
* nb_conda

**Option 1: Local Installation and Execution**
If you would like to run the Jupyter Notebook on your local machine, execute the following commands in your terminal or commandline (does not vary between MacOS, Linux, or Windows):

Make a new directory where the 3DEP Jupyter Notebooks (and all 3DEP data, if desired) will be saved. Change into directory and clone this Github repository to your local file system.
	
	$ mkdir 3DEP 
	$ cd 3DEP
	$ git clone https://github.com/cmspeed/OT_3DEP_Workflows

It is suggested to use Anaconda. Anaconda installers for MacOS/Linux/Windows can be downloaded from https://docs.anaconda.com/anaconda/install/. Follow the instructions to install the appropriate version of Anaconda.

After installing Anaconda, create a conda virtual environment with the required dependencies (contained in `environement.yml`). Note exectuting the following command will automatically create the conda environement with name `3dep`. If you would prefer a different name, replace `3dep` to another name in the following command:

	$ conda env create -n 3dep --file environment.yml

Activate the conda environment with all of the necessary dependencies installed. 
	
	$ conda activate 3dep

Now, launch the chosen Jupyter Notebook. If unsure how to launch a Notebook, refer to this guide (https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html). 

**Option 2: Google Collaboratory Installation and Execution**
Click the [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)] badge beneath the Jupyter notebook you would like to use. All of the required dependencies will be installed within a Google Colab runtime within the notebook. 

## USGS 3DEP Jupyter Notebooks

1. [Programmatic USGS 3DEP point cloud access, processing, and DTM/DSM creation/visualization for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_pointcloud_access_processing_DTM_creation.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_pointcloud_access_processing_DTM_creation.ipynb)<br/>

2. [Programmatic USGS 3DEP point cloud access, processing, and DTM/DSM creation/visualization for USGS 7.5' Quadrangles](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Programmatically_accessing_3DEP_data_using_USGS_7.5_Quadrangles.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Programmatically_accessing_3DEP_data_using_USGS_7.5_Quadrangles.ipynb)

3. [Programmatic USGS 3DEP point cloud access, processing, and DTM/DSM creation/visualization for USGS Watersheds (12- and 14-digit HUCs)]()

4. [Build a Canopy Height Model with USGS 3DEP data for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Making_a_Canopy_Height_Model_Using_USGS_3DEP_Data.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Making_a_Canopy_Height_Model_Using_USGS_3DEP_Data.ipynb)

5. [Topographic differencing with USGS 3DEP data for user-defined AOI]()
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()

6. [Colorize USGS 3DEP point cloud data with NAIP imagery]()
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()
