# Rivulet Scoop Bucket

[Scoop](https://scoop.sh) bucket for [Rivulet](https://github.com/thoser666/Rivulet) —
a free, open-source screen recorder and live streaming studio (MIT).

## Install

```powershell
scoop bucket add rivulet https://github.com/thoser666/scoop-bucket
scoop install rivulet/rivulet
```

## Update

```powershell
scoop update rivulet
```

## How this bucket is maintained

`bucket/rivulet.json` is generated from a GitHub release by the generator in the
main repository (`packaging/windows/generate-scoop-manifest.ps1`): the manifest
pins the portable ZIP asset URL plus its SHA-256, and the SHA-256 is taken from
the release's own `SHA256SUMS` asset — a manifest can never reference an
unverified binary. The CI dry-run job "Distribution Readiness → scoop" in the
main repo generates and byte-verifies the manifest for any release tag; the
verified file is then copied here (commit + push). Scoop requires no code
signing, so this channel works already, unlike winget.

## Package notes

- The package is the portable Windows x86_64 build with a bundled GStreamer
  runtime — no external dependencies, no admin rights needed.
- The `rivulet` shim starts the Rivulet GUI.
- Update checks: `checkver.github` points at the main repository.
