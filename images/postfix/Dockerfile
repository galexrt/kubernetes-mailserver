FROM galexrt/kubernetes-mailserver-base:latest

RUN apt-get install -y \
        postfix \
        postfix-ldap \
        postfix-mysql \
        postfix-pcre \
        postfix-pgsql

COPY ./includes/supervisord.conf /etc/supervisor/supervisord.conf
COPY ./includes/rsyslog.conf /etc/rsyslog.conf
COPY ./includes/listen.conf /etc/rsyslog.d/listen.conf

ENTRYPOINT ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
