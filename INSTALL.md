# Tynx Installation Guide

Tynx is a high-fidelity native compiler that translates a supported subset of TypeScript directly into idiomatic Kotlin/JVM code for execution on the Java Virtual Machine.

The current official production release is **Tynx v1.0.0**.

---

## 1. Automated Installation

### macOS & Linux

The official installer automatically detects your operating system and CPU architecture, downloads the release archive, verifies its cryptographic SHA-256 checksum, and installs the binary to `$HOME/.tynx/bin`:

```bash
curl -fsSL https://tynx.dev/install.sh | sh
```

#### Environment Configuration

Ensure the binary directory is added to your shell `PATH`:

```bash
export PATH="$HOME/.tynx/bin:$PATH"
```

Verify your installation:

```bash
tynx --version
# Expected output: tynx 1.0.0 (<target-triple>)
```

### Windows (PowerShell)

Install via the official PowerShell installer:

```powershell
irm https://tynx.dev/install.ps1 | iex
```

---

## 2. Manual Installation & Verification

### Step 1: Download Archive and SHA256SUMS

Download the appropriate archive and `SHA256SUMS` manifest from [GitHub Releases](https://github.com/tynx-lang/tynx-releases/releases):

| Platform | Target Triple | Archive |
|---|---|---|
| macOS Apple Silicon | `aarch64-apple-darwin` | `tynx-v1.0.0-aarch64-apple-darwin.tar.gz` |
| macOS Intel | `x86_64-apple-darwin` | `tynx-v1.0.0-x86_64-apple-darwin.tar.gz` |
| Linux x64 (glibc) | `x86_64-unknown-linux-gnu` | `tynx-v1.0.0-x86_64-unknown-linux-gnu.tar.gz` |
| Linux ARM64 | `aarch64-unknown-linux-gnu` | `tynx-v1.0.0-aarch64-unknown-linux-gnu.tar.gz` |
| Windows x64 | `x86_64-pc-windows-msvc` | `tynx-v1.0.0-x86_64-pc-windows-msvc.zip` |

### Step 2: Verify SHA-256 Checksum

Before extracting or executing the binary, verify the archive SHA-256 checksum against `SHA256SUMS`:

On macOS:
```bash
shasum -a 256 tynx-v1.0.0-<target-triple>.tar.gz
```

On Linux:
```bash
sha256sum tynx-v1.0.0-<target-triple>.tar.gz
```

On Windows (PowerShell):
```powershell
Get-FileHash .\tynx-v1.0.0-x86_64-pc-windows-msvc.zip -Algorithm SHA256
```

### Step 3: Extract and Install

#### macOS & Linux
```bash
tar -xzf tynx-v1.0.0-<target-triple>.tar.gz
mkdir -p ~/.tynx/bin
mv tynx ~/.tynx/bin/
chmod +x ~/.tynx/bin/tynx
```

#### Windows
Extract `tynx-v1.0.0-x86_64-pc-windows-msvc.zip` and move `tynx.exe` into a directory included in your system `%PATH%` (such as `%USERPROFILE%\.tynx\bin`).

---

## 3. Creating & Running Your First Project

Once installed, verify the compiler and initialize a new project:

### Initialize a New Project
```bash
tynx init my-app
cd my-app
```

This scaffolds:
* `tynx.json` — Project compiler configuration
* `src/main.ts` — TypeScript entrypoint
* `.gitignore` — Ignore build outputs

### Type Check
```bash
tynx check
```

### Compile to Kotlin
```bash
tynx build
```

The emitted Kotlin source files will be written to `dist/`.

### Run Project
```bash
tynx run
```

Compiles the TypeScript entrypoint, builds JVM bytecode with `kotlinc`, and executes on the JVM.

---

## 4. Historical Releases

Previous releases (such as initial public release `v0.32.0`) are archived in the [Releases](https://github.com/tynx-lang/tynx-releases/releases) repository and remain immutable historical references.
