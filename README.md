# Thresher - THRESHold EvaluatoR for Python

A bare pandas implementation of a tool for finding the threshold which maximizes accuracy 
of `predict_proba` like-outputs (from e.g. `scikit-learn`), in regard to the provided ground truth (labels).

## Project description

Method interesting for the user is `optimize_threshold(scores, actual_classes)`, which is available 
from the `Thresher` class. This method, for given _scores_ and _actual classes_, 
returns a threshold that yields the _**highest fraction** of correctly classified_ samples.

```
optimize_threshold parameters:
  scores​:list
    The list of scores.
  actual_classes​:list
    The list of ground truth (correct) classes. 
    Classes are represented as -1 and 1.
returns:
  threshold:​float
    The threshold value that yields ​the highest fraction of correctly classified 
    samples​. If multiple thresholds give the optimal fraction, return any threshold.
```

### An oracle mechanism

### Implemented algorithms

### Linear search

### 2-dim Stochastic Gradient Descent

### Evolutionary algorithm

### Grid search

### Stochastic Grid search

## How to setup?

The process is rather straightforward, you just need to just whether to install 
from the sources (latest revision), or from the PyPI repository (stable release).

### Requirements

Tested with Python `3.7+`, on a standard Unix environment

### Installation

Installation from source:

```
pip install git+https://github.com/oskar-j/thresher.git
```

Stable release using the `pip` tool:

```
pip install thresher-py
```

## Sample usage

```python
import thresher

t = thresher.Thresher()

print('Currently supported algorithms:')
print(t.get_supported_algorithms())

cases = [0.1, 0.3, 0.4, 0.7]
actual_labels = [-1, -1, 1, 1]

print(f'Optimization result: {t.optimize_threshold(cases, actual_labels)}')
```

## Future work

* adding more algorithms
* publishing on conda
* more heavy test loads
* python docs
* CI pipeline for automated tests
