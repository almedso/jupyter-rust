# Rust Jupyter Notebooks

This repository contains jupyter notebooks that are processed by a rust engine.

## Why a Rust in Jupyter

* Learn and explore stuff interactively
* Faster than python on big data
* Appropriate solution for simulation context (of embedded rust code)


## Evcxr Jupyter Kernel

Here is explained what is supported and what not:

https://github.com/google/evcxr/blob/master/COMMON.md

As a short summary:
```
:help - to get help
:dep - install cargo dependencies
:sccache 1 - use caching (precompiled stuff)
:vars - print present variables
```

Customized output:
* by implementing own formatter
* see https://github.com/google/evcxr/tree/master/evcxr_jupyter for example
* output is provided by
  * Petgraph
  * https://igiagkiozis.github.io/plotly/content/fundamentals/jupyter_support.html
  * https://crates.io/crates/plotchart
  * https://crates.io/crates/showata


## Installation

### Prerequisite

* install python3
* use rustup to install rust
  https://rust-lang.github.io/rustup/


### Installing Jupyter Lab

https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html

```
pip3 install jupyter-lab
```
### Installing the Excvr Kernel

run
```
cargo install evcxr_jupyter
evcxr_jupyter --install
```

Additionally install for caching precompiled stuff
```
cargo install sccache
```

### Docker alternative

TODO
