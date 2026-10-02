# AI for Sustainability: Hands-on Labs

[![License: CC BY 4.0](https://img.shields.io/badge/Content-CC%20BY%204.0-lightgrey.svg)](LICENSE-CONTENT)
[![License: MIT](https://img.shields.io/badge/Code-MIT-blue.svg)](LICENSE)
[![Colab](https://img.shields.io/badge/Run%20in-Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)](#labs)
![Level](https://img.shields.io/badge/Level-Undergraduate-green)

Six Colab-ready Jupyter labs that take undergraduate students from their first line of Python to fine-tuning a **geospatial foundation model** for flood mapping. Every lab is built around a real sustainability problem and real open data: food security, biodiversity, surface water, river discharge and floods.

Developed for the undergraduate course **AI for Sustainability** at the **University of Wisconsin–Madison** (Nelson Institute), taught by **Dr. Beth Tellman**.
Labs designed and co-taught by **[Saurabh Kaushik](https://sk-2103.github.io)**.

---

## Labs

| # | Lab | Sustainability theme | Method | Data | Open | Assessment |
|---|-----|---------------------|--------|------|------|------------|
| 01 | [Python & Jupyter basics](labs/lab01_python_basics/lab01_python_basics.ipynb) | Foundations | Python, data types, control flow, functions | None | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab01_python_basics/lab01_python_basics.ipynb) | [Evaluation](labs/lab01_python_basics/lab01_evaluation.ipynb) |
| 02 | [Random Forest for crop yield](labs/lab02_random_forest_crop_yield/lab02_random_forest_crop_yield.ipynb) | Food security | Random Forest regression, time-based split, feature importance | FAOSTAT maize yield + World Bank indicators | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab02_random_forest_crop_yield/lab02_random_forest_crop_yield.ipynb) | [Evaluation](labs/lab02_random_forest_crop_yield/lab02_evaluation.ipynb) |
| 03 | [Artificial Neural Networks](labs/lab03_ann_biodiversity/lab03_ann_biodiversity.ipynb) | Biodiversity | Perceptron, MLP, activations, over/underfitting (PyTorch) | Iris species morphometrics | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab03_ann_biodiversity/lab03_ann_biodiversity.ipynb) | [Evaluation](labs/lab03_ann_biodiversity/lab03_evaluation.ipynb) |
| 04 | [CNNs for surface water mapping](labs/lab04_cnn_surface_water/lab04_cnn_surface_water.ipynb) | Water resources | NDWI baseline, tiny CNN, U-Net segmentation (TorchGeo) | Earth Surface Water (Sentinel-2) | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab04_cnn_surface_water/lab04_cnn_surface_water.ipynb) | [Evaluation](labs/lab04_cnn_surface_water/lab04_evaluation.ipynb) |
| 05 | [LSTM streamflow forecasting](labs/lab05_lstm_streamflow/lab05_lstm_streamflow.ipynb) | Hydrology | LSTM, sliding windows, chronological splits, NSE/KGE | USGS gauge 05397500 (Wisconsin River) + Daymet | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab05_lstm_streamflow/lab05_lstm_streamflow.ipynb) | [Evaluation](labs/lab05_lstm_streamflow/lab05_evaluation.ipynb) |
| 06 | [Geospatial Foundation Models](labs/lab06_gfm_flood_mapping/lab06_gfm_flood_mapping.ipynb) | Floods | Self-supervised learning, ViT/MAE, fine-tuning TerraMind (TerraTorch), S1+S2 fusion | Sen1Floods11 | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Sk-2103/AI4Sustainability-Labs/blob/main/labs/lab06_gfm_flood_mapping/lab06_gfm_flood_mapping.ipynb) | [Evaluation](labs/lab06_gfm_flood_mapping/lab06_evaluation.ipynb) |

**Learning arc:** Python → classical ML → neural networks → convolutional networks for imagery → recurrent networks for time series → foundation models.

## What makes these labs different

- **Real problems, real data.** Every model is trained on open, authoritative sources (FAO, World Bank, USGS, Daymet, Sentinel-1/2), not toy examples.
- **Physics before parameters.** Students compute a physically based baseline (e.g. NDWI) before training a network, and compare against it.
- **Honest evaluation.** Time-based splits to avoid leakage, and domain metrics (IoU/F1 for segmentation, NSE/KGE/PBIAS for hydrology).
- **Up to the research frontier.** The final lab fine-tunes a current multimodal geospatial foundation model (IBM/ESA TerraMind) on a free Colab GPU.
- **Ready to teach.** Each lab has a matching graded assessment (theory + fill-in-the-blank coding, 20–25 marks) with a marking breakdown.

## Getting started

**Google Colab (recommended).** Click any *Open in Colab* badge, then **File → Save a copy in Drive**. Labs 04–06 need a GPU: **Runtime → Change runtime type → T4 GPU**. Each notebook installs its own dependencies in the first cell.

**Locally.**
```bash
git clone https://github.com/Sk-2103/AI4Sustainability-Labs.git
cd AI4Sustainability-Labs
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```
Lab 06 pins specific versions (`terratorch==1.2.6`, `numpy==1.26.4`) and is easiest to run on Colab.

## Repository structure

```
AI4Sustainability-Labs/
├── labs/
│   ├── lab01_python_basics/           lab + evaluation notebook
│   ├── lab02_random_forest_crop_yield/
│   ├── lab03_ann_biodiversity/
│   ├── lab04_cnn_surface_water/
│   ├── lab05_lstm_streamflow/
│   └── lab06_gfm_flood_mapping/
├── requirements.txt
├── CITATION.cff
├── LICENSE            (MIT, code)
└── LICENSE-CONTENT    (CC BY 4.0, text, figures, assessments)
```

## For instructors

You are welcome to adopt these labs. Evaluation notebooks are published **without solutions**; instructors who would like answer keys can contact the author from a university email address. If you use the materials, a short note or a GitHub star helps us track impact.

## Data and acknowledgements

Datasets belong to their providers: [FAOSTAT](https://www.fao.org/faostat/), [World Bank WDI](https://data.worldbank.org/), [UCI Iris](https://archive.ics.uci.edu/dataset/53/iris), [Earth Surface Water](https://github.com/xinluo2018/WatNet) via [TorchGeo](https://torchgeo.readthedocs.io/en/stable/tutorials/earth_surface_water.html), [USGS NWIS](https://waterdata.usgs.gov/), [Daymet](https://daymet.ornl.gov/), and [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11) (Bonafilia et al., 2020). Lab 04 is adapted from the TorchGeo *Earth Surface Water* tutorial. Lab 06 uses [TerraTorch](https://github.com/IBM/terratorch) and [TerraMind](https://huggingface.co/ibm-esa-geospatial).

## Citation

If you use or adapt these materials, please cite:

```bibtex
@misc{kaushik2026ai4sustainabilitylabs,
  author       = {Kaushik, Saurabh and Tellman, Beth},
  title        = {{AI for Sustainability: Hands-on Labs}},
  year         = {2026},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/Sk-2103/AI4Sustainability-Labs}},
  note         = {Undergraduate course materials, University of Wisconsin--Madison}
}
```

## Contact

Saurabh Kaushik · [sk-2103.github.io](https://sk-2103.github.io) · [LinkedIn](https://www.linkedin.com/in/saurabh-kaushik-552613129) · [GitHub](https://github.com/Sk-2103)

Issues and pull requests (typo fixes, broken links, new labs) are welcome.
