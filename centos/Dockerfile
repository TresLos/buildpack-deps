FROM buildpack-deps:centos-scm

RUN set -ex; \
	yum update -y; \
	yum install -y \
		autoconf \
		automake \
		bzip2 \
	dpkg-dev \
		file \
	g++ \
		gcc \
	imagemagick \
	libbz2-dev \
	libc6-dev \
	libcurl4-openssl-dev \
		libdb-devel \
		libevent-devel \
		libffi-devel \
	libgdbm-dev \
	libgeoip-dev \
	libglib2.0-dev \
	libgmp-dev \
	libjpeg-dev \
	libkrb5-dev \
	liblzma-dev \
	libmagickcore-dev \
	libmagickwand-dev \
	libncurses5-dev \
	libncursesw5-dev \
		libpng-devel \
	libpq-dev \
	libreadline-dev \
	libsqlite3-dev \
	libssl-dev \
		libtool \
		libwebp-devel \
		libxml2-devel \
		libxslt-devel \
		libyaml-devel \
		make \
		patch \
		unzip \
	xz-utils \
	zlib1g-dev \
		\
# https://lists.debian.org/debian-devel-announce/2016/09/msg00000.html
		$( \
# if we use just "apt-cache show" here, it returns zero because "Can't select versions from package 'libmysqlclient-dev' as it is purely virtual", hence the pipe to grep
			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then \
				echo 'default-libmysqlclient-dev'; \
			else \
				echo 'libmysqlclient-dev'; \
			fi \
		) \
	; \
	rm -rf /var/lib/apt/lists/*
