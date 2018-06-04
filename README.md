# IxorTalk Config Docker

This module contains basic Docker configuration to get started easily with the IxorTalk platform.  All Docker images are publicly available in the [ixortalk](https://hub.docker.com/u/ixortalk/) organization. 

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

When the instance is up and running, the gateway will be available at: `http://<your-ip>:8888/` (eg. http://localhost:8888 when running locally). 

## Remarks

Some important remarks to be made: 

* Properties `${ixortalk.loadbalancer.internal.host}` and `${ixortalk.loadbalancer.external.host}` should point to a resolvable ip-address for the docker host, resolvable on the host and within the docker containers.  They are configured to be `10.200.10.1` in the demo configuration, either configure this to the actual ip address or add an alias: Eg. `sudo ifconfig lo0 alias 10.200.10.1/24`
* When the platform is initially started, the very first request might timeout, after a refresh it should work fine
* By default there is an admin user which can be used to login to the platform: `admin`/`admin`     

## License
```
The MIT License (MIT)

Copyright (c) 2016-present IxorTalk CVBA

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
