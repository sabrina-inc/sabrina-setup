# Sabrina Setup

The installer for Sabrina on your computer. This repository holds **releases only** — the packages, their checksums and the release notes. There is no source here.

## Install

1. Download the package for your computer from the [latest release](../../releases/latest):
   - **Windows** — `sabrina-setup-<version>-windows-amd64.msi`
   - **macOS** — `sabrina-setup-<version>-macos.pkg`
2. Run it. Then open **Sabrina Setup** (Start menu on Windows, Applications on macOS) and follow the screens: it checks this computer, asks for the **invite code** your administrator sent you, shows a short code, and waits while your administrator approves from Slack. No terminal, no commands.
3. Your administrator sends the invite code with the link to this page. If you do not have one, ask them before you start.

While a release is marked **pre-release** the package is not yet signed on every platform: Windows may show *Windows protected your PC* — choose **More info → Run anyway** — and macOS may ask you to allow the package from **System Settings → Privacy & Security**.

## Verify a download

Every release carries `sabrina-setup-<version>-SHA256SUMS.txt`. In the folder you downloaded to:

```
# macOS
shasum -a 256 -c sabrina-setup-<version>-SHA256SUMS.txt
# Windows (PowerShell)
Get-FileHash .\sabrina-setup-<version>-windows-amd64.msi -Algorithm SHA256
```

The Windows hash must match the line for the `.msi` in the sums file.

## Support

Ask your administrator. This repository does not take issues or pull requests.
