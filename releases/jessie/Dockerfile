FROM coldrye/debian-tini:0-9-0-jessie-latest

MAINTAINER Carsten Klein <trancesilken@gmail.com>

RUN set -x \
    && export APT_LISTCHANGES_FRONTEND=none \
    && apt-get update \
    && apt-get -q -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" install apt-transport-https \
    && apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D \
    && echo "deb https://apt.dockerproject.org/repo debian-jessie main" > /etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-get -q -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" install docker-engine \
    && apt-get clean \
    && rm -Rf /var/lib/apt/lists/* 2>/dev/null

