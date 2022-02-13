# docker-vernemq
**VerneMQ** for amd64 (x86_64) and ARM32 (Raspberry Pi)

more see:
* https://github.com/vernemq/docker-vernemq
* https://github.com/vernemq/vernemq
* https://docs.vernemq.com/installing-vernemq/docker
* https://docs.vernemq.com/configuring-vernemq/the-vernemq-conf-file (or on [GitHub](https://github.com/vernemq/vmq-docs/blob/1.12.3/configuration/the-vernemq-conf-file.md)) (use prefix "DOCKER_VERNEMQ_" and then key=value in docker command or docker-compose file)

Images:
* https://github.com/Tob1asDocker/docker-vernemq/pkgs/container/docker-vernemq
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:latest-alpine` (AlpineLinux)
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:VERSION-alpine` (AlpineLinux)
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:latest` (Debian)
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:VERSION` (Debian)
* https://hub.docker.com/r/tobi312/vernemq
  * `docker pull tobi312/vernemq:latest-alpine` (AlpineLinux)
  * `docker pull tobi312/vernemq:VERSION-alpine` (AlpineLinux)
  * `docker pull tobi312/vernemq:latest` (Debian)
  * `docker pull tobi312/vernemq:VERSION` (Debian)
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
          context: https://github.com/Tob1asDocker/docker-vernemq/raw/main/vernemq.alpine.Dockerfile
          args:
            VERNEMQ_VERSION: "1.12.3"
        image: local/vernemq:latest-alpine
        container_name: vernemq
        restart: unless-stopped
        # more settings ...
    ``` 
  * Note: Version must exists in repository [vernemq/docker-vernemq](https://github.com/vernemq/docker-vernemq) and [vernemq/vernemq](https://github.com/vernemq/vernemq) as branch/tag!
