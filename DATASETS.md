# Dataset acquisition and expected inputs

Do not redistribute third-party raw datasets without verifying each licence and redistribution terms.

- **RanSAP (Windows):** original execution folders containing `ata_read.csv` and `ata_write.csv`; the notebook also uses preprocessed `ransap_train.csv` and `ransap_test.csv` if present. Dataset citation: Hirano et al. (verify exact original URL in manuscript bibliography).
- **DroidRan (Android):** Excel workbooks (`.xlsx`/`.xls`), expected stage sheets and the column layout encoded in the notebook. The notebook expects the dataset's original folder hierarchy for attack-vector and family identification. Check the original dataset CC BY 4.0 licence and attribution requirements.
- **Linux ftrace:** `isitencrypted_dataset.csv` function-graph traces; the notebook builds process-level features and trace-prefix features. Verify the original repository, publication, label provenance, and redistribution permissions before publishing links or derived data.

The notebook searches Kaggle `/kaggle/input`, `RAW_DATA_DIR`, and `working/`. It uses some Kaggle-specific hints. Ensure exact original dataset versions and checksums are recorded for reproducibility.
