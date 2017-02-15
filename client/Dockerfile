FROM ubuntu:16.04

RUN apt-get update && apt-get install -y wget
RUN wget -qO - http://packages.fluentbit.io/fluentbit.key | apt-key add -
RUN echo "deb http://packages.fluentbit.io/ubuntu xenial main" >> /etc/apt/sources.list
RUN apt-get update && \
    apt-get install -y td-agent-bit && \
    touch /var/log/syslog

COPY td-agent-bit.conf /etc/td-agent-bit/td-agent-bit.conf

CMD ["/opt/td-agent-bit/bin/td-agent-bit","-c","/etc/td-agent-bit/td-agent-bit.conf"]
