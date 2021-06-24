# Eisenberg Collection


## Introduction

The Eisenberg Collection is a collection of commercial music recordings distributed in the Kenyan coast between 1930-1975. 

## Metadata

Metadata are provided as a [pandas](https://pandas.pydata.org/docs/) DataFrame, which is provided in HDF5 file format as a PyTables Table structure. The `metadata.h5` file can be loaded using the `pandas.read_hdf` method.
```python
import pandas as pd
metadata = pd.read_hdf("metadata.h5")
```

Not all metadata are available for all recordings, and this is the purpose of specific datasets, as explained later in this document. Empty entries contain the keyword **NA**. The metatags are listed below.
* Song Title
* Artist
* Composer
* Year (estimate/range)
* Original Form
* Label
* Serial Number
* Genre
* Collection ID
* NYUAD Archives Reference

## Features

Features are provided as a python dictionary using the NYUAD Archive Reference of each recording as a key. The `features.h5` file can be loaded using a library such as [deepdish](https://deepdish.readthedocs.io/en/latest/) with the `io.load` method.
```python
import deepdish as dd
features = dd.io.load("features.h5")
```
The archive reference for each recording is present in the metadata file, and can also be useful for retrieving the audio files of the collection if the user has [access](http://dlib.nyu.edu/findingaids/html/nyuad/ad_mc_035/admininfo.html) to them. The value of each key is a dictionary of features. The string keys for the features provided are
* `mfcc` : [Mel-frequency Cepstral Coefficients](https://librosa.org/doc/main/generated/librosa.feature.mfcc.html)
* `chromagram` : [Chromagram](https://librosa.org/doc/main/generated/librosa.feature.chroma_stft.html)
* `tempogram` : [Tempogram](https://librosa.org/doc/main/generated/librosa.feature.tempogram.html)

All features were computed using [librosa](https://librosa.org/doc/main/index.html) with the default parameters for each method. 

Below is an example of the features dictionary.
```python
{
  "AD-MC-035_ref2": {  # NYUAD Archive reference key
    "mfcc": np.ndarray,  # shape=(20, t)
    "chromagram": np.ndarray,  # shape=(12, t)
    "tempogram": np.ndarray  # shape=(384, n)
   }
   ..
}
```


## Datasets

Datasets containing subsets of the collection are provided to ensure the completness of the relevant metadata for particular tasks. For each dataset, a .txt file with <em>newline</em>-separated entries is provided containing the NYUAD Archive reference keys of the recordings in the dataset. The file can be loaded as a python list and used to retrieve the relevant metadata and features.

### Tarab Classification

### Genre Classification

### Instrument Classification

### Date Estimation

