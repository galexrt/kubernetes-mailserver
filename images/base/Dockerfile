FROM debian:stretch-slim

RUN apt-get -q update && \
    apt-get -q upgrade -y && \
    apt-get install -y \
        ca-certificates && \
    groupadd -g 5000 vmail
    useradd -g vmail -u 5000 vmail -d /var/vmail -m
