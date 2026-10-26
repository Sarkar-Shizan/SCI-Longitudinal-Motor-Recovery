# Publish checklist

1. Review repository contents (especially notebook code) and confirm that none reveal credentials, identifiable clinical information, or confidential paths. All notebook outputs have been stripped; code has not been rewritten.
2. Confirm ethical, contractual, and copyright terms of source Sygen data and derived outputs.
3. Start with a **private** GitHub repository.
4. Extract this ZIP. Upload extracted files/folders via GitHub UI, or from the extracted root run:

```bash
git init
git add .
git status
git commit -m "Initial SCI prognostic modelling research artifacts"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/SCI-Longitudinal-Motor-Recovery.git
git push -u origin main
```

5. Inspect `git status` / `git ls-files` to ensure no patient-level source files have been tracked; `.gitignore` protects against accidental additions but does not erase anything already committed.
6. Add a license only after deciding on terms and permissions.
7. The notebook is archival; validate installation, dataset acquisition and end-to-end reproducibility separately before claiming a runnable release.
