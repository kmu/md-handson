# MD hands-on

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/kmu/md-handson/HEAD?urlpath=lab%2Ftree%2Findex.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kmu/md-handson/blob/main/index.ipynb)

A Binder-compatible repo with an `environment.yml` file, based on
[binder-examples/conda](https://github.com/binder-examples/conda).

Packages: **ASE**, **ASAP3**, **pymatgen**, **mp-api**, **nglview** / **py3Dmol**, **GPAW**, **CHGNet**.

Launch: https://mybinder.org/v2/gh/kmu/md-handson/HEAD?urlpath=lab%2Ftree%2Findex.ipynb

## Google Colab

Open `index.ipynb` in Colab via the badge above. The first code cell detects Colab and:

1. Clones this repo for `input/` CIF files (if missing)
2. `pip install`s dependencies (`ase`, `asap3`, `gpaw`, `chgnet`, …)
3. Uses **py3Dmol** for 3D visualization (`nglview` does not work in Colab)

Runtime restart may be required after the first install. Prefer a GPU runtime for CHGNet sections.


> **Note:** open this in **JupyterLab**, not the classic Notebook interface.
> `nglview`'s 3D viewer widget is shipped as a JupyterLab federated
> extension and will not render in the classic `/notebooks/` (`filepath=`)
> interface.

`nglview`, `jupyterlab`, and `ipywidgets` are pinned together in
`environment.yml`. Bumping one of them alone tends to break the viewer, since
`nglview` bundles a prebuilt labextension whose version has to match the one
`jupyterlab-manager` registers.

First build is slower (PyTorch CPU + GPAW). Keep GPAW examples small on Binder.
Open `index.ipynb` in JupyterLab for the Japanese hands-on (structures → GPAW electron density → NaCl DFT scan → DFT opt → Materials Project → EMT opt → ASAP MD → CHGNet MD → CHGNet relax / nglview → Al surface oxidation).
For the Materials Project section, set `MP_API_KEY` (see [API docs](https://next-gen.materialsproject.org/api)).
