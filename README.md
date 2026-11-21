# Audiosurf Tweaker — Nightly

Complete nightly builds of [Audiosurf Tweaker](https://github.com/Unchpokable/Audiosurf-Tweaker),
built from the organization mirror
[`Audiosurf-Tweaker/Audiosurf-Tweaker`](https://github.com/Audiosurf-Tweaker/Audiosurf-Tweaker)
(`main`). These are experimental snapshots, not the stable release channel — but they are **full
builds**, plugin included, not UI-only.

Every push to the mirror's `main` — or a manual run of the workflow — builds the bundle and
publishes `Audiosurf-Tweaker-Nightly-<yyyyMMdd>.zip` as a regular release. Download the newest one
from [Releases](https://github.com/Audiosurf-Tweaker/Audiosurf-Tweaker-Nightly/releases).

## What is inside

A complete drop-in bundle:

- `TweakerUI` (Native AOT) with `asbridge.exe` and the injector;
- the in-game plugin `TweakerPlugin.dll` (x86), ready to install from **Settings → In-game plugin**;
- `twllink`, the legacy skin converter and the developer tools;
- the bundled skin packs (`Skins/`), the Canvas sky package and PuzzlePRO HUD.

Extract the zip and run `TweakerUI.exe`; nothing else needs to be installed.

## How it builds

The workflow checks the mirror out with its submodules. DirectX June 2010, Dear ImGui, Detours and
LuaJIT are public submodules; the proprietary Quest3D SDK is a private organization repository that
the workflow checks out with a short-lived GitHub App token. A hosted `windows-latest` runner
therefore builds the complete bundle, plugin included, in about ten minutes. The repository
variable `NIGHTLY_RUNNER` can point at a self-hosted runner instead, but it is not needed for a
complete build.

This repository contains no source code. The build workflow is `.github/workflows/nightly.yml`; its
source copy is kept in the main repository at `Tools/ReleaseChannel/nightly.yml`.
