# Clang docker container for TMIV CI

[![docker](https://img.shields.io/docker/pulls/cbachhuber/tmiv-clang.svg)](https://hub.docker.com/r/cbachhuber/tmiv-clang/)

A docker container with modern CMake and clang for [TMIV](https://gitlab.com/mpeg-i-visual/tmiv)'s continuous integration.
Built on top of [cbachhuber/clang](https://github.com/cbachhuber/clang), it additionally offers

- build caching with [ccache](https://ccache.dev/).
- TMIV's CMake dependencies in folder `/dependencies/`:
  - [Catch2](https://github.com/catchorg/Catch2.git)
  - [fmt](https://github.com/fmtlib/fmt.git)
  - [HM](https://vcgit.hhi.fraunhofer.de/jct-vc/HM.git)
  - [VVdeC](https://github.com/fraunhoferhhi/vvdec)
  - [VVenC](https://github.com/fraunhoferhhi/vvenc)
