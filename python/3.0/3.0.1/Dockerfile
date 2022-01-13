FROM python:3.7.2-alpine3.9
MAINTAINER marvinpanpan 
ENV TIMEZONE=Asia/Shanghai
RUN apk add --no-cache mariadb-dev zlib-dev openssl freetds-dev && \
    apk add --no-cache --virtual=build-dependencies \
                            g++ \
                            build-base libffi-dev python3-dev \
                            libffi  ca-certificates \
                            pcre-dev \
                bzip2-dev \
		coreutils \
		dpkg-dev dpkg \
		expat-dev \
		findutils \
		gcc \
		gdbm-dev \
		libc-dev \
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
                tzdata && \
pip3 install --upgrade pip Cython --no-cache-dir -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com && \
pip3 install --no-cache-dir -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com \
                                                    certifi==2019.6.16 \
                                                    chardet==3.0.4 \
                                                    Django==2.1.8 \
                                                    djangorestframework==3.9.4 \
                                                    idna==2.8 \
                                                    mysqlclient==1.4.2.post1 \
                                                    pytz==2019.1 \
                                                    PyYAML==5.1 \
                                                    requests==2.21.0 \
                                                    sqlparse==0.3.0 \
                                                    urllib3==1.24.3 \
                                                    uWSGI==2.0.18 \
                                                    kubernetes==9.0.0 \
                                                    sqlalchemy==1.3.1 \
                                                    pymssql==2.1.4 \
						    xlrd==1.2.0 && \ 
apk del --purge build-dependencies && \
rm -rf /root/.cache /tmp/* && \
# modify timezone from UTC -> CST
    apk add tzdata && \
    cp /usr/share/zoneinfo/$TIMEZONE /etc/localtime && \
    echo $TIMEZONE > /etc/timezone && \
    apk del tzdata && \
# add user jr
    addgroup -g 10001 -S jr && \
    adduser jr -u 20001 -D -S -s /bin/bash -G jr && \
    chmod 4755 /bin/busybox && \
    echo -e "aitougu2019\naitougu2019" | passwd jr && \
    echo -e "1qaz2wsx!@#$\n1qaz2wsx!@#$" | passwd root
