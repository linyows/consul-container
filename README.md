Docker Consul
=============

https://hub.docker.com/r/linyows/consul/

- linyows/consul:ver
    - linyows/consul:ver-server
        ```
        - consul-server
        ```
    - linyows/consul:ver-agent
        ```
        - supervisord
            - consul-agent
            - consul-template
        ```
        - linyows/consul:ver-node
