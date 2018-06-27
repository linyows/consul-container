FROM linyows/consul:1.2

COPY consul.d /etc/consul.d

EXPOSE 53 53/udp 8300 8301 8301/udp

CMD ["/bin/consul", "agent", "-server", "-bootstrap", "-data-dir=/data", "-config-dir=/etc/consul.d", "-dns-port=53"]
