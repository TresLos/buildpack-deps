FROM centos

RUN yum update -y && yum install -y \
		ca-certificates \
		curl \
		wget \
	&& yum clean all

RUN set -ex; \
	if ! command -v gpg > /dev/null; then \
		yum update -y; \
		yum install -y \
			gnupg \
			dirmngr \
		; \
		yum clean all; \
	fi
