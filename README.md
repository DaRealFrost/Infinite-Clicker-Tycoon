# Roblox CI-CD Test

[![Continuous Integration](https://github.com/DaRealFrost/Infinite-Clicker-Tycoon/actions/workflows/ci.yaml/badge.svg?branch=main)](https://github.com/DaRealFrost/Infinite-Clicker-Tycoon/actions/workflows/ci.yaml)
[![Continous Delivery](https://github.com/DaRealFrost/Infinite-Clicker-Tycoon/actions/workflows/cd.yaml/badge.svg?branch=main)](https://github.com/DaRealFrost/Infinite-Clicker-Tycoon/actions/workflows/cd.yaml)

## Prerequisites

In order to build the project you'll need the following tools:

1. [Foreman](https://github.com/Roblox/foreman) - Toolchain manager.
2. [Wally](https://github.com/UpliftGames/wally) - Package manager.
3. [Darklua](https://github.com/seaofvoices/darklua) - Lua code Transformer.
4. [Selene](https://github.com/Kampfkarren/selene) - Helper for writing Idiomantic Lua code.
5. [Rojo](https://github.com/rojo-rbx/rojo) - Syncing and Building.

## Building the Project

- Install toolchain via Foreman: `foreman install`
- Install required packages using Wally: `wally install`
- Generate the Roblox Standard Library format using Selene: `selene generate-roblox-std`
- Prepare src folder for building using DarkLua: `darklua process src processed-src --config darklua.json`
- Build the project using Rojo:
  - dev.rbxl: `rojo build -o dev.rbxl dev.project.json`
  - dev.rbxlx: `rojo build -o dev.rbxlx dev.project.json`
  - release.rbxm: `rojo build -o release.rbxm release.project.json`
  - release.rbxmx: `rojo build -o release.rbxmx release.project.json`
 
## Releases

A little guide to creating a new release:

- Create a new Tag: `git tag 1.0.2` replace `1.0.2` with the new version
  - If you accidently create the wrong tag use `git tag -d <tag>`
- Push the tag `git push --tags`
