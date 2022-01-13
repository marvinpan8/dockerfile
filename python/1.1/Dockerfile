FROM marvinpan/python:1.0
MAINTAINER marvinpan <pantj@investoday.com.cn>
RUN apk add mariadb-dev zlib-dev openssl && apk add --no-cache --virtual=build-dependencies \ 
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
		sqlite-dev \
		tcl-dev \
		tk \
		tk-dev \
		util-linux-dev \
		xz-dev \
                linux-headers \
                zlib-dev \
    && pip3 install --default-timeout=100 --no-cache-dir --upgrade \
		 pip==19.1.1 \
                 prometheus_client==0.7.1 \
                 croniter==0.3.30 \
                 celery==4.3.0 \
		 celery[redis] \
                 psutil==5.6.3 \
                 mysqlclient==1.4.4 \
    && apk del --purge build-dependencies
