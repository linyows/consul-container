FROM linyows/consul:1.2

COPY consul.d /etc/consul.d

EXPOSE 53 53/udp 8300 8301 8301/udp 8500

CMD ["/bin/consul", "agent", "-server", "-ui", "-bootstrap", "-data-dir=/data", "-config-dir=/etc/consul.d", "-dns-port=53"]
