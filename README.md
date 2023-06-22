# ICEM 2023 workshop on Climate Services

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jfallon1997/ICEM-2023-ClimateServicesWorkshop/blob/main/ClimServ%20Intro.ipynb)

Instructions are currently a work in progress.

For more information on the workshop and related pages, visit [https://linktr.ee/ICEM23ClimateServices](https://linktr.ee/ICEM23ClimateServices)

## Using the notebook

*Please note, if the notebook has a window popup about a validation error warning, it is safe to ignore this and click continue anyway*.

### Recommended method

Use the interactive slides in the web browser (no additional setup required) [via mybinder.org](https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb) or [via Google collab](https://colab.research.google.com/github/jfallon1997/ICEM-2023-ClimateServicesWorkshop/blob/main/ClimServ%20Intro.ipynb)

Note: if using google collab, you will need to manually copy the
[datasets](https://github.com/jfallon1997/ICEM-2023-ClimateServicesWorkshop/tree/main/datasets)
folder from github, before running the notebook.

### Code snippets method

It is possible to view the notebook on github, or view the PDF version.

### Advanced method

*If you haven't yet run the [python setup](#python-setup) instructions, skip there first!*

With `python` setup with the correct packages installed, you are now ready to run the workshop notebook.

First, ensure that your python environment is activated:

```sh
# method 2 (using anaconda)
conda activate icem

# alternatively, method 3
# windows
.\icem/Scripts\activate
# mac/linux
source icem/bin/activate
```

Next, download the notebook if you haven't already. Either click the green "code" button above on github and download everything as a compressed zip file, or if you prefer you can clone the repo:

```sh
git clone https://github.com/jfallon1997/ICEM-2023-ClimateServicesWorkshop.git
cd ICEM-2023-ClimateServicesWorkshop
```

And finally, launch the notebook with:

```sh
jupyter notebook "ClimServ Intro.ipynb"
```

## Python setup

### Method 1: mybinder.org or Google collab

**recommended method (run via webapp, no installation required)**

Visit https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb or https://colab.research.google.com/github/jfallon1997/ICEM-2023-ClimateServicesWorkshop/blob/main/ClimServ%20Intro.ipynb

Note: if using google collab, you will need to manually copy the
[datasets](https://github.com/jfallon1997/ICEM-2023-ClimateServicesWorkshop/tree/main/datasets)
folder from github, before running the notebook.

### Method 2: using conda

**(only use this installation method if you are familiar with using conda)**

Ensure that you install the required packages with [conda](https://docs.conda.io/en/latest) or [mamba](https://mamba.readthedocs.io/en/latest/user_guide/mamba.html):

```sh
conda create -n icem
conda activate icem
conda install -c conda-forge jupyter pandas xarray rioxarray matplotlib rasterio
```

And in future access the packages using

```sh
conda activate icem
```

### Method 3: using pip

**(use this installation method if you are not familiar with using conda)**

Create a `python venv` (note that this will create a new directory `icem` where the `venv` is stored):

```sh
# windows
py -m venv icem
# mac/linux
python3 -m venv icem
```

Activate the new `venv` that you have created:

```sh
# windows
.\icem/Scripts\activate
# mac/linux
source icem/bin/activate
```

Lastly you need to install required packages:

```sh
# windows
py -m pip install jupyter pandas xarray rioxarray matplotlib rasterio

# mac/linux
python3 -m pip install jupyter pandas xarray rioxarray matplotlib rasterio
```

For more help on pip, see https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments

## Downloading Data

### Reanalysis via NASA POWER DAVe

NASA POWER DAVe can be accessed at https://power.larc.nasa.gov/beta/data-access-viewer

In the example notebook, data spanning *01/29/2022* to *01/28/2023* at *+039.48*, *-073.59* is saved in `netCDF4` format as `datasets/reanalysis/POWER_Point_Hourly_20220129_20230128_039d48N_073d59W_LST.nc`, although different dates/regions may be used.

### Observations LiDAR measurements

LiDAR measurements are obtained from NYSERDA Floating LiDAR Buoy Data: https://oswbuoysny.resourcepanorama.dnv.com

> OceanTech Services/DNV under contract to NYSERDA have kindly provided this data free of charge. Neither NYSERDA nor OceanTech Services/DNV have reviewed the information contained herein and the opinions in this report do not necessarily reflect those of any of these parties.

In the example notebook, we download `CSV` formatted dataset `E05_Hudson_South_West_10_min_avg_20220129_20230128.csv` and save in the directory `datasets/NYSERDA Floating LiDAR Buoy Data/`

### Global Wind Atlas

Global Wind Atlas makes many outputs freely available via api:

```
https://globalwindatlas.info/api/gis/country/DNK/wind-speed/100
https://globalwindatlas.info/api/gis/country/DNK/elevation_w_bathymetry
https://globalwindatlas.info/api/gis/country/ITA/wind-speed/100
```

## RISE

Use RISE to view the notebook as a series of interactive slides (as in the workshop). Using RISE is completely optional - if skipped the notebook will fallback as a regular jupyter notebook.

### Installation

To install RISE:

```sh
# windows
py -m pip install rise
# mac/linux
python3 -m pip install rise
```

Full usage available at https://rise.readthedocs.io/en/stable/usage.html

Note: RISE is only compatible with `jupyter notebook` and will not yet work with `jupyter labs` `visualcode` etc.

### Slides export

#### Option 1: Export to HTML

```sh
jupyter nbconvert "ClimServ Intro.ipynb" --to slides --reveal-prefix reveal.js
```

or if `reveal.js` is not installed:

```sh
jupyter nbconvert "ClimServ Intro.ipynb" --to slides --reveal-prefix "http://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.3.0"
```

#### Option 2: Export to PDF

```sh
jupyter nbconvert "ClimServ Intro.ipynb" --to slides --post serve
```

Add `?print-pdf` to the query `url` and save the destination `pdf` file, or alternatively open the page and print to PDF
