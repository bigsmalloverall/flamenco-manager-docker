# FLamenco manager docker
This repo is in WIP state.

My attempt at running flamenco-manager on docekr. The rendering is meant to be done by workers on other Windows machines.

## To do
Make rendiering work

## Setup
1. `cd .docker/`.
2. Copy `.env.example` and rename to `.env`.
3. Modify `.env` to your liking.
4. `docker compose build`
5. `docker compose up`
6. manager starts at port specified in `.env`. By default `12055`.

## Resources
https://blender.dtmc.ca/docs/documentation/technical/installation/flamenco/example_dockerfile/
https://github.com/dblanque/flamenco-compositor-script