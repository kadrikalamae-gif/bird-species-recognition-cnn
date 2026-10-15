# Bird Species Classification Using Small Convolutional Neural Networks

**BERN02 Project** · Sek Huen Leung and Kadri Kalamäe

## Overview

This project investigates how image resolution and image-preprocessing choices affect bird-species classification using small convolutional neural networks (CNNs). Using citizen-science photographs, we compare model configurations and evaluate their performance on held-out data.

The project is implemented in Python using a Jupyter notebook and can be run in Google Colab.

## Dataset

The dataset contains **2,188 observations** covering four bird species:

- Mallard (*Anas platyrhynchos*)
- Hooded Crow (*Corvus cornix*)
- Great Tit (*Parus major*)
- Common Blackbird (*Turdus merula*)

Observations come from Sweden, Norway, Denmark, Finland, Estonia, Latvia and Lithuania. The data were obtained through GBIF from iNaturalist Research-Grade Observations.

**Dataset DOI:** [10.15468/dl.pfd9ab](https://doi.org/10.15468/dl.pfd9ab)

Only images with CC0, CC BY, or CC BY-SA licences were included.

The image dataset is stored separately from this repository and downloaded in the notebook from Google Drive.

## Project workflow

The notebook covers:

1. Dataset exploration and preparation.
2. Data splitting.
3. CNN experiments with different image resolutions and architectural choices.
4. Comparison of RGB and grayscale inputs, colour augmentation, and image-enhancement methods.
5. Evaluation using macro-F1, accuracy, and other classification metrics.

## Getting started

1. Open `BERN02_Project.ipynb` in Google Colab.
2. Run the notebook cells in order. The setup cell automatically downloads and extracts the dataset from a shared Google Drive link.
3. The dataset is stored in the temporary Colab runtime and may need to be downloaded again after a runtime reset.

For local Jupyter execution, additional environment and path configuration may be required.

## Repository contents

- `BERN02_Project.ipynb` — data analysis, experiments, and evaluation.
- `README.md` — project overview and instructions.
- `LICENSE` — repository licence.

## Licence and attribution

Original code and documentation authored for this repository are released under the **MIT License**; see [LICENSE](LICENSE).

**The MIT License does not apply to third-party bird photographs or source data.** Only images recorded as CC0, CC BY, or CC BY-SA were included. Each image remains subject to its own licence. Where required, preserve creator attribution, licence information, source links, and notices of modifications. CC BY-SA may impose additional share-alike requirements on adaptations.

The dataset was obtained through a GBIF occurrence download:

> GBIF.org (15 October 2026). GBIF Occurrence Download. https://doi.org/10.15468/dl.pfd9ab

When redistributing images, check the associated metadata and licence conditions. For more information, see the [Creative Commons licence guidance](https://creativecommons.org/share-your-work/cclicenses/) and the [GBIF data user agreement](https://www.gbif.org/terms/data-user).

## Authors

Sek Huen Leung and Kadri Kalamäe





