# SonicDB

macOS builds of SonicDB, a desktop SQL workbench for PostgreSQL and ClickHouse. This repository hosts releases only; the source code is private.

## Install

On a Mac with Apple Silicon or Intel, open Terminal and run:

```sh
curl -fsSL https://github.com/mkakim95/sonicdb-releases/releases/latest/download/install.sh | bash
```

The installer downloads the latest release, checks it against its published SHA-256, and puts `SonicDB.app` in `/Applications`, or in `~/Applications` when `/Applications` is not writable. It does not use `sudo`.

To update, quit SonicDB and run the same command again. After an update, macOS may ask once per saved password before SonicDB can read it from Keychain.

SonicDB has no Developer ID signature. A copy installed with the command above opens normally. A zip downloaded with a web browser is quarantined, and macOS refuses to open it; use the command instead.

## Uninstall

Move `SonicDB.app` to the Trash. Connection profiles, query history and settings stay in `~/Library/Application Support/com.sonicdb.app`, and saved passwords stay in Keychain under `com.sonicdb.app.connections`. Delete those too to remove everything.

## Release files

Each release carries three files:

- `SonicDB-macos-universal.zip`: the app, for Apple Silicon and Intel
- `SonicDB-macos-universal.zip.sha256`: its checksum
- `install.sh`: the installer used by the command above
