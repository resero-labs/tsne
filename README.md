[![PyPI - Version](https://img.shields.io/pypi/v/tsne-mp.svg)](https://pypi.org/project/tsne-mp/) [![PyPI - Wheel](https://img.shields.io/pypi/wheel/tsne-mp.svg)](https://pypi.org/project/tsne-mp/) [![Python 3.6](https://img.shields.io/badge/python-3.7-blue.svg)](https://www.python.org/downloads/release/python-370/) [![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/) [![Python 3.6](https://img.shields.io/badge/python-3.5-blue.svg)](https://www.python.org/downloads/release/python-350/) 

# Python TSNE implementation utilizing openmp for performance

This is based on the [10XDev/tsne](https://github.com/10XDev/tsne.git) fork of L.J.P. van der Maaten BH-tSNE implementation.

It has fixes to allow this to run in Python 3 and performance has been significantly
increased with OpenMP parallelism. (see: [tsne-perf-test](https://github.com/rappdw/tsne-perf-test.git))

**Note:** While [Scikit-learn v0.17](http://scikit-learn.org/stable/whats_new.html#version-0-17) has a tsne implementation, 
this implementation performs significantly faster than scikit-learn's. If you need speed, use this.


## Algorithms

### Barnes-Hut-SNE

A python ([cython](http://www.cython.org)) wrapper for [Barnes-Hut-SNE](http://homepage.tudelft.nl/19j49/t-SNE.html) aka fast-tsne.

We forked 10XDev's implementation and openmp enabled the code.

## Installation

This library has been added to pypi as tsne-mp

```
pip install tsne-mp
```

It requires openmp support.
* OSX - `brew install libomp`
* linux - 'sudo apt-get install libgomp1'
* Windows - Included with Visual Studio C++

## Usage

Basic usage:

```
from tsne import bh_sne
X_2d = bh_sne(X)
```
Or, the wheels also contain an executable that can be used from the command-line as described
in [the original project](https://github.com/lvdmaaten/bhtsne).

### Examples

* [Iris](http://nbviewer.ipython.org/urls/raw.github.com/danielfrg/py_tsne/master/examples/iris.ipynb)
* [MNIST](http://nbviewer.ipython.org/urls/raw.github.com/danielfrg/py_tsne/master/examples/mnist.ipynb)
* [word2vec on presidential speeches](https://github.com/prateekpg2455/U.S-Presidential-Speeches) via [@prateekpg2455](https://github.com/prateekpg2455)

## More Information

See *Barnes-Hut-SNE* (2013), L.J.P. van der Maaten. It is available on [arxiv](http://arxiv.org/abs/1301.3342).

