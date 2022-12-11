# docker-vernemq
**VerneMQ** for amd64 (x86_64) and ARM32 (Raspberry Pi)

VerneMQ is a MQTT message broker, developed in Erlang.

### Docs

* https://docs.vernemq.com/
  * https://docs.vernemq.com/installing-vernemq/docker
  * https://github.com/vernemq/vmq-docs/blob/master/configuration/the-vernemq-conf-file.md  
   (use prefix "DOCKER_VERNEMQ_" and then key=value in docker command or docker-compose file)
  * https://github.com/vernemq/vmq-docs/blob/master/configuration/file-auth.md
* https://github.com/vernemq/docker-vernemq
* https://github.com/vernemq/vernemq

### Images / Build

* https://github.com/Tob1asDocker/docker-vernemq/pkgs/container/docker-vernemq
  * `docker pull ghcr.io/tob1as/docker-vernemq:latest-alpine` | `:VERSION-alpine` (AlpineLinux)
  * `docker pull ghcr.io/tob1as/docker-vernemq:latest` | `:VERSION` (Debian)
* https://hub.docker.com/r/tobi312/vernemq
  * `docker pull tobi312/vernemq:latest-alpine` | `:VERSION-alpine` (AlpineLinux)
  * `docker pull tobi312/vernemq:latest` | `:VERSION` (Debian)
* build yourself:
  * Docker:  
    ```sh
    # git clone and then:
    docker build -t local/vernemq:latest-alpine --build-arg VERNEMQ_VERSION="1.12.3" -f vernemq.alpine.Dockerfile .
    # or (without git clone)
    docker build -t local/vernemq:latest-alpine --build-arg VERNEMQ_VERSION="1.12.3" https://github.com/Tob1asDocker/docker-vernemq/raw/main/vernemq.alpine.Dockerfile
    ```  
  * Docker-Compose:  
    ```yml
    version: '2.4'
    services:
      vernemq:
        build: 
          context: https://github.com/Tob1as/docker-vernemq/raw/main/vernemq.alpine.Dockerfile
          args:
            VERNEMQ_VERSION: "1.12.3"
        image: local/vernemq:latest-alpine
        container_name: vernemq
        restart: unless-stopped
        # more settings ...
    ``` 
  * Note: Version must exists in repository [vernemq/docker-vernemq](https://github.com/vernemq/docker-vernemq) and [vernemq/vernemq](https://github.com/vernemq/vernemq) as branch/tag!

### Example

For docker-compose see [example-folder](example/)!  
  
Clients for publishing/subscribing:
* mosquitto-clients: [mosquitto_pub](https://mosquitto.org/man/mosquitto_pub-1.html)/[mosquitto_sub](https://mosquitto.org/man/mosquitto_sub-1.html).  
You can use docker-compose also, use "[MQTT-Client](https://github.com/Tob1asDocker/Collection/blob/master/examples_docker-compose/mqtt-client.yml)"-example.
* [MQTT-CLI](https://github.com/hivemq/mqtt-cli) from HiveMQ
* [MQTT.fx](https://mqttfx.jensd.de/index.php/download) Version: [1.7.1](http://www.jensd.de/apps/mqttfx/1.7.1/)
* [MQTT-Explorer](https://github.com/thomasnordquist/MQTT-Explorer)

### This Image on
* [DockerHub](https://hub.docker.com/r/tobi312/vernemq)
* [GitHub](https://github.com/Tob1as/docker-vernemq)