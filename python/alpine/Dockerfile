FROM python:3.7.2-alpine3.9
MAINTAINER marvinpan <pantj@investoday.com.cn>
ENV PYMSSQL_BUILD_WITH_BUNDLED_FREETDS=1 \
    TIMEZONE=Asia/Shanghai
RUN echo "http://mirrors.aliyun.com/alpine/latest-stable/main/" > /etc/apk/repositories && \
    echo "http://mirrors.aliyun.com/alpine/latest-stable/community/" >> /etc/apk/repositories && \
    # add user jr
    addgroup -g 10001 -S jr && \
    adduser jr -u 20001 -D -S -s /bin/bash -G jr && \
    chmod 4755 /bin/busybox && \
    echo -e "lingyunzhitou2019\nlingyunzhitou2019" | passwd jr && \
    echo -e "1qaz2wsx!@#$\n1qaz2wsx!@#$" | passwd root && \
    apk add --no-cache --virtual .build-deps  \
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
                freetds-dev \
                tzdata && \
    apk add --no-cache freetds && \
    cp /usr/share/zoneinfo/$TIMEZONE /etc/localtime && \
    echo $TIMEZONE > /etc/timezone && \
    pip3 install --default-timeout=100 --no-cache-dir --upgrade Cython && \
    pip3 install --default-timeout=100 --no-cache-dir --upgrade requests pymysql numpy pymssql PyYAML ConcurrentLogHandler && \
    apk del .build-deps
WORKDIR /opt
