FROM alpine:3.7

ENV CONSUL_VERSION 1.2.0
ENV CONSUL_SHA256 85d84ea3f6c68d52549a29b00fd0035f72c2eabff672ae46ca643cb407ef94b4

RUN apk --no-cache add curl ca-certificates bind-tools && \
    curl -sSL https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip \
    -o /tmp/consul.zip && \
    echo "${CONSUL_SHA256}  /tmp/consul.zip" > /tmp/consul.sha256 && \
    sha256sum -c /tmp/consul.sha256 && \
    cd /bin && \
    unzip /tmp/consul.zip && \
    chmod +x /bin/consul && \
    rm /tmp/consul.zip /tmp/consul.sha256 && \
    mkdir /etc/consul.d
