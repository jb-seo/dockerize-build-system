FROM ubuntu:bionic
# 14.04 - trusty
# 16.04 - xenial
# 18.04 - bionic
# 18.10 - cosmic

MAINTAINER Yi-Soo An <yisooan@gmail.com>
MAINTAINER JeongBong Seo <lifeofthanks@gmail.com>

# Replace the repo with kakao mirror
# Consider uncommenting for Korea
# RUN sed -i "s/archive.ubuntu.com/mirror.kakao.com/g" /etc/apt/sources.list

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git sudo vim-common lsb-release wget software-properties-common && \
    useradd -m webos && \
    touch /etc/sudoers.d/webos && \
    echo "webos ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/webos && \
    mkdir -p /home/webos/mpoint

RUN wget https://raw.githubusercontent.com/webosose/build-webos/master/scripts/prerequisites.sh
RUN chmod +x prerequisites.sh && ./prerequisites.sh && rm prerequisites.sh

USER webos
WORKDIR /home/webos/mpoint
