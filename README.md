# Conference video streaming with the help of NixOS

Presentation for FOSDEM 2026

## Build presentation

```sh
nix build
```

## Run locally

```sh
python -m http.server 8000 -d result/
```

open http://localhost:8000 in your browser and press `s` to activate 'speaker notes'

## GitHub Pages Deployment

This repository is configured with GitHub Actions to automatically build and deploy the presentation to GitHub Pages on every push to the `main` branch.

The presentation will be available at:
[gotha.github.io/presentation-2026-fosdem-conference-video-streaming-with-the-help-of-nixos](https://gotha.github.io/presentation-2026-fosdem-conference-video-streaming-with-the-help-of-nixos/)
