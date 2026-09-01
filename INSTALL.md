# Tynx Installation Guide

This guide covers installing and verifying the official Tynx native CLI compiler on supported platforms.

---

## 1. Automated Installation (macOS & Linux)

The official installer detects your operating system and architecture, downloads the release archive, verifies its SHA-256 checksum, and installs the binary to `$HOME/.tynx/bin`:

```bash
curl -fsSL https://tynx.dev/install.sh | sh
```

### Environment Configuration

Add the binary directory to your PATH (if not already present in your shell profile):

```bash
export PATH="$HOME/.tynx/bin:$PATH"
```

Verify your installation:

```bash
tynx --version
```

---

## 2. Manual Installation & Verification

### Step 1: Download Archive and SHA256SUMS

Download the appropriate archive for your platform from [Releases](https://github.com/tynx-lang/tynx-releases/releases):

| Platform | Target Triple | Archive |
|---|---|---|
| macOS Apple Silicon | `aarch64-apple-darwin` | `tynx-v0.32.0-aarch64-apple-darwin.tar.gz` |
| macOS Intel | `x86_64-apple-darwin` | `tynx-v0.32.0-x86_64-apple-darwin.tar.gz` |
| Linux x64 (glibc) | `x86_64-unknown-linux-gnu` | `tynx-v0.32.0-x86_64-unknown-linux-gnu.tar.gz` |
| Linux x64 (musl) | `x86_64-unknown-linux-musl` | `tynx-v0.32.0-x86_64-unknown-linux-musl.tar.gz` |
| Linux ARM64 | `aarch64-unknown-linux-gnu` | `tynx-v0.32.0-aarch64-unknown-linux-gnu.tar.gz` |
| Windows x64 | `x86_64-pc-windows-msvc` | `tynx-v0.32.0-x86_64-pc-windows-msvc.zip` |

### Step 2: Verify SHA-256 Checksum

On macOS:
```bash
shasum -a 256 tynx-v0.32.0-<target-triple>.tar.gz
```

On Linux:
```bash
sha256sum tynx-v0.32.0-<target-triple>.tar.gz
```

Compare the computed checksum against the matching entry in `SHA256SUMS`.

### Step 3: Extract and Install

```bash
tar -xzf tynx-v0.32.0-<target-triple>.tar.gz
mkdir -p ~/.tynx/bin
mv tynx ~/.tynx/bin/
chmod +x ~/.tynx/bin/tynx
```
