# Jupyter

https://jupyter.org/

...  from this site

The Jupyter Notebook is an open-source **web application** that allows you to **create and share documents that contain live code, equations, visualizations and narrative text**. Uses include: data cleaning and transformation, **numerical simulation, statistical modeling, data visualization, machine learning**, and much more.

online viewer: https://nbviewer.jupyter.org/

## Jupyter Notebook and Jupyter Lab

Jupiter Notebook ist das web basierte GUI for ein Jupyter Notebook.
(je browser tab ein notebook)

```
jupyter notebook
```

Jupiter Lab ist nächste Generation GUI für Jupyter Notebooks.
Jupyter Lab ist single tab.

```
jupyter lab
```

## Jupyter Kernels


https://jupyter-tutorial.readthedocs.io/de/latest/workspace/jupyter/kernels/install.html

* Python2
* Python3
* R
* Scala
* Julia
* *Rust** -> ./rust-kernel.md


## Jupyter Extensions


https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/


### Spell Checker Extension

Brauche ich unbedingt ...
```
# on jupyter notebook
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
jupyter nbextension enable spellchecker/main

# on jupyter lab
pip3 install jupyterlab-spellchecker
jupyter labextension install @ijmbarr/jupyterlab_spellchecker

```

## Dokumente formatieren

Sphinx!

https://jupyter-tutorial.readthedocs.io/de/latest/workspace/jupyter/nbsphinx.html

# Binder

Öffentlich verfügbare Execution Facility für Jupyternotebooks
organisiert in git repositories. 

https://mybinder.org/

Projekt Info: https://jupyter.org/binder
Binderhub (https://github.com/jupyterhub/binderhub)
Binder nutzt *jupyterhub* und *repo2docker*

## repo2docker Tool

https://github.com/jupyterhub/repo2docker

Tool um ein (git) Repository mit Jupyter Notebooks im
Docker Container laufen zu lassen.

### Voraussetzungen

* python3 installiert, pip3 installiert
* docker installiert; laufend; und lokale Rechte

### Installation

als gewöhnliches Python package

```
pip3 install repo2docker
```

### Benutzung

Ein Repository mit Jupyter Notebooks enthält neben den Notebooks auch
Definitionen von Abhängigkeiten z.B. *requirements.txt* (pip)
*environment.yml* (conda), cargo.toml?

https://repo2docker.readthedocs.io/en/latest/usage.html

configuration über

* environment.yml (conda https://conda.io/projects/conda/en/latest/configuration.html)
* requirements.txt (python packages)
* apt.txt (debian packages)
* postBuild (bash script)


Note:

conda context over pip, apt
** platform independent, binary
** support of tensorflow, gpu, scipy, opencv


Au der Kommandozeile:

```
jupyter-repo2docker https://github.com/norvig/pytudes
```
* baut ein Image (nutzt hinterlegte Abhängigkeiten um Extensions und Kernel zu installieren)
* started das Docker image
* bietet Url mit token z.B.
  ```
  Copy/paste this URL into your browser when you connect for the first time,
  to login with a token:
    http://0.0.0.0:36511/?token=f94f8fabb92e22f5bfab116c382b4707fc2cade56ad1ace0
  ````
* Ctrl-C stopped und löscht den Container
* Image bleibt bestehen .. z.B.
  ```
  Volkers-MBP:volker$ docker images
  REPOSITORY               TAG       IMAGE ID       CREATED          SIZE
  r2d-2e1619187023         latest    66973dffc643   38 minutes ago   1.72GB
  ```

### Jupyterhub

(kopiert aus dem README ...)
With JupyterHub you can create a multi-user Hub which spawns, manages, and proxies multiple instances of the single-user Jupyter notebook server.

https://github.com/jupyterhub/jupyterhub


# Jupyter und Docker Images

Vorgefertigte Jupyter Docker Container

* https://hub.docker.com/search?q=jupyter&type=image
* https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html

Image dependencies

* https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#image-relationships

Beliebteste Container:

* https://hub.docker.com/r/jupyter/datascience-notebook (10M+ downloads)
* https://hub.docker.com/r/jupyter/tensorflow-notebook (10M+ downloads)

