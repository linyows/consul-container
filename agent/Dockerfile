FROM linyows/consul:1.2

ENV CONSUL_TEMPLATE_VERSION 0.19.5
ENV CONSUL_TEMPLATE_SHA256 e6b376701708b901b0548490e296739aedd1c19423c386eb0b01cfad152162af

RUN apk --no-cache add openssl curl ca-certificates \
                       autoconf automake libtool linux-headers alpine-sdk git bind-tools supervisor curl-dev

RUN curl -sSL https://releases.hashicorp.com/consul-template/${CONSUL_TEMPLATE_VERSION}/consul-template_${CONSUL_TEMPLATE_VERSION}_linux_amd64.zip \
    -o /tmp/consul-template.zip && \
    echo "${CONSUL_TEMPLATE_SHA256}  /tmp/consul-template.zip" > /tmp/consul-template.sha256 && \
    sha256sum -c /tmp/consul-template.sha256 && \
    cd /bin && \
    unzip /tmp/consul-template.zip && \
    chmod +x /bin/consul-template && \
    rm /tmp/consul-template.zip /tmp/consul-template.sha256

COPY consul.d /etc/consul.d
COPY consul-template.d /etc/consul-template.d
COPY consul-template.conf /etc/consul-template.conf
COPY supervisor.d /etc/supervisor.d
COPY supervisord.conf /etc/supervisord.conf

ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisord.conf"]
