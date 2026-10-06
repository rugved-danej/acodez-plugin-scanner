# Acodez Plugin Scanner (Android/Termux Builds)

This repository automatically builds Android-compatible binaries (aarch64 & armv7) for the [Acode-Foundation/plugin_scanner](https://github.com/Acode-Foundation/plugin_scanner) using GitHub Actions.

## Why?
The official repository only provides standard Linux (GNU) and macOS binaries. Termux on Android requires binaries linked against the Android NDK (or musl/static), so standard GNU binaries fail with `ENOENT` (missing interpreter). This repository bridges the gap so users don't have to install Rust/Cargo on their mobile devices.

## How it works
A GitHub Actions workflow runs daily. It checks the latest release tag of the official scanner. If there's a new release, it uses `cross` to compile the Rust project for `aarch64-linux-android` and `armv7-linux-androideabi`, then publishes them here.
