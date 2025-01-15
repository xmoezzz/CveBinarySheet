# CveBinarySheet: A Comprehensive Pre-built Binaries Database Focused on IoT Vulnerability Scenarios

**CveBinarySheet**, a dataset designed to help researchers and developers rapidly build **state-of-the-art (SOTA) binary SCA**, **binary similarity analysis**, and **binary vulnerability matching tools**. We provide pre-built binaries for various CPU architectures used in IoT, UEFI, and MCU firmware, along with detailed information about each CVE.

---

## Overview

- **Pre-built Binaries**: All binaries are compiled based on **Arch Linux AUR** packages.
- **Current Scope**: 
  - Over **1334** CVE entries.
  - Focused on common IoT/UEFI/MCU firmware vulnerabilities.
- **Folders**:
  - **cve-compilation**: Contains compilation scripts for each CVE.
  - **cve-map**: Contains JSON files with detailed information about each CVE.
- **Pre-built Binaries**: Available in multiple datasets (see [Datasets](#datasets)).

---

## Supported Architectures

The following architectures are currently supported and cover most CPU targets found in IoT devices, UEFI firmware, and MCU firmware:

- **x86-64**
- **i386**
- **mips**
- **armv7**
- **riscv**

---

## Included CVEs

There are **1334** CVE entries included. Each entry provides:
- CVE identifier
- Affected software version range
- Potentially affected functions (extracted using [tree-sitter](https://tree-sitter.github.io/tree-sitter/))
- Links to patches, commits, or further information

---

## Directory Structure

```plaintext
.
├── cve-compilation/
│   ├── <LIB>/<VERSION>
│   │   ├── build.sh
│   │   └── ...
│   └── ...
└── cve-map/
    ├── CVE-XXXX-XXXX.json
    ├── CVE-XXXX-YYYY.json
    └── ...
```

- **cve-compilation**: Houses the compilation scripts used to build binary files for each CVE.
- **cve-map**: Contains individual JSON files, each mapping to a specific CVE. These JSON files include details about the vulnerability such as the CVE number, patch information, affected files, function names, and more.

---

## Third-Party Components

This project includes pre-built versions of the following components:

- `busybox`
- `coreutils`
- `curl`
- `ffmpeg`
- `imagemagick`
- `libpcap`
- `libpng`
- `libtiff`
- `libuv`
- `libxml2`
- `lua`
- `mbedtls`
- `mutt`
- `openvpn`
- `openssl`
- `wget`

---

## How to Use

Inside the **cve-map** folder, each JSON file records detailed information about a specific vulnerability:

- **cve_name**: The CVE identifier (e.g., `CVE-2025-XXXX`).
- **patch_url**: URL to the patch or commit that fixes this vulnerability.
- **reaching_path**: Link(s) with additional information (often the NVD listing).
- **function_names**: The functions impacted by the vulnerability (extracted via Tree-sitter).
- **affected_version**: The version range affected by this CVE.
- **binary_version**: The specific version used to compile our pre-built binaries for this vulnerability.
- **old_files** and **new_files**: A list of file paths and line ranges that changed before/after the patch, also extracted using Tree-sitter.

Feel free to explore these JSON files to find information about specific vulnerabilities. The corresponding pre-built binaries (for each architecture) are listed in our datasets.

---

## Datasets

We host all pre-built binaries on multiple datasets for easier access.
* [Kaggle](https://www.kaggle.com/datasets/anzzzzzzzzu/cvebinarysheet)
* [Zenodo](https://zenodo.org/record/5810737)

---

## Contributing

We welcome contributions, such as:
- Adding new CVE information or correcting existing data
- Submitting additional compilation scripts
- Providing improvements or enhancements to existing scripts

To contribute, please open a [pull request](../../pulls) or file an [issue](../../issues). We appreciate your help in expanding and refining this resource!

