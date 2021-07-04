FROM cbachhuber/clang:12

RUN apt-get update -qq && DEBIAN_FRONTENT=noninteractive apt-get install -qqy --no-install-recommends \
        build-essential \
        ccache

RUN /usr/sbin/update-ccache-symlinks

# As cbachhuber/clang sets the paths to the compiler as env variables, the below canonical line doesn't work.
# ENV PATH="/usr/lib/ccache:$PATH"
# Therefore, overwriting those ENV values directly below
ENV CXX=/usr/lib/ccache/clang++-12
ENV CC=/usr/lib/ccache/clang-12

ENV CCACHE_DIR=/.ccache

RUN mkdir -p /dependencies
RUN git clone --depth 1 --branch v2.13.4 https://github.com/catchorg/Catch2.git /dependencies/Catch2-2_13_4
RUN git clone --depth 1 --branch 7.0.3 https://github.com/fmtlib/fmt.git /dependencies/fmt-7_0_3
RUN git clone --depth 1 --branch 8.0.1 https://github.com/fmtlib/fmt.git /dependencies/fmt-8_0_1
RUN git clone --depth 1 --branch HM-16.16 https://vcgit.hhi.fraunhofer.de/jct-vc/HM.git /dependencies/HM-16_16
RUN git clone --depth 1 --branch v1.0.1 https://github.com/fraunhoferhhi/vvdec /dependencies/vvdec-1_0_1
RUN git clone --depth 1 --branch v0.3.1.0 https://github.com/fraunhoferhhi/vvenc /dependencies/vvenc-0_3_1_0
RUN git clone --depth 1 --branch v1.0.0 https://github.com/fraunhoferhhi/vvenc /dependencies/vvenc-1_0_0
