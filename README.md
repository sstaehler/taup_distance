[![Build Status](https://travis-ci.org/sstaehler/taup_distance.svg?branch=master)](https://travis-ci.org/sstaehler/taup_distance)
[![DOI](https://zenodo.org/badge/317642884.svg)](https://zenodo.org/badge/latestdoi/317642884)



# taup_distance
Compute the distance of an earthquake given a seismic velocity model and a travel time difference between two phases (typically P and S).
Uses TauP in the implementation of obspy (https://obspy.org)

## Requirements
````
matplotlib
obspy 
scipy
numpy
````

## Installation
Using pip:
```shell script
$ git clone https://github.com/sstaehler/taup_distance
$ cd taup_distance
$ pip install -r requirements.txt
$ pip install -v -e .
```
## Example:
Contains a python script that can be called from shell:
```shell script
$ python -m taup_distance.taup_distance ./taup_file.nd 200 300 400
./taup_file.nd, S-P time: 200.0: NO SOLUTION FOUND!
./taup_file.nd, S-P time: 300.0, distance:  46.0
./taup_file.nd, S-P time: 400.0, distance:  62.9
```
as well as a Python function 
```python
from taup_distance.taup_distance import get_dist
from obspy.taup import TauPyModel
model = TauPyModel('iasp91')

dist = get_dist(tSmP=400, 
                depth=50.)
print(dist)
```
