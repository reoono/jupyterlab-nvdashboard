JupyterLab GPU Dashboards
===========================

[![Build Status](https://travis-ci.com/jacobtomlinson/jupyterlab-nvdashboard.svg?branch=master)](https://travis-ci.com/jacobtomlinson/jupyterlab-nvdashboard)

A JupyterLab extension for displaying dashboards of GPU usage.

![demo](./demo.gif)

Built with [JupyterLab and Bokeh Server](https://github.com/ian-r-rose/jupyterlab-bokeh-server)


What's here
-----------

This repository contains two sets of code:

-   Python code defining a Bokeh Server application that generates the dashboards
    in the `jupyterlab_nvdashboard/` directory
-   TypeScript code integrating these dashboards into JupyterLab in the `src/`
    directory

You should be able to modify only the Python code to edit the dashboards
without modifying the TypeScript code.

## Prerequisites

* JupyterLab 1.0
* bokeh
* pynvml

## Installation

This extension has a server-side (Python) and a client-side (Typescript) component,
and we must install both in order for it to work.

To install the server-side component, run the following in your terminal

```bash
pip install jupyterlab-nvdashboard
```

To install the client-side component, run

```bash
jupyter labextension install jupyterlab-nvdashboard
```

## Development

To install the server-side part, run the following in your terminal from the repository directory:

```bash
pip install -e .
```

In order to install the client-side component (requires node version 8 or later), run the following in the repository directory:

```bash
jlpm install
jlpm run build
jupyter labextension install .
```

To rebuild the package and the JupyterLab app:

```bash
jlpm run build
jupyter lab build
```

## Publishing

This application is distributed as two subpackages.

The JupyterLab frontend part is published to [npm](https://www.npmjs.com/package/jupyterlab-nvdashboard),
and the server-side part to [PyPI](https://pypi.org/project/jupyterlab-nvdashboard/).

Releases are done with the `npm` tool, git and travis.

```console
$ npm version [major|minor|patch]  # updates package.json and creates git commit and tag
$ git push && git push --tags  # pushes tags to GitHub which triggers Travis CI to build and deploy
```
