# ICEM 2023 workshop on Climate Services

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb)

Instructions are currently a work in progress.

For more information on the workshop and related pages, visit [https://linktr.ee/ICEM23ClimateServices](https://linktr.ee/ICEM23ClimateServices)

## Using the notebook

Recommended method: use the [interactive slides in the web browser (no additional setup required) via mybinder.org](https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb)

Advanced method: follow the instructions below to setup python, download data, and optionally install RISE (for presentation viewing mode). Once setup, the notebook can be viewed by running:

```sh
jupyter notebook "ClimServ Intro.ipynb"
```

## Python setup

### Method 1: mybinder.org

**recommended method (run via webapp, no installation required)**

Visit https://mybinder.org/v2/gh/jfallon1997/ICEM-2023-ClimateServicesWorkshop/HEAD?labpath=ClimServ%20Intro.ipynb

### Method 2: using conda

**(use this installation method if you are familiar with using conda)**

Ensure that you install the required packages with [conda](https://docs.conda.io/en/latest) or [mamba](https://mamba.readthedocs.io/en/latest/user_guide/mamba.html):

```sh
conda create -n icem
conda activate icem
conda install -c conda-forge jupyterlab pandas xarray rioxarray scipy matplotlib rasterio
```

And in future access the packages using

```sh
conda activate icem
```

### Method 3: using pip

**(use this installation method if you are not familiar with using conda)**

Please ensure you have the following packages installed:

```sh
# windows
py -m venv icem
source ./icem/bin/activate
py -m pip install jupyterlab pandas xarray rioxarray scipy matplotlib rasterio

# mac/linux
python3 -m venv icem
source icem/bin/activate
python3 -m pip install jupyterlab pandas xarray rioxarray scipy matplotlib rasterio
```

And in future, access the packages using

```sh
# windows
source ./icem/bin/activate
# mac/linux
source icem/bin/activate
```
For more help on pip, see https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments


## Downloading Data

### Reanalysis via NASA POWER DAVe

NASA POWER DAVe can be accessed at https://power.larc.nasa.gov/beta/data-access-viewer

In the example notebook, data spanning *2022-01-29* to *2023-01-28* at *039.48N*, *073.59W* is saved in `netCDF4` format as `datasets/POWER_Point_Hourly_20220129_20230128_039d48N_073d59W_LST.nc`, although different dates/regions may be used.

### Observations LiDAR measurements

LiDAR measurements are obtained from NYSERDA Floating LiDAR Buoy Data:
https://oswbuoysny.resourcepanorama.dnv.com

In the example notebook, we download `CSV` formatted dataset `E05_Hudson_South_West_10_min_avg_20220129_20230128.csv` and save in the directory `datasets/NYSERDA Floating LiDAR Buoy Data/`

## RISE

Use RISE to view the notebook as a series of interactive slides (as in the workshop). Using RISE is completely optional - if skipped the notebook will fallback as a regular jupyter notebook.

### Installation

To install RISE (ensure the correct venv is activated first, see previous instructions):

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
