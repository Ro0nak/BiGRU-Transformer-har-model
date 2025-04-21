# BiGRU-Transformer for Human Activity Recognition (HAR)

This project implements a hybrid **BiGRU + Transformer** model for **Human Activity Recognition (HAR)** using the **Aruba smart home dataset** from the **CASAS project**.

## 📊 Dataset: Aruba (CASAS)

- Source: [CASAS Datasets – Washington State University](https://casas.wsu.edu/datasets/)
- Dataset: Aruba (Smart Home Environmental Sensor Data)
- Sensor types include motion, door, and temperature.
- Data is annotated with daily activity labels (e.g., Sleeping, Eating, Housekeeping).

To download the dataset automatically, run the following script (included in the notebook or separately):

```python
import os
import requests
from zipfile import ZipFile

# Download Aruba dataset
url = "http://casas.wsu.edu/datasets/aruba.zip"
filename = "aruba.zip"

if not os.path.exists(filename):
    print("Downloading Aruba dataset...")
    r = requests.get(url)
    with open(filename, "wb") as f:
        f.write(r.content)
    print("Download complete.")

# Extract
with ZipFile(filename, 'r') as zip_ref:
    zip_ref.extractall("aruba")
    print("Dataset extracted to ./aruba/")
