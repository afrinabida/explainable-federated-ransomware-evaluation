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

- `notebooks/cross_platform_fl_evaluation.ipynb`: research pipeline (outputs cleared for publication).
- `requirements.txt`: main Python dependencies, **not an environment lockfile**.
- `DATASETS.md`: expected raw inputs and dataset-access cautions.
- `REPRODUCIBILITY.md`: run procedure, thresholds, and verification checklist.
- `CITATION.cff`: metadata template; fill in real authors before release.
- `.gitignore`: excludes raw data, generated results, and local environments.

## Running

1. Use Python 3.11 (recommended starting point; the exact original environment has not been verified).
2. Create an environment and install `requirements.txt`.
3. Obtain each dataset from its original provider and review the terms of use. **Raw datasets are not bundled.**
4. Place raw data in a local directory and set `RAW_DATA_DIR` to its absolute path, or attach datasets in Kaggle under `/kaggle/input`.
5. Open the notebook and run cells in order. The notebook creates `working/` and `working/Full_Pipeline_Results/`.

**Important:** This notebook was authored for a Kaggle-style environment and has not been rerun or fully validated as a clean-room reproduction from this package. Input discovery may require adjustment to the original dataset layouts. A smoke run with `QUICK=1` is **not** equivalent to the published full experiments.

## Evidence and interpretation

The manuscript reports experiments across five seeds (2026–2030). Windows fixed-horizon detection uses separately validation-calibrated thresholds by horizon, while sequential first-alert timing uses one threshold calibrated at 30 s. Do not conflate these evaluation protocols. Windows pre-alert write volume is a **proxy**, not verified encrypted or prevented bytes.

Do not claim that results in the paper were independently reproduced from this package until a clean-environment rerun confirms them.

## Availability and licence

The authors retain copyright unless a licence is explicitly added. **No open-source licence is granted by this package.** Before publishing, choose and add an appropriate licence (e.g. MIT for original code) after checking third-party dependencies, rights, and institutional policies. Dataset licences are separate.

## Contact

Add corresponding-author contact information before public release.
