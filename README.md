# Audited Explainable Federated Learning for Cross-Platform Ransomware-Related Detection

Research implementation accompanying the manuscript **An Explainable Federated Learning Framework for Cross-Platform Early-Stage Ransomware Detection Using Heterogeneous Behavioral Datasets**.

## Scope and important limitations

The three datasets represent **different prediction tasks**, not one universal ransomware label:

| Platform | Dataset | Task |
|---|---|---|
| Windows | RanSAP | Ransomware vs benign execution from storage I/O |
| Android | DroidRan | Attack-in-progress vs clean pre-attack device state |
| Linux | ftrace | Encryption-related vs non-encryption process activity |

The notebook implements preprocessing and leakage audits, centralised and local models, within-platform federated XGBoost, cross-platform multi-task FedAvg, early-observation experiments, out-of-distribution tests, and explanation analyses. This is an **experimental research prototype**, not a deployed detector or a privacy guarantee. No secure aggregation or differential privacy is claimed.

## Repository contents

- `notebooks/code_ransomware.ipynb`: research pipeline (outputs cleared for publication).
- `requirements.txt`: main Python dependencies, **not an environment lockfile**.
- `DATASETS.md`: expected raw inputs and dataset-access cautions.
- `REPRODUCIBILITY.md`: run procedure, thresholds, and verification checklist.
- `.gitignore`: excludes raw data, generated results, and local environments.

## Running

1. Use Python 3.11 (recommended starting point; the exact original environment has not been verified).
2. Create an environment and install `requirements.txt`.
3. Obtain each dataset from its original provider and review the terms of use. **Raw datasets are not bundled.**
4. Place raw data in a local directory and set `RAW_DATA_DIR` to its absolute path, or attach datasets in Kaggle under `/kaggle/input`.
5. Open the notebook and run cells in order. The notebook creates `working/` and `working/Full_Pipeline_Results/`.

## Execution Environment

The experimental implementation was originally developed in a Kaggle-based environment. Researchers reproducing the experiments in other environments may need to configure dataset paths and dependencies according to their local setup.

The repository includes a quick execution mode for preliminary functionality checks. Full experimental reproduction requires the complete datasets, original evaluation configurations, and all specified random seeds.

The reported experimental results have not yet been independently verified through a clean-environment rerun.
## Experimental Protocol and Reproducibility

The experiments reported in the associated manuscript were conducted using five random seeds (2026–2030).

For Windows early-stage ransomware detection, fixed-horizon evaluation uses separately calibrated validation thresholds for each observation horizon. Sequential first-alert analysis uses a single threshold calibrated at the 30-second horizon.

Pre-alert write volume is used as a behavioral proxy and should not be interpreted as a direct measurement of encrypted or prevented data.

The repository provides the research implementation and supporting documentation. Independent reproducibility of the reported results has not yet been verified through a clean-environment rerun.

## Availability and licence

The source code is publicly available for research inspection. No licence for reuse, modification, or redistribution is granted at this time.
