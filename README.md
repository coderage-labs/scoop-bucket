# scoop-bucket

Scoop manifests for [coderage-labs](https://github.com/coderage-labs).

```powershell
scoop bucket add coderage-labs https://github.com/coderage-labs/scoop-bucket
scoop install spillway
```

## What's here

| App | What it is |
|---|---|
| [spillway](https://github.com/coderage-labs/spillway) | Pool your own AI subscription accounts behind one local proxy |

## Upgrading

```powershell
scoop update spillway
```

If spillway is registered as a Scheduled Task, the manifest's `post_install`
restarts it onto the new binary. Scoop replaces the files under the app
directory but does not touch a running process, and the task holds an
absolute path — so without that step an upgrade leaves the previous version
serving every request while `scoop list` reports the new one.

## Don't edit `bucket/`

Manifests there are written by
[goreleaser](https://goreleaser.com) from each project's own release, and any
change made here is overwritten by the next one. Fix it at the source repo.
