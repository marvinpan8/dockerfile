FROM marvinpan/python:1.1
MAINTAINER marvinpan <pantj@investoday.com.cn>
RUN apk add --no-cache lapack && \
    apk add --no-cache --virtual .build-deps \
                g++ \
                lapack-dev \
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
                gfortran \
                freetds-dev && \
    pip3 install --default-timeout=100 --no-cache-dir --upgrade scipy && \
    apk del .build-deps
