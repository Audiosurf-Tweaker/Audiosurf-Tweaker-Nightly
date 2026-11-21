# Audiosurf Tweaker — Nightly

Pre-release builds of [Audiosurf Tweaker](https://github.com/Unchpokable/Audiosurf-Tweaker),
built from the organization mirror
[`Audiosurf-Tweaker/Audiosurf-Tweaker`](https://github.com/Audiosurf-Tweaker/Audiosurf-Tweaker)
(`main`).

Every push to the mirror's `main` — or a manual run of the workflow — builds the bundle and
publishes `Audiosurf-Tweaker-Nightly-<date>.zip` as a pre-release. Download the newest one from
[Releases](https://github.com/Audiosurf-Tweaker/Audiosurf-Tweaker-Nightly/releases).

This repository contains no source code. The build workflow is
`.github/workflows/nightly.yml`; its source copy is kept in the main repository at
`Tools/ReleaseChannel/nightly.yml`.

The in-game plugin needs the proprietary Quest3D SDK and the DirectX June 2010 SDK. A hosted
runner builds everything except `TweakerPlugin.dll`, so its bundle is UI-only; set the repository
variable `NIGHTLY_RUNNER` to a self-hosted runner that has both SDKs for a complete nightly.
