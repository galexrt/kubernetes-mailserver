FROM galexrt/kubernetes-mailserver-base:latest

RUN wget -O- https://rspamd.com/apt-stable/gpg.key | \
        apt-key add - && \
    echo "deb http://rspamd.com/apt-stable/ stretch main" > \
        /etc/apt/sources.list.d/rspamd.list && \
    apt-get -q update && \
    apt-get -q upgrade -y && \
    apt-get install -y \
        rspamd

ENTRYPOINT ["/usr/bin/rspamd"]
