# QuCl private runtime backup

Download the installed runtime from the [2026-11-05 release](https://github.com/johnlimmm/backup/releases/tag/runtime-2026-11-05). The large archive is attached to the release, rather than stored in Git history.

## Included environment

- Python 3.7.17, NetSquid 1.1.7, PyDynAA 1.0.2 and installed scientific dependencies.
- Python 3.10.12 with Matplotlib 3.8.4 for plotting.
- QuCl source and compiled ns-3 3.47 / Q2NS participants and native tests.
- Relative-path launchers, a package/version manifest and file checksums.

Use Ubuntu 22.04 x86-64 as the reference destination. This is a runnable application environment; the complete OS image and C++ development toolchain are not included. No NetSquid download or package installation is required to run the included examples.

## Restore on another PC

Sign in to GitHub and download both `qucl-runtime-linux-x86_64.tar.gz` and `qucl-runtime-linux-x86_64.tar.gz.sha256` from the release. Then run:

```bash
sha256sum -c qucl-runtime-linux-x86_64.tar.gz.sha256
tar -xzf qucl-runtime-linux-x86_64.tar.gz
cd qucl-runtime
./check.sh
./run-example.sh
```

For the complete test suite:

```bash
./run-tests.sh
```

The included `README.txt` explains other scenarios, experiment commands and the export procedure. The release also includes the environment manifest, verification summary and verification log.

## Verification

The archive was tested after relocation to `/opt/qucl`, with the original home directory and system Python standard-library directories hidden and external networking disabled. Both Python environments passed dependency checks, a plot was rendered, the chained Swap-to-Teleport example passed its independent reference check, and all 81 Python tests plus 83 Q2NS native test cases passed. A different physical PC has not yet been tested.

Archive SHA-256:

```text
43bf4391d361cec7b928b505fb9827bc5e8684351cb01c74626f5e80e8045f40
```

Keep this repository private. The archive contains the installed NetSquid distribution and is for private environment recovery. Third-party software retains its original licensing terms.
