Docker Consul
=============

- linyows/consul:latest
- linyows/consul-server:latest
    - consul-server
- linyows/consul-agent:latest
    - supervisord
        - consul-agent
        - consul-template
