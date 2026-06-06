# AutoKeyClick — Installers & Releases

Distribution repository for **[AutoKeyClick](https://github.com/MrParkerZ7/project-auto-key-click)** — a Windows automation tool for mouse-clicking and keyboard-input automation.

Each release lives under `vX.Y.Z/` with packaged artifacts and a `SHA256SUMS.txt`.

## Latest release — v1.0.0

| Artifact | File | Size | Use when… |
|----------|------|-----:|-----------|
| **Installer (recommended)** | [`AutoKeyClick-1.0.0-setup.exe`](v1.0.0/AutoKeyClick-1.0.0-setup.exe) | ~50 MB | You want a normal install: Start-menu shortcut, optional desktop icon, and an uninstaller. Shows the MIT license agreement during setup. |
| **Portable (zip)** | [`AutoKeyClick-1.0.0-win-x64-portable.zip`](v1.0.0/AutoKeyClick-1.0.0-win-x64-portable.zip) | ~64 MB | You want no install — unzip and run `AutoKeyClick.exe` anywhere. |
| **Portable (single exe)** | [`AutoKeyClick-1.0.0-win-x64.exe`](v1.0.0/AutoKeyClick-1.0.0-win-x64.exe) | ~70 MB | You want a single double-click file, no unzip. |
| **MSIX package** | [`AutoKeyClick-1.0.0.msix`](v1.0.0/AutoKeyClick-1.0.0.msix) | ~69 MB | You prefer the modern Windows app package (requires trusting the cert — see below). |
| **Signing certificate** | [`AutoKeyClick-1.0.0.cer`](v1.0.0/AutoKeyClick-1.0.0.cer) | — | Trust this to install the MSIX. |

All builds are **self-contained** (the .NET 8 runtime is bundled) and target **Windows x64** — no prerequisites required.

## Install instructions

### Installer (`-setup.exe`)
1. Download and run `AutoKeyClick-1.0.0-setup.exe`.
2. Read and accept the **MIT License agreement** on the license page.
3. Choose options (optional desktop icon) and finish. Installs per-user (no admin needed).
4. Launch from the Start menu. Uninstall via *Settings → Apps* or the Start-menu *Uninstall* entry.

### Portable (`.zip` or `.exe`)
- **Zip:** extract anywhere, then run `AutoKeyClick.exe`. Nothing is written to the registry; delete the folder to remove.
- **Single exe:** just double-click `AutoKeyClick-1.0.0-win-x64.exe`.

### MSIX (`.msix`)
The MSIX is signed with a **self-signed certificate**, so Windows needs to trust it first:
1. Download both `AutoKeyClick-1.0.0.msix` and `AutoKeyClick-1.0.0.cer`.
2. Right-click `AutoKeyClick-1.0.0.cer` → **Install Certificate** → *Local Machine* → place in **Trusted People** (or *Trusted Root Certification Authorities*). Admin rights required for this step.
3. Double-click `AutoKeyClick-1.0.0.msix` → **Install** via the App Installer.

> A self-signed certificate is used because this is an independent, open-source release. If you prefer not to trust a self-signed cert, use the installer or portable build instead.

## Verify your download

```powershell
Get-FileHash .\AutoKeyClick-1.0.0-setup.exe -Algorithm SHA256
```
Compare the output against `v1.0.0/SHA256SUMS.txt`.

## License & policy

AutoKeyClick is released under the **[MIT License](LICENSE)** — free to use, modify, and distribute, **with no warranty**. The installer presents this license for acceptance before installing.

**Acceptable-use note:** AutoKeyClick automates mouse and keyboard input. You are responsible for using it lawfully and in accordance with the terms of any software, game, or service you use it with. The authors accept no liability for misuse (see the MIT "AS IS" / no-liability clause).
