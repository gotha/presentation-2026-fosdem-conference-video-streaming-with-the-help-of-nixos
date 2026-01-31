---
author: Angel Angelov (dexterlb), Hristo Georgiev (gotha)
title: Conference video streaming with the help of NixOS
date: January 31, 2026
---

## What are we going to talk about today

- Setup for OpenFest 2025
- the audio/video mixer distro we started
- mixos on FOSDEM boxes
- future of the project

---

## $(cat /etc/passwd)

```
dexterlb:x:1000:1000:Angel Angelov:/github.com/dexterlb
gotha:x:1001:1001:Hristo Georgiev:/hgeorgiev.com
```

---

## What is OpenFest

- conference about free culture, free knowledge sharing, free and open source software
- since 2003
- usually every fall in Sofia (sometimes in multiple cities simultaniously)

---

## The plan and preparation for OpenFest 2025

- set up the audio/video mixer
- main goal - set up everything working in one go!
- enter [openfest/mixos](https://github.com/openfest/mixos)
    - bundle ffmpeg, GPU drivers and rice Sway
    - setup custom keypad
    - pack all the assets - promo images, videos, etc
    - ready to use pre-configured OBS
- build and test with QEMU
- provision with ~~deploy-rs~~ - [dexterlb/deploy-o-matic](https://github.com/dexterlb/deploy-o-matic)

---

## The execution

- We were prepared for disaster
    - HDD to boot from
    - BYOBC (where BC stands for Binary Cache) - nix-serve
- of course the setup broke on Friday evening ... but we fixed it
- how many people casually carry around a bootable Linux drive in their pocket?

---

## FOSDEM video box

- hardware redundancy
    - just replace the box with an identical one
- relatively cheap (400EUR)
- new revision can stream a single room with one box

---

## FOSDEM video box

- lots of software that supports the custom hardware
- we packaged everything to work with mixos
- mixos runs on the FOSDEM box!

---

## Deployment

- For a first boot, we just generate a disk image
    - `nixos-generators`

- Iteration and regular deployment
    - Our flake exports `nixosConfigurations`
    - Deploy with
    ```
        nixos-rebuild switch --flake '.#foo' --target-host foo.example.com
    ```
    - Or deploy with `deploy-rs`

---

## Deployment (pt 2)

- `nixos-generators` doesn't do much:
    - it adds some target-specific nixos modules
    - it calls host.config.system.build.${imageFormat}
- This is incompatible with subsequent redeploys
    - the `nixosConfiguration` doesn't contain the target-specific modules
    - so they don't get deployed by `deploy-rs`
- So we made yet another tool: [deploy-o-matic](https://github.com/dexterlb/deploy-o-matic)
    - just a few nix functions that generate `nixosConfigurations` and image packages

---

## Thank you!

