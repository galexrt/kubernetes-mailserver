FROM galexrt/kubernetes-mailserver-base:latest

RUN apt-get -q update && \
    apt-get -q upgrade -y && \
    apt-get install -y \
        postfix \
        postfix-ldap
        postfix-mysql \
        postfix-pcre \
        postfix-pgsql \
