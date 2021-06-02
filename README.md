# Eisenberg Collection
Collection of commercial music recordings distributed in the Kenyan coast between 1930-1975

## Metadata

Metadata are provided as a Python dictionary saved in .json file format. The collection's hierarchy is flat, and metadata for a specific recording are accessed using the NYUAD Archive reference key. Not all metadata are available for all recordings, and this is the purpose of specific datasets, as explained later in this document. Empty entries contain the keyword **None**. All possible metadata categories are listed below.
* title
* artist
* recording_date
* etc...

An example can be seen below.
```python
{
  "AD-MC-035_ref2": { # NYUAD Archive reference key
    "title": "Basamir Azzein—Part 1",
    "artist": "A. M. Bin Berek",
    "recording_date": "ca. 1955-1965",
    "genre": None
    ..
   }
   ..
}

````

## Datasets

Datasets containing subsets of the collection are provided to ensure the completness of the relevant metadata for particular tasks. For each dataset, a .csv file with <em>newline</em>-separated entries is provided containing the NYUAD Archive reference keys of the recordings in the dataset. The metadata can then be retrieved from the global metadata dictionary using the keys.

### Tarab Classification
