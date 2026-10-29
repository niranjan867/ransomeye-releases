# RansomEye Official Releases

This repository hosts official compiled Windows binary releases for **RansomEye**, served directly via GitHub Pages for frictionless HTTPS downloads.

* **GitHub Pages Site**: [https://niranjan867.github.io/ransomeye-releases/](https://niranjan867.github.io/ransomeye-releases/)
* **Direct EXE Download**: [https://niranjan867.github.io/ransomeye-releases/RansomEye.exe](https://niranjan867.github.io/ransomeye-releases/RansomEye.exe)
* **Main Source Repository**: [https://github.com/niranjan867/RansomEye](https://github.com/niranjan867/RansomEye)

---

## Current Release: v1.0.0-rc.3

* **Artifact Name**: `RansomEye.exe`
* **Target Architecture**: Windows 10/11 x64 (AMD64)
* **File Size**: 21,100,919 bytes (20.12 MB)
* **SHA-256 Checksum**:
  ```text
  F22F93B2A5855FA906CF8816EB893D77769FCE095216E5B36A55F251C11CB871
  ```

---

## Download & Verification

### 1. Download via PowerShell
```powershell
Invoke-WebRequest -Uri "https://niranjan867.github.io/ransomeye-releases/RansomEye.exe" -OutFile "RansomEye.exe"
```

### 2. Verify SHA-256 Checksum
Always verify the integrity of the downloaded executable against the published SHA-256 hash before running:
```powershell
(Get-FileHash .\RansomEye.exe -Algorithm SHA256).Hash -eq "F22F93B2A5855FA906CF8816EB893D77769FCE095216E5B36A55F251C11CB871"
```
The command should return `True`.

### 3. Usage
`RansomEye.exe` is a standalone, portable Windows application. No installer or administrative service setup is required. You can launch it directly from PowerShell, Windows Terminal, or Command Prompt:
```cmd
.\RansomEye.exe
```

---

## Repository Separation & Architecture

To ensure fast, reliable, direct-to-binary distribution without landing page redirects or external third-party download intermediaries:
* **Source Code Repository** (`niranjan867/RansomEye`): Contains the Python codebase, forensics engines, test suites, and documentation.
* **Release Distribution Repository** (`niranjan867/ransomeye-releases`): A dedicated distribution repository configured with GitHub Pages to serve `RansomEye.exe` directly over HTTPS.

---

## Publishing Future Releases

When a new release candidate or production build is ready:
1. Copy the new release executable to the repository root as `RansomEye.exe`.
2. Compute the new SHA-256 checksum:
   ```powershell
   Get-FileHash .\RansomEye.exe -Algorithm SHA256
   ```
3. Update `README.md` and `index.html` with the new version tag, file size, and SHA-256 checksum.
4. Stage only the release files:
   ```bash
   git add RansomEye.exe index.html README.md .nojekyll
   git commit -m "Publish RansomEye <version> Windows release"
   git push origin main
   ```
5. Allow GitHub Pages ~1-2 minutes to deploy the updated build.

---

## License & Issues

* Project issues and bug reports: [RansomEye Issue Tracker](https://github.com/niranjan867/RansomEye/issues)
* Privacy policy: [Privacy Policy](https://github.com/niranjan867/RansomEye/blob/main/PRIVACY.md)
