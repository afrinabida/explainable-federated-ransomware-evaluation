# Reproducibility and publication checklist

## Windows PowerShell commands

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
$env:RAW_DATA_DIR = 'D:\research-datasets'
jupyter lab
```

Open `notebooks/cross_platform_fl_evaluation.ipynb`, inspect dataset paths, and run top-to-bottom.

## Experimental settings read from notebook

- Seeds: `2026, 2027, 2028, 2029, 2030` in full mode.
- `FED_ROUNDS=20`, `FED_LOCAL_STEPS=100`, `FED_BATCH=128`, `FED_LR=1e-3`.
- `FXGB_ROUNDS=20`, `FXGB_LOCAL_TREES=5`.
- `QUICK=1` reduces work and **must not** be used to reproduce reported paper metrics.
- Default output folder: `working/Full_Pipeline_Results/`.

## Before claiming reproducibility

- [ ] Record actual Python and package versions (`pip freeze > environment-lock.txt`).
- [ ] Verify exact raw dataset versions, licences, provenance, and SHA256 checksums.
- [ ] Test a full run from a clean environment, with no cached intermediate outputs.
- [ ] Check all manuscript tables and figures against regenerated results.
- [ ] Audit train/validation/test group isolation and threshold calibration.
- [ ] Confirm that no passwords, API tokens, personal paths, or restricted data are present.
- [ ] Add a code licence and final author metadata.
- [ ] Tag the paper version (e.g. `v1.0.0`) and archive that tag using Zenodo if desired.

This package was assembled from the supplied notebook without executing the full experiments. It is **not** a claim of verified end-to-end reproducibility.
