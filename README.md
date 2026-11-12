# GEOGM0081 Example Code Repository

This repository is part of the the [class GEOGM0081 "Geospatial Scientific Computing"](https://trchudley.github.io/geospatial-scientific-computing/), taught in the School of Geographical Sciences at the University of Bristol. It shows an example of how you might wish to structure your code submission for the class's final report. 

The Jupyter Notebooks contained herein [rework the examples shown in Week 7](https://trchudley.github.io/geospatial-scientific-computing/week/07/) into a suitably structured reproducable repository. In it, we use Landsat imagery to map the severity/extent of the April 2026 wildfire in Powys, Wales, using the Normalised Burn Ratio (NBR).

## Repository structure

```
geogm0081-example-repo/
├── README.md
├── LICENSE
├── environment.yml
├── .gitignore
├── data/
│   ├── README.md                           # description of the data and where it comes from
│   ├── effis_modis_powys_20260427.gpkg     # EFFIS fire perimeter (included)
│   ├── multispectral/                      # Landsat surface reflectance (created by notebook 1)
│   ├── nbr/                                # NBR rasters (created by notebook 2)
│   ├── dnbr/                               # dNBR rasters (created by notebook 2)
│   └── timeseries/                         # burned area and dNBR statistics (created by notebook 2)
├── figures/                                # figures (created by notebook 3)
└── notebooks/
    ├── 1-download-landsat.ipynb
    ├── 2-process-data.ipynb
    └── 3-plot-data.ipynb
```

GeoTIFF files (`*.tif`) are no included in the repository. They can be recreated by running the notebooks. See [`data/README.md`](data/README.md) for more details on the data.

## Setup

Create and activate the conda environment, which will be called `powys-fire`:

```
conda env create -f environment.yml
conda activate powys-fire
```

Then start Jupyter Lab from the repository directory:

```
jupyter lab
```

## Usage

Run the notebooks in `notebooks/` in order:

1. `1-download-landsat.ipynb` searches the Microsoft Planetary Computer for Landsat 8/9 imagery,  saving it to `data/multispectral/`.
2. `2-process-data.ipynb` calculates NBR and dNBR, and the burned area and dNBR statistics through time, saving it to `data/`.
3. `3-plot-data.ipynb` produces the figures, saving them to `figures/`.

Each notebook should be able to be run from start to finish with no further input.

## License

Code is released under the MIT License (see `LICENSE`).
