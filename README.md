[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1227836.svg)](https://doi.org/10.5281/zenodo.1227836)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/felixriese/hyperspectral-soilmoisture-dataset/master?filepath=example.ipynb)

# Hyperspectral benchmark dataset on soil moisture

Hyperspectral and soil-moisture data from a field campaign based on a soil sample. Karlsruhe (Germany), 2017.

**License:** [GNU GPLv2](https://www.gnu.org/licenses/gpl-2.0.html)

**Authors:**

- [Felix M. Riese, M.Sc.](mailto:felix.riese@kit.edu)
- [Dr. rer.nat. Sina Keller](mailto:sina.keller@kit.edu)

**Citation:** see [Citation](#citation) and [bibliography.bib](bibliography.bib).


## Description

This dataset was measured in a five-day field campaign in May 2017 in Karlsruhe, Germany. An undisturbed soil sample is the centerpiece of the measurement setup. The soil sample consists of bare soil without any vegetation and was taken in the area near Waldbronn, Germany.

The following sensors were deployed:

- Cubert UHD 285 **hyperspectral** snapshot camera recording 50 by 50 images with 125 spectral bands ranging from 450 nm to 950 nm and a spectral resolution of 4 nm.
- TRIME-PICO time-domain reflectometry (TDR) sensor in a depth of 2 cm measuring the **soil moisture** in percent.

## Variables

- **datetime:** date and time of the measurement
- **soil_moisture:** soil moisture in %
- **soil_temperature:** soil temperature in °C
- **454, 458, … 946, 950:** hyperspectral bands in nm

## Example script to read in the data

In Python 3.6:

```python
import pandas as pd
from sklearn.model_selection import train_test_split

# load dataframe
df = pd.read_csv("soilmoisture_dataset.csv", index_col=0)

# get hyperspectral bands:
hypbands = []
for col in df.columns:
    try:
        int(col)
    except Exception:
        continue
    hypbands.append(col)

# split dataset
X_train, X_test, y_train, y_test = train_test_split(
    df[hypbands], df["soil_moisture"],
    test_size=0.5, random_state=42, shuffle=True)
```

## Citation

The bibtex file including both references is available in [bibliography.bib](bibliography.bib).

**Paper**

Felix M. Riese and Sina Keller, “Introducing a Framework of Self-Organizing Maps for Regression of Soil Moisture with Hyperspectral Data,” in *IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium*, Valencia, Spain, 2018, pp. 6151-6154. ([Link](https://doi.org/10.1109/IGARSS.2018.8517812))

```
    @inproceedings{riese2018introducing,
        author = {Riese, Felix~M. and Keller, Sina},
        title = {{Introducing a Framework of Self-Organizing Maps for Regression of Soil Moisture with Hyperspectral Data}},
        booktitle = {IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium},
        year = {2018},
        month = {July},
        address = {Valencia, Spain},
        doi = {10.1109/IGARSS.2018.8517812},
        ISSN = {2153-7003},
        pages = {6151--6154},
    }
```

**Code**

Felix M. Riese and Sina Keller, "Hyperspectral benchmark dataset on soil moisture", Dataset, Zenodo, 2018. ([Link](http://doi.org/10.5281/zenodo.1227836))

```
    @misc{riesekeller2018,
        author = {Riese, Felix~M. and Keller, Sina},
        title = {Hyperspectral benchmark dataset on soil moisture},
        year = {2018},
        DOI = {10.5281/zenodo.1227837},
        publisher = {Zenodo},
        howpublished = {\href{https://doi.org/10.5281/zenodo.1227837}{doi.org/10.5281/zenodo.1227837}}
    }
```

