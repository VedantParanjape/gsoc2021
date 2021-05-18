---
layout: post
title:  "Week 8"
date:   2020-07-27 13:22:00 +0530
categories:
---

# Coding Period (1st June - 31st August)

## 20th July 2020

* Tried to get eCap PWM working, found out that pru_ecap followed little endian, so bit fields were wrong, corrected those.
* Added functionality to autodetect which BB board is being used, and automatically load it's Header<->PRU mappings.

## 21st July 2020

* Added functionality such that compiler autodetects board version and uses appropriate header-PRU pin mappings

## 22nd July 2020

* Couldnot work due to personal work

## 23rd July 2020

* Implemented commandline options using argp
* Created Makefile to compile the project
* Shifted to autotools for compilation

## 24th July 2020

* Setup CI on github actions, to build the project. 
* Fixed issues in make distclean, caused due to incorrect naming scheme for files

## 25th July 2020

* Created docker images for arm32v7 and amd64 for compilation, both have pru-gcc installed, which was compiled on the image, used AWS for the same. Uploaded images on dockerhub
* Tried adding pru-gcc static lib generation in configure.ac, failed to work
* Implemented github workflows after struggling for days with it. It used those prebuilt docker images to compile

## 26th July 2020

* autotools is pathetic, it took three days to setup, and it didn't work well in the end. Shifted to CMake build system. Ported within 10 hrs, pru static lib generation also worked well in CMake build system.
* Updated simppru code, such that it will reference headers and static lib according to their install locations.

