# Jupyter

https://jupyter.org/

... from this site

The Jupyter Notebook is an open-source **web application** that allows you to **create and share documents that contain live code, equations, visualizations and narrative text**. Uses include: data cleaning and transformation, **numerical simulation, statistical modeling, data visualization, machine learning**, and much more.

online viewer: https://nbviewer.jupyter.org/

## Jupyter Notebook and Jupyter Lab

Jupiter Notebook is the WEB GUI for _a single_ Jupyter Notebook.
(One notebook per browser tab.)

```
jupyter notebook
```

Jupiter Lab is the kind of next generation of WEB GUI for a set of Jupyter Notebooks.
(Jupyter Lab is single tab.)

```
jupyter lab
```

## Visual Studio Code

Pluggins:

- Jupyter (14.4M downloads, 2.5 stars) - works ok
- VSCode Jupyter (246k downlads, 3.5 stars)

... there are more

## Jupyter Kernels

https://jupyter-tutorial.readthedocs.io/de/latest/workspace/jupyter/kernels/install.html

- Python2
- Python3
- R
- Scala
- Julia
- \*Rust\*\* -> ./rust-kernel.md

## Jupyter Extensions

https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/

### Spell Checker Extension

This is what I need ...

```
# on jupyter notebook
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
jupyter nbextension enable spellchecker/main

# on jupyter lab
pip3 install jupyterlab-spellchecker
jupyter labextension install @ijmbarr/jupyterlab_spellchecker

```

## Format Documents

Sphinx!

https://jupyter-tutorial.readthedocs.io/de/latest/workspace/jupyter/nbsphinx.html

# Binder

Binder is a publicly available execution facility for Jupyter Notebooks
which are organized in git repositories.

https://mybinder.org/

Project Info: https://jupyter.org/binder
Binderhub (https://github.com/jupyterhub/binderhub)
Binder uses _jupyterhub_ und _repo2docker_

## repo2docker Tool

https://github.com/jupyterhub/repo2docker

Tool um ein (git) Repository mit Jupyter Notebooks im
Docker Container laufen zu lassen.

### Prerequisites

- python3 installed
- pip3 installed
- docker running with administrative access

Note:
Does not work on windows

### Installation

repo2docker is installed like any other python package.

```
pip3 install jupyter-repo2docker
```

### Usage

A repository with Jupyter Notebooks contains the notebooks and might contain
optional dependency definitions.

https://repo2docker.readthedocs.io/en/latest/usage.html

Configuration could be expressed as follow

- environment.yml (conda https://conda.io/projects/conda/en/latest/configuration.html)
- requirements.txt (python packages)
- apt.txt (debian packages)
- postBuild (bash script)

Note:

conda context over pip, apt

** platform independent, binary
** support of tensorflow, gpu, scipy, opencv

On the command line run:

```
jupyter-repo2docker https://github.com/norvig/pytudes
```

- creates a docker image on the fly; installs specified dependencies to install extensions and kernels.
- starts a docker container using the image built
- binds Url with a token and gives information about this URL

  ```
  Copy/paste this URL into your browser when you connect for the first time,
  to login with a token:
    http://0.0.0.0:36511/?token=f94f8fabb92e22f5bfab116c382b4707fc2cade56ad1ace0
  ```

- Ctrl-C stops and removes the container
- image is not removed; e.g.
  ```
  Volkers-MBP:volker$ docker images
  REPOSITORY               TAG       IMAGE ID       CREATED          SIZE
  r2d-2e1619187023         latest    66973dffc643   38 minutes ago   1.72GB
  ```

### Jupyterhub

(copied from README ...)
With JupyterHub you can create a multi-user Hub which spawns, manages, and proxies multiple instances of the single-user Jupyter notebook server.

https://github.com/jupyterhub/jupyterhub

# Jupyter and Docker Images

There are predefined Jupyter docker container

- https://hub.docker.com/search?q=jupyter&type=image
- https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html

Image dependencies

- https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#image-relationships

Popular images:

- https://hub.docker.com/r/jupyter/datascience-notebook (10M+ downloads)
- https://hub.docker.com/r/jupyter/tensorflow-notebook (10M+ downloads)
