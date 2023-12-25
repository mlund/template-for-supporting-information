[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mlund/template-for-supporting-information/HEAD)
[![CC BY 4.0][cc-by-shield]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

# Electronic Notebook: Title goes here

Template for Notebooks for Supporting Information and Zenodo Deposition.

## Layout

Description of the directory layout.

- `README.md` This is the file you're viewing right now. You may want to edit the **Binder** badge above to match your repository.
- `environment.yml` Defines the required Python packages using conda. It's a good idea to try to set specific versions of your
  dependencies as their behavior may change in the future.
  The environment is currently called `my_environment` and you'll likely want to rename it to something less generic.
- `.zenodo.json` metadata for Zenodo.
- `ruff.toml` and `github/workflows/ruff.yml` sets up ruff linting for Python and Jupyter Notebooks. Delete if not relevant to your project.

## Requirements

To run the Notebooks online, click on the _Launch Binder_ badge above. Alternatively, if you want to run on your own computer,
install Python using _e.g._ [Miniforge](https://github.com/conda-forge/miniforge) or [Anaconda](https://docs.conda.io))
and make sure all required packages are loaded by issuing the following terminal commands

``` bash
    conda env create -f environment.yml
    source activate my_environment
    jupyter-lab
```

## Checklist - delete before publishing

- [ ] Add authors and other relevant metadata to `.zenodo.json`; to learn more about the available datafields, see
  [here](https://developers.zenodo.org/?python#depositions).
  Before publishing, validate the JSON file using the Zenodo deposition schema [`legacyrecord.json`](https://raw.githubusercontent.com/zenodo/zenodo/master/zenodo/modules/deposit/jsonschemas/deposits/records/legacyrecord.json) with _e.g._
  ``` bash
  pip install jsonschema
  wget https://raw.githubusercontent.com/zenodo/zenodo/master/zenodo/modules/deposit/jsonschemas/deposits/records/legacyrecord.json
  jsonschema legacyrecord.json < .zenodo.json
  ```
- [ ] Update Binder badge to point to your repository
- [ ] Add the Github repo link and DOI of the associated publication to `.zenodo.json` under `related_identifiers`.
- [ ] Update `environment.yml` to include required packages. Select name for environment.
- [ ] If needed, change the license (`LICENSE` and badge in `README.md`)
- [ ] Activate Github tracking of the repository on Zenodo.org. Repository must be public.
- [ ] Create a release on Github - adhere to [SemVer](https://semver.org). This triggers a archivation on Zenodo.
- [ ] Once you get the Zenodo DOI, add a badge to the top if this README. Use link to _all_ versions.
- [ ] Feel free to update and make new releases!
