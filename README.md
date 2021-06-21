# Eisenberg Collection
Collection of commercial music recordings distributed in the Kenyan coast between 1930-1975

## Metadata

Metadata are provided as a pandas DataFrame saved in HDF5 file format. The file can be loaded using the `pandas.read_hdf` method, where specific columns can be selectively read.

Not all metadata are available for all recordings, and this is the purpose of specific datasets, as explained later in this document. Empty entries contain the keyword **NA**. All possible metatags are listed below.
* Song Title
* Artist
* Composer
* Year (estimate/range)
* Original Form
* Label
* Serial Number
* Genre
* Collection ID
* NUAD Archives Reference

## Datasets

Datasets containing subsets of the collection are provided to ensure the completness of the relevant metadata for particular tasks. For each dataset, a .csv file with <em>newline</em>-separated entries is provided containing the NYUAD Archive reference keys of the recordings in the dataset. The metadata can then be retrieved from the global metadata dictionary using the keys.

### Tarab Classification
