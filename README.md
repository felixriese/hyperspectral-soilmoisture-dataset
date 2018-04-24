# Hyperspectral benchmark dataset on soil moisture

Hyperspectral and soil-moisture data from a field campaign based on a soil sample. Karlsruhe (Germany), 2017.

**Introducing paper:** Felix M. Riese and Sina Keller, “Introducing a Framework of Self-Organizing Maps for Regression of Soil Moisture with Hyperspectral Data,” in *2018 IEEE International Geoscience and Remote Sensing Symposium (IGARSS)*, Valencia, Spain, 2018, accepted.

**License:** [GNU GPLv2](https://www.gnu.org/licenses/gpl-2.0.html)

**Authors:**

- [Felix M. Riese, M.Sc.](mailto:felix.riese@kit.edu)
- [Dr. rer.nat. Sina Keller](mailto:sina.keller@kit.edu) 

**Citation of the dataset:** TODO

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

