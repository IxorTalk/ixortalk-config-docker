# IxorTalk Config Docker

This module contains basic Docker configuration to get started easily with the IxorTalk platform.  All Docker images are publicly available in the `ixortalk` organization. 

For general documentation about the IxorTalk platform: https://github.com/ixortalk/ixortalk-gateway

## Requirements

* Docker
* Docker Compose

## Getting started

To get started simply execute the following:
```
ixortalk-config-docker $ docker-compose up -d
```

This will start an IxorTalk instance called `demo` pulling its configuration from https://github.com/ixortalk/ixortalk.config.demo. The instance name and some other basic Docker compose environment variables are configured in `.env`.

When the instance is up and running, the gateway will be available at: http://<your-ip>:8888/ (eg. http://localhost:8888 when running locally). 

## Remarks

Some important remarks to be made: 

* Properties `${ixortalk.loadbalancer.internal.host}` and `${ixortalk.loadbalancer.external.host}` should point to a resolvable ip-address for the docker host, resolvable on the host and within the docker containers.  They are configured to be `10.200.10.1` in the demo configuration, either configure this to the actual ip address or add an alias: Eg. `sudo ifconfig lo0 alias 10.200.10.1/24`
* When the platform is initially started, the very first request might timeout, after a refresh it should work fine
* By default there is an admin user which can be used to login to the platform: `admin`/`admin`     

## License

