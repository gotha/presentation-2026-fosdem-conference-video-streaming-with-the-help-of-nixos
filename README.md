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
