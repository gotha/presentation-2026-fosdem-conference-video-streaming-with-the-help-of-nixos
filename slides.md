---
author: Angel Angelov, gotha
title: Building unix-like operating systems the nix way
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

## Take it away dexterlb

---


## Thank you!

