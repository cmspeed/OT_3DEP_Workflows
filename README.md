# Workflows for Programmatically Accessing, Processing, and Visualizing USGS 3DEP Data

![workflow_examples](docs/imgs/examples.png)

## Background
The 3D Elevation Program (3DEP), managed by the U.S. Geological Survey (USGS), is acquiring high-quality light detecting and ranging (lidar) data over the conterminous United States, Hawaii, and US Territories to meet the growing need for high-resolution 3-D representations of Earth's surface, vegetation, and other constructed features. To date, over 1800 unique 3DEP projects have been acquired, amounting to more than 42 trillion lidar points covering an area greater than 6.5 million sq. km. The resulting data are publicly and freely available in Entwine Point Tile (EPT) format hosted in an Amazon Web Services (AWS) S3 bucket. While the volume of available 3DEP lidar data is substantial, documented workflows and best practices for most effectively utilizing these cloud-hosted resources are underdeveloped. <a href="https://opentopography.org/">OpenTopography</a>, supported by the USGS <a href="https://www.usgs.gov/centers/community-for-data-integration-cdi">Community for Data Integration (CDI)</a>, is developing well-documented and customizable Jupyter Notebook-based Python workflows for programmatically accessing, processing, and visualizing 3DEP data products for a variety of use-cases geared toward USGS applications and for users of point cloud data across the geospatial community. 

## Contents
This repository contains a suite of Python workflows for programmatically accessing, processing, and visualizing U.S. Geological Survey (USGS) 3D Elevation Program (3DEP) lidar point cloud data and creating derivative products (DEMs, topographic difference maps, colorized point clouds, etc.). The workflows are in Jupyter Notebook format, with each notebook documenting a standalone workflow designed for a specific use-case. This suite of Jupyter Notebooks was developed in collaboration with USGS and funded by a USGS Community for Data Integration(CDI) grant awarded up for the project <a href="https://www.usgs.gov/centers/community-for-data-integration-cdi/science/enhancing-usability-3dep-data-and-web-services"> *"Enhancing usability of 3DEP data and web services with Jupyter notebooks"*</a>. Therefore, several of the notebooks provide workflows designed to address specific needs of the USGS. However, these workflows are designed for any users interested in using 3DEP lidar datasets and for those who may not have extensive experience. Each notebook will run with no additional user modification, but can be customized for specific use-cases and based on the user's. Please direct questions, comments, or suggestion related to these workflows to Cole Speed (<cole.speed@beg.utexas.edu>). 

## Dependencies and Installation
Two options exist for accessing and using these notebooks. (1) Install the required Python dependencies, clone, and execute the notebooks locally; or (2) Execute the notebooks on <a href="https://colab.research.google.com/">Google Collaboratory</a>, Google's cloud platform (Requires Google account with Google Drive access).

**Dependencies**
* PDAL
* GDAL
* Geopandas
* Ipyleaflet
* Matplotlib
* python-pdal
* Requests
* Pyproj
* nb_conda

**Option 1 (Suggested): Google Collaboratory Installation and Execution**

For ease-of-use, it is suggested to launch and execute these notebooks on Google Collaboratory (Colab, for short), Google's Cloud Platform. Dependencies will be installed on a virtual machine on Google's cloud servers and the code will be executed directly in your browser! A major benefit of this is that you will have direct access to Google high-end CPU/GPUs and will not have to install any dependencies locally. All deliverables will be saved to your personal Google Drive.

To experiment and run one of the below Jupyter Notebooks on Google Colab click the [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)] badge beneath the corresponding Jupyter notebook. 

**Option 2: Local Installation and Execution**

If you would like to run the Jupyter Notebook on your local machine, follow these steps:

Make a new directory where the 3DEP Jupyter Notebooks (and all 3DEP data, if desired) will be saved. In this case, the directory will be called `3DEP`. Change into the new directory and git clone the Github repository containing the Jupyter Notebooks and other relevant files to your local file system.

```bash
mkdir 3DEP
cd 3DEP
git clone https://github.com/cmspeed/OT_3DEP_Workflows
```

Anaconda is recommended for Python package installation and management. Package versions in Anaconda are managed by the package management system *conda*. Anaconda installers for MacOS/Linux/Windows can be downloaded from https://docs.anaconda.com/anaconda/install/. Follow the instructions to install the appropriate version of Anaconda.

After installing Anaconda, create a conda virtual environment with the required dependencies (contained in `environement.yml`). Note: Exectuting the following command will automatically create the conda environement with name `3dep` and all of the required dependencies installed. If you would prefer a different name, replace `3dep` with another name in the following command:

```bash
conda env create -n 3dep --file environment.yml
```

Activate the conda environment with all of the necessary dependencies installed. 

```bash
conda activate 3dep
```

Now, launch the chosen Jupyter Notebook. If unsure how to launch a Notebook, refer to this guide (https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html). 

## USGS 3DEP Jupyter Notebooks

1. [Accessing, processing, and visualizing 3DEP lidar point cloud data and derivative products for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_pointcloud_access_processing_DTM_creation.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_pointcloud_access_processing_DTM_creation.ipynb)<br/>

2. [Accessing, processing, and visualizing 3DEP lidar point cloud data and derivative products for USGS 7.5' Quadrangles](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Programmatically_accessing_3DEP_data_using_USGS_7.5_Quadrangles.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Programmatically_accessing_3DEP_data_using_USGS_7.5_Quadrangles.ipynb)

3. [Accessing, processing and visualizing 3DEP point cloud data and derivative products for USGS 12- and 14-digit Hydrologic Unit Code (HUC) Boundaries](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_data_for_watershedboundaries.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/3DEP_data_for_watershedboundaries.ipynb)

4. [Making canopy height models (CHMs) with 3DEP point cloud data and derivative products for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Making_a_Canopy_Height_Model_Using_USGS_3DEP_Data.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Making_a_Canopy_Height_Model_Using_USGS_3DEP_Data.ipynb)

5. [Topographic differencing with 3DEP point cloud data and derivative products for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Topographic_differencing_3DEP_and_OT_lidar_data.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/Topographic_differencing_3DEP_and_OT_lidar_data.ipynb)

6. [Colorizing 3DEP point cloud data with 1m NAIP imagery for user-defined AOI](https://github.com/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/colorizePC.ipynb)<br/>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cmspeed/OT_3DEP_Workflows/blob/main/notebooks/colorizePC.ipynb)

## References

[![NSF-1948997](https://img.shields.io/badge/NSF-1948997-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948997) 
[![NSF-1948994](https://img.shields.io/badge/NSF-1948994-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948994)
[![NSF-1948857](https://img.shields.io/badge/NSF-1948857-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1948857)
