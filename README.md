# MD hands-on

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/kmu/md-handson/HEAD?urlpath=lab%2Ftree%2Findex.ipynb)

A Binder-compatible repo with an `environment.yml` file, based on
[binder-examples/conda](https://github.com/binder-examples/conda).

Packages: **ASE**, **ASAP3**, **pymatgen**, **mp-api**, **nglview**, **GPAW**, **CHGNet**.

Launch: https://mybinder.org/v2/gh/kmu/md-handson/HEAD?urlpath=lab%2Ftree%2Findex.ipynb

> **Note:** open this in **JupyterLab**, not the classic Notebook interface.
> `nglview`'s 3D viewer widget is shipped as a JupyterLab federated
> extension and will not render in the classic `/notebooks/` (`filepath=`)
> interface.

`nglview`, `jupyterlab`, and `ipywidgets` are pinned together in
`environment.yml`. Bumping one of them alone tends to break the viewer, since
`nglview` bundles a prebuilt labextension whose version has to match the one
`jupyterlab-manager` registers.

First build is slower (PyTorch CPU + GPAW). Keep GPAW examples small on Binder.
Open `index.ipynb` in JupyterLab for the Japanese hands-on (structures → Materials Project → GPAW → ASAP MD → CHGNet MD).
For the Materials Project section, set `MP_API_KEY` (see [API docs](https://next-gen.materialsproject.org/api)).
