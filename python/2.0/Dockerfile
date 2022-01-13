FROM marvinpan/python:1.0
MAINTAINER marvinpan <pantj@investoday.com.cn>
ARG PANDAS_VERSION=0.24.2
RUN apk add --no-cache libstdc++ && \
    apk add --no-cache --virtual .build-deps \
                g++ \
                bzip2-dev \
                coreutils \
                dpkg-dev dpkg \
                expat-dev \
                findutils \
                gcc \
                gdbm-dev \
                libc-dev \
                libffi-dev \
                libnsl-dev \
                libtirpc-dev \
                linux-headers \
                make \
                ncurses-dev \
                openssl-dev \
                pax-utils \
                readline-dev \
                sqlite-dev \
                tcl-dev \
                tk \
                tk-dev \
                util-linux-dev \
                xz-dev \
                linux-headers \
                zlib-dev \
                freetds-dev && \
    pip3 install --default-timeout=100 --no-cache-dir --upgrade pandas==${PANDAS_VERSION} && \
    apk del .build-deps
