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
