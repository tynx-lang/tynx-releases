# Tynx Releases & Public Issue Tracker

Welcome to the public releases and issue tracker repository for **Tynx** — the high-fidelity TypeScript-to-Kotlin/JVM compiler.

> **Note**: This public repository is dedicated exclusively to public release distributions, binary downloads, issue tracking, and community support. The core compiler source code is developed and maintained in a private repository.

---

## Quick Installation

### macOS & Linux

Install or update the official Tynx native CLI compiler with a single command:

```bash
curl -fsSL https://tynx.dev/install.sh | sh
```

Verify your installation:

```bash
tynx --version
# Expected output: tynx 1.0.0 (<target-triple>)
```

### Direct Binary Downloads

Pre-built native binaries and SHA-256 checksums are published with every release on GitHub:

* **[Browse All Releases](https://github.com/tynx-lang/tynx-releases/releases)**
* Supported Platforms:
  * **macOS Apple Silicon** (`aarch64-apple-darwin`)
  * **macOS Intel** (`x86_64-apple-darwin`)
  * **Linux x64 glibc** (`x86_64-unknown-linux-gnu`)
  * **Linux ARM64** (`aarch64-unknown-linux-gnu`)
  * **Windows x64** (`x86_64-pc-windows-msvc.zip`)

See [INSTALL.md](./INSTALL.md) for detailed platform-specific installation instructions and manual checksum verification.

---

## Reporting Issues & Feedback

We welcome community feedback, bug reports, and feature suggestions through our public issue tracker:

* **[Report a Bug](https://github.com/tynx-lang/tynx-releases/issues/new?template=bug_report.yml)**
* **[Installation Problems](https://github.com/tynx-lang/tynx-releases/issues/new?template=installation_problem.yml)**
* **[Feature Requests](https://github.com/tynx-lang/tynx-releases/issues/new?template=feature_request.yml)**
* **[View Existing Issues](https://github.com/tynx-lang/tynx-releases/issues)**

> **Important**: Never include credentials, API keys, private source code, or confidential proprietary assets in public GitHub issues.

---

## Private Compiler Diagnostics

If you encounter lowering anomalies or diagnostic errors while using the [Interactive Playground](https://tynx.dev/playground), you can also submit confidential, private diagnostic reports directly to the engineering team using the in-editor **Send private feedback** action or the web feedback portal at [tynx.dev/feedback](https://tynx.dev/feedback).

---

## Security Vulnerabilities

Please report security concerns responsibly according to our [Security Policy](./SECURITY.md). Do not file public GitHub issues for security vulnerabilities.

---

## License

Tynx V1 is distributed under the Free Edition and Founder Edition terms. See [tynx.dev/license](https://tynx.dev/license) for licensing details.
