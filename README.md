# kidchenko/scoop-bucket

[![Tests](https://github.com/kidchenko/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/kidchenko/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/kidchenko/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/kidchenko/scoop-bucket/actions/workflows/excavator.yml)

[Scoop](https://scoop.sh) manifests for [kidchenko](https://github.com/kidchenko)'s tray apps.
The macOS counterpart is [kidchenko/homebrew-tap](https://github.com/kidchenko/homebrew-tap).

```pwsh
scoop bucket add kidchenko https://github.com/kidchenko/scoop-bucket
scoop install kidchenko/cota
```

| App | |
|---|---|
| [`cafe`](bucket/cafe.json) | [Cafe](https://github.com/kidchenko/cafe) keeps your PC awake from the tray. |
| [`cantos`](bucket/cantos.json) | [Cantos](https://github.com/kidchenko/cantos) gives your screen corners actions, from the tray. |
| [`cota`](bucket/cota.json) | [Cota](https://github.com/kidchenko/cota) shows your Claude usage limits in the tray. |
| [`porta`](bucket/porta.json) | [Porta](https://github.com/kidchenko/porta) lists what's listening on your ports in the tray, and stops it. |
| [`suavez`](bucket/suavez.json) | [Sua Vez](https://github.com/kidchenko/suavez) lights up the tray when your coding agent finishes or needs you. |

Each app installs the release's portable exe with a Start menu shortcut. They
live in the tray, so quit them from their menu before `scoop update` or
`scoop uninstall`. Uninstalling also turns off Run at login; settings in
`%APPDATA%` are kept.

## Updates

[`excavator`](.github/workflows/excavator.yml) runs every four hours and moves
each manifest to its app's latest GitHub release, taking the hash from the
release's `SHA256SUMS.txt`. To run it now:

```bash
gh workflow run excavator.yml --repo kidchenko/scoop-bucket
```

[`ci`](.github/workflows/ci.yml) validates the manifests and installs and
uninstalls every app on each push and pull request.
