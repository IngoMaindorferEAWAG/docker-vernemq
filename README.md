# docker-vernemq
VerneMQ for amd64 (x86_64) and ARM (Raspberry Pi) based on AlpineLinux

more see:
* https://github.com/vernemq/docker-vernemq
* https://github.com/vernemq/vernemq
* https://docs.vernemq.com/installing-vernemq/docker
* https://docs.vernemq.com/configuring-vernemq/the-vernemq-conf-file (or on [GitHub](https://github.com/vernemq/vmq-docs/blob/1.12.3/configuration/the-vernemq-conf-file.md)) (use prefix "DOCKER_VERNEMQ_" and then key=value in docker command or docker-compose file)

Images:
* https://github.com/Tob1asDocker/docker-vernemq/pkgs/container/docker-vernemq
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:latest-alpine`
  * `docker pull ghcr.io/tob1asdocker/docker-vernemq:VERSION-alpine`
* https://hub.docker.com/r/tobi312/vernemq
  * `docker pull tobi312/vernemq:latest-alpine`
  * `docker pull tobi312/vernemq:VERSION-alpine`
* build yourself:
  * `docker build -t local/vernemq:1.12.3-alpine --build-arg VERNEMQ_VERSION="1.12.3" -f vernemq.alpine.Dockerfile .`  
  (Version must exists in repository [vernemq/docker-vernemq](https://github.com/vernemq/docker-vernemq) and [vernemq/vernemq](https://github.com/vernemq/vernemq) as branch/tag!)
