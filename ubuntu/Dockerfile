FROM ubuntu
ARG nvm_version=v0.35.2
ENV LANG=C.UTF-8 nvm_version=${nvm_version}
WORKDIR /root
RUN sed -i 's/archive.ubuntu/mirrors.aliyun/g' /etc/apt/sources.list && \
    sed -i 's/security.ubuntu/mirrors.aliyun/g' /etc/apt/sources.list && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -y --no-install-recommends install apt-utils curl ca-certificates && \
    DEBIAN_FRONTEND=noninteractive apt-get -y --no-install-recommends install build-essential git vim-tiny && \
    apt-get autoremove && apt-get clean
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/${nvm_version}/install.sh | bash
#RUN wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/${nvm_version}/install.sh | bash