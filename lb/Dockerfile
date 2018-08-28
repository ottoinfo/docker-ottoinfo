FROM haproxy:1.8

MAINTAINER Matt Otto "matt@ottoinfo.com"

RUN apt-get update
RUN apt-get install -qqy vim rsyslog curl htop

ADD config/rsyslog-haproxy.conf /etc/rsyslog.d/rsyslog-haproxy.conf
ADD config/logrotate-haproxy.conf /etc/logrotate.d/logrotate-haproxy.conf

RUN touch /var/log/haproxy.log
RUN chmod 777 /var/log/haproxy.log
RUN /etc/init.d/rsyslog start

COPY config/haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
COPY config/self-signed-cert.pem /usr/local/etc/haproxy/self-signed-cert.pem

CMD ["haproxy", "-f", "/usr/local/etc/haproxy/haproxy.cfg"]
