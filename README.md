# Clang docker container for TMIV CI

[![docker](https://img.shields.io/docker/pulls/cbachhuber/tmiv-clang.svg)](https://hub.docker.com/r/cbachhuber/tmiv-clang/)

A docker container with modern CMake and clang for [TMIV](https://gitlab.com/mpeg-i-visual/tmiv)'s continuous integration.
Built on top of [cbachhuber/clang](https://github.com/cbachhuber/clang), it additionally offers

- build caching with [ccache](https://ccache.dev/).
  Inside the docker container, folder `/.ccache` is used for caching.
  Mount that one with read&write rights to a persistent folder on your machine to achieve build caching between container invocations.
- TMIV's CMake dependencies in folder `/dependencies`:
  - [Catch2](https://github.com/catchorg/Catch2.git)
  - [fmt](https://github.com/fmtlib/fmt.git)
  - [HM](https://vcgit.hhi.fraunhofer.de/jct-vc/HM.git)
  - [VVdeC](https://github.com/fraunhoferhhi/vvdec)
  - [VVenC](https://github.com/fraunhoferhhi/vvenc)

Tags and corresponding docker files:

- `1`: [1.Dockerfile/](https://github.com/cbachhuber/tmiv-clang/blob/master/1.Dockerfile/Dockerfile) contains clang 11
- `2`: [2.Dockerfile/](https://github.com/cbachhuber/tmiv-clang/blob/master/2.Dockerfile/Dockerfile) contains clang 12
