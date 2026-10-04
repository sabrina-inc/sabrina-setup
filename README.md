# Sabrina Setup

The installer for Sabrina on your computer. This repository holds **releases only** — the packages, their checksums and the release notes. There is no source here.

## Install

**The short way.** These two links always point at the current version:

- **Mac:** https://github.com/sabrina-inc/sabrina-setup/releases/download/current/sabrina-setup-mac.pkg
- **Windows:** https://github.com/sabrina-inc/sabrina-setup/releases/download/current/sabrina-setup-windows.msi

Download the one for your computer, run it, then open **Sabrina Setup** and follow the screens. Which version "current" is, and the checksums to verify it, are in the same place: https://github.com/sabrina-inc/sabrina-setup/releases/tag/current

**The long way**, if you want a specific version or Linux:

1. Download the package for your computer from the newest entry on the [releases page](https://github.com/sabrina-inc/sabrina-setup/releases), together with that release's `sabrina-setup-<version>-SHA256SUMS.txt`:
   - **Windows** — `sabrina-setup-<version>-windows-amd64.msi`
   - **macOS** — `sabrina-setup-<version>-macos.pkg`
   - **Linux** (command line only) — `sabrina-setup-<version>-linux-amd64.tar.gz` or `-linux-arm64.tar.gz`
2. **Verify it before you run it** (next section). Continue only if the check passes.
3. Run it. Then open **Sabrina Setup** (Start menu on Windows, Applications on macOS) and follow the screens: it checks this computer, asks for the **invite code** your administrator sent you, shows a short code, and waits while your administrator approves from Slack. No terminal, no commands. On Linux, unpack the tarball and run `./sabrina-setup` from a terminal.
4. Your administrator sends the invite code with the link to this page. If you do not have one, ask them before you start.

While a release is marked **pre-release** the package is not yet signed on every platform: Windows may show *Windows protected your PC* — choose **More info → Run anyway** — and macOS may ask you to allow the package from **System Settings → Privacy & Security**. Only do this for a package whose checksum you have verified.

## Verify a download

The sums file lists every package in the release. Check only the one you downloaded — in the folder you downloaded to:

```
# macOS
grep macos.pkg sabrina-setup-<version>-SHA256SUMS.txt | shasum -a 256 -c
# Linux, Intel/AMD
grep linux-amd64 sabrina-setup-<version>-SHA256SUMS.txt | sha256sum -c
# Linux, ARM
grep linux-arm64 sabrina-setup-<version>-SHA256SUMS.txt | sha256sum -c
# Windows (PowerShell)
Get-FileHash .\sabrina-setup-<version>-windows-amd64.msi -Algorithm SHA256
```

The Windows hash must match the line for the `.msi` in the sums file. A passing check proves the file is the one this release published; it is not a substitute for the platform signature, which is why pre-release builds still warn.

## Support

Ask your administrator. This repository does not take issues or pull requests.
