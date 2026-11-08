# GitHub upload: step by step

1. Review the notebook and files; remove secrets, personal paths, restricted data, and unsupported claims. Add a code licence after confirming rights. Update `CITATION.cff` with real author details.
2. Sign in to GitHub; select **New repository**. Suggested name: `explainable-federated-ransomware-evaluation`.
3. Set visibility to **Private** while reviewing; switch to **Public** only after the checks. Do **not** initialise with README, licence, or `.gitignore` (this package already has README and gitignore).
4. Extract this ZIP on your computer and open the folder in VS Code.
5. In VS Code terminal (PowerShell):

```powershell
git init
git branch -M main
git add .
git status
git commit -m "Add research evaluation notebook and documentation"
git remote add origin https://github.com/YOUR_USERNAME/explainable-federated-ransomware-evaluation.git
git push -u origin main
```

6. Check the repository in a browser. Ensure datasets, generated results, and sensitive material are absent. Check README and notebook render correctly.
7. Test the code from a clean environment and verify manuscript results. Add a `LICENSE` file and final citation metadata.
8. Create a tagged GitHub Release (e.g. `v1.0.0`). Optionally connect GitHub to Zenodo and archive the release to get a DOI.
9. After public release, use the **real** URL in the paper's `Data and Code Availability` section.

## LaTeX text (only after repository is public)

```latex
\section*{Data and Code Availability}
The datasets analysed in this study are available from their respective original sources. The research code for preprocessing, model training, federated evaluation, and explainability analysis is available at \url{https://github.com/YOUR_USERNAME/explainable-federated-ransomware-evaluation}. Dataset access and reproduction instructions are provided in the repository.
```

Replace the placeholder URL with the actual working link. Do not say the code is public before publication.
