# Retouch — releases

Installers and update metadata for **Retouch**, a precision-first desktop image
editor for Windows.

This repository is **binary distribution only**. It exists so that Retouch can
be downloaded and updated without handing out the application source.

## What is here

Nothing in the file tree but this README. Everything that matters is on the
[Releases](../../releases) page:

| Asset | What it is |
| --- | --- |
| `Retouch-Setup-<version>-x64.exe` | The Windows installer (NSIS, per-user) |
| `Retouch-Setup-<version>-x64.exe.blockmap` | Lets the updater download only changed blocks |
| `latest.yml` | Update feed for the stable channel |
| `beta.yml` | Update feed for the beta channel, when a beta is published |
| `SHA256SUMS.txt` | Checksums for manual verification |

The application's built-in updater reads `latest.yml` (or `beta.yml`) from here.

## What is deliberately not here

- application source code
- build scripts, tests or CI configuration
- development history
- issues and roadmap

Those live in a separate private repository, which is never mirrored here. A
release lands as built artefacts only.

## Status

**Beta.** This repository is currently private while Retouch is
owner-and-invitee only. When Retouch is ready for general use, *this* repository
can be made public so that anyone can download and receive updates — the source
repository stays private permanently.

## Verifying a download

```powershell
Get-FileHash .\Retouch-Setup-<version>-x64.exe -Algorithm SHA256
```

Compare the result with the matching line in `SHA256SUMS.txt` on the same
release.

## Installers are not code-signed yet

Windows SmartScreen will warn on first run, and the updater can verify the
SHA-512 checksum but not a publisher signature. Signing is planned before
general availability.

## Support

Please report problems through the channel you were given access by. Issues are
tracked in the private development repository, not here.
