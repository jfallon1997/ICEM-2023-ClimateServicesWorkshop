# ICEM-2023-ClimateServicesWorkshop
ICEM 2023 workshop on Climate Services

To view this notebook as a RISE presentation (recommended), open on mybinder.org (todo - need to make this repo public for this to work). The slides may alternatively be viewed as PDF or HTML, with limited functionality (see files in this repo)

Instructions are currently a work in progress.

Relevant links are kept up to date at [https://linktr.ee/ICEM23ClimateServices](https://linktr.ee/ICEM23ClimateServices)

## Python setup

### Method 1: mybinder.org

**recommended method**

No download or installation setup is needed, simply visit [URL to be created TODO](https://example.org) for an interactive copy of the workshop

### Method 2: using conda

**(use this installation method if conda/mamba already installed and not using mybinder.org)**

Alternatively, install the packages with [conda](https://docs.conda.io/en/latest) or [mamba](https://mamba.readthedocs.io/en/latest/user_guide/mamba.html):

```zsh
conda create -n icem
conda activate icem
conda install -c conda-forge jupyterlab pandas xarray
```

And in future access the packages using

```zsh
conda activate icem
```

### Method 3: using pip

**(use this installation method if running without conda installation and not on mybinder.org)**

Please ensure you have the following packages installed:

```python
# windows
py -m venv icem
source ./icem/bin/activate
py -m pip install jupyterlab pandas xarray

# mac/linux
python3 -m venv icem
source icem/bin/activate
python3 -m pip install jupyterlab pandas xarray
```

And in future, access the packages using

```zsh
# windows
source ./icem/bin/activate
# mac/linux
source icem/bin/activate
```
For more help on pip, see https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments


## RISE

Use RISE to view the notebook as a series of slides (as used in the workshop).

### Installation

To install RISE (ensure the correct venv is activated first, see previous instructions):

```zsh
# windows
py -m pip install rise
# mac/linux
python3 -m pip install rise
```

Full usage available at https://rise.readthedocs.io/en/stable/usage.html

Note: RISE is only compatible with `jupyter notebook` and will not work with `jupyter labs` `visualcode` etc.

### Slides export

#### Option 1: Export to HTML

```zsh
jupyter nbconvert "ClimServ Intro.ipynb" --to slides --reveal-prefix reveal.js
```

or if `reveal.js` is not installed:

```zsh
jupyter nbconvert "ClimServ Intro.ipynb" --to slides --reveal-prefix "http://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.3.0"
```

#### Option 2: Export to PDF

```zsh
jupyter nbconvert --to slides "ClimServ Intro.ipynb" --post serve
```

Add `?print-pdf` to the query `url` and save the destination `pdf` file, or alternatively open the page and print to PDF
