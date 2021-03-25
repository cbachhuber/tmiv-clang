FROM cbachhuber/clang:11

RUN apt-get update -qq && DEBIAN_FRONTENT=noninteractive apt-get install -qqy --no-install-recommends \
        build-essential \
        ccache

RUN /usr/sbin/update-ccache-symlinks

# As cbachhuber/clang sets the paths to the compiler as env variables, the below canonical line doesn't work.
# ENV PATH="/usr/lib/ccache:$PATH"
# Therefore, overwriting those ENV values directly below
ENV CXX=/usr/lib/ccache/clang++-11
ENV CC=/usr/lib/ccache/clang-11

ENV CCACHE_DIR=/.ccache

RUN mkdir -p /dependencies
RUN git clone --depth 1 --branch v2.13.4 https://github.com/catchorg/Catch2.git /dependencies/catch2
RUN git clone --depth 1 --branch 7.0.3 https://github.com/fmtlib/fmt.git /dependencies/fmt
RUN git clone --depth 1 --branch HM-16.16 https://vcgit.hhi.fraunhofer.de/jct-vc/HM.git /dependencies/hm
RUN git clone --depth 1 --branch v0.2.0.0 https://github.com/fraunhoferhhi/vvdec /dependencies/vvdec
RUN git clone --depth 1 --branch v0.2.0.0 https://github.com/fraunhoferhhi/vvenc /dependencies/vvenc
