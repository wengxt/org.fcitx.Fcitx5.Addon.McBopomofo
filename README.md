# Flathub Manifest for fcitx5-mcbopomofo

Based on [Brli's work](https://github.com/Brli/flatpak.fcitx5-mcbopomofo).

## Summary

This directory contains the Flathub manifest for fcitx5-mcbopomofo. The
manifest is based on the ones in [fcixt5's own Flathub
manifests](https://github.com/fcitx/flatpak-fcitx5).

## Build the Flatpak Locally

To build the Flatpak locally, install `flatpak` and `flatpak-builder` first.
See Flatpak's [Quick Setup](https://flatpak.org/setup/) for how to install them
on the distro you use.

Once you have `flatpak-builder` installed, run the command in the same
directory where you find this README file:

```bash
flatpak-builder \
  --force-clean \
  --install-deps-from=flathub \
  --disable-cache \
  --repo=/tmp/fcitx5-mcbopomofo-repo \
  --user \
  /tmp/fcitx5-mcbopomofo-app org.fcitx.Fcitx5.Addon.McBopomofo.yaml
```

Once the builder successfully finishes, you can export a single package, which
in turn can be installed locally on other machines:

```bash
flatpak build-bundle \
  --runtime \
  /tmp/fcitx5-mcbopomofo-repo \
  org.fcitx.Fcitx5.Addon.McBopomofo.flatpak \
  org.fcitx.Fcitx5.Addon.McBopomofo \
  stable
---

This exports a runtime (since fcitx5-mcbopofo is an add-on of fcitx5) instead
of an app. The resulting flatpak file is
`org.fcitx.Fcitx5.Addon.McBopomofo.flatpak` in the same directory.

You can copy the flatpak file to another machine now. To install it, run:

```bash
flatpak install --user org.fcitx.Fcitx5.Addon.McBopomofo.flatpak
```
