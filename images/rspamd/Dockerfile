FROM galexrt/kubernetes-mailserver-base:latest

RUN apt-get -q update && \
    apt-get install -y \
        wget \
        gnupg2 && \
    wget -O- https://rspamd.com/apt-stable/gpg.key | \
        apt-key add - && \
    echo "deb http://rspamd.com/apt-stable/ stretch main" > \
        /etc/apt/sources.list.d/rspamd.list && \
    apt-get -q update && \
    apt-get install -y \
        rspamd && \
    apt-get remove -y wget gnupgp2

ENTRYPOINT ["/usr/bin/rspamd"]
