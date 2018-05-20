FROM galexrt/kubernetes-mailserver-base:latest

RUN apt-get -q update && \
    apt-get -q upgrade -y && \
    apt-get install -y \
        supervisor \
        rsyslog \
        dovecot-core \
        dovecot-imapd \
        dovecot-lmtpd \
        dovecot-managesieved
        dovecot-mysql \
        dovecot-pgsql \
        dovecot-pop3d

ENTRYPOINT ["/usr/sbin/dovecot", "-F", "-c", "/config/dovecot.conf"]
