# Bird Species Classification Using CNNs

A BERN02 statistical learning project investigating the classification of bird species from photographs using convolutional neural networks (CNNs). The project uses openly licensed bird images linked to occurrence records from the [Global Biodiversity Information Facility (GBIF)](https://www.gbif.org/).

The workflow is developed in Python using Jupyter notebooks / Google Colab, with an emphasis on reproducibility, careful model evaluation, and the FAIR principles.

## Project aims

The main task is **four-class bird species classification**. In addition to evaluating predictive performance, the project can investigate how results change with CNN architecture, image resolution, colour preprocessing, image augmentation, and geographic variation in the data.

The four species are:

| Common name | Scientific name |
| --- | --- |
| Mallard | *Anas platyrhynchos* |
| Hooded Crow | *Corvus cornix* |
| Great Tit | *Parus major* |
| Common Blackbird | *Turdus merula* |

## Data source and preparation

The images originate from GBIF occurrence records for human observations across seven countries. Data preparation selects **one image per observation** and retains images whose recorded licences are **CC0, CC BY, or CC BY-SA**. The applicable terms of each individual image still need to be followed.

GBIF occurrence data were retrieved for this project; the relevant download is documented at [GBIF download DOI: 10.15468/dl.7egxfm](https://doi.org/10.15468/dl.7egxfm). See [GBIF's citation guidelines](https://www.gbif.org/citation-guidelines) for citing occurrence data and associated images.

The prepared dataset is stored outside the GitHub repository as a ZIP archive in Google Drive:

```text
MyDrive/
└── GBIF/
    └── bird_dataset.zip
```

Its contents are:

```text
bird_dataset.zip
├── metadata.csv
└── bird_images/
    ├── ...
    └── ...
```

The metadata includes a `file` column identifying each local image and a `species` column containing its class. It also retains relevant provenance information (such as GBIF occurrence identifiers, image URLs, creators, and licences) and a `group` column intended to support group-aware evaluation. Not all fields are necessarily complete for every record.

## Repository layout

```text
.
├── README.md          # Overview and instructions
├── LICENSE            # MIT licence for original code and documentation
└── *.ipynb            # Data preparation, analysis, and modelling notebooks
```

The exact notebook filenames depend on the final repository. The image archive is deliberately kept outside GitHub because of its size and third-party licensing requirements.

## How to reproduce the analysis

1. Open the project's notebooks in Google Colab (or another compatible Jupyter environment).
2. Make sure `bird_dataset.zip` is available in your Google Drive at `MyDrive/GBIF/bird_dataset.zip`.
3. Run the following setup cell to mount Google Drive and extract the dataset into the Colab runtime.
4. Execute the notebooks in their documented order, installing any packages specified in those notebooks. Record the package versions, random seeds, and chosen train/validation/test split when reporting results.

### Model evaluation

To reduce information leakage, images linked through the grouping variable should be assigned to the **same** fold. For example, if the `group` column captures photographer/observation-date overlap, ordinary random image-level splitting could allow closely related photographs in both training and validation sets.

Fit preprocessing transformations and model hyperparameters on training data only; do not use a held-out test set for model selection. Suitable evaluation outputs include per-class precision/recall, macro-F1, a confusion matrix, and overall accuracy. If geographical generalization is studied, report the country-level split separately from ordinary cross-validation.

## Reproducibility and FAIR principles

- **Findable:** This README identifies the data provider, species, and GBIF download DOI; image-level identifiers should be retained in `metadata.csv`.
- **Accessible:** Code and documentation can be accessed through the repository. The large image archive is kept in Google Drive and is not automatically public; access must be arranged separately. Original records may be found via GBIF identifiers and image URLs.
- **Interoperable:** The metadata is stored as CSV, and notebooks use broadly available Python tools. Scientific species names and GBIF identifiers support consistent interpretation.
- **Reusable:** The workflow documents data preparation, evaluation, and provenance. Retaining per-image licensing and attribution information is essential for lawful reuse.

## Licence and attribution

Original code and documentation authored for this repository are released under the **MIT License**; see [LICENSE](LICENSE).

**The MIT License does not apply to third-party bird photographs or source data.** Images remain under their respective recorded licences (CC0, CC BY, or CC BY-SA), and any required creator credit, links to the original licence, and notices of modifications must be preserved. In particular, CC BY-SA images may have share-alike requirements for adaptations. Check the actual `license`, `creator`, and source URL associated with each image before redistribution or publication.

Users of GBIF-mediated data should cite the [GBIF download DOI](https://doi.org/10.15468/dl.7egxfm) and acknowledge the relevant data publishers and image creators as appropriate. See the [GBIF data user agreement](https://www.gbif.org/terms/data-user).

## Authors

Sek Huen Leung and Kadri Kalamäe.
