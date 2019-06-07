# xivapi.com - v3 [![Build Status](https://travis-ci.org/xivapi/xivapi.com-v3.svg?branch=master)](https://travis-ci.org/xivapi/xivapi.com-v3)

## Getting Setup

Make a folder where all XIVAPI projects (including Mogboard) can sit:

- `mkdir xivapi`
- `cd xivapi`

Clone XIVAPI (or Mogboard) and Docker

- `git clone https://github.com/xivapi/xivapi.com-v3.git`
- `git clone https://github.com/xivapi/xivapi.com-docker.git`

Build and run the docker

- `cd xivapi.com-docker`
- `docker-compose build`
- `docker-compose up -d`

Add to your hosts file: `127.0.0.1 xivapi.local`



## XDebug
- IDE Key: PHPSTORM
- Update `docker-compose.yml` -> `extra_hosts: "docker-host.localhost:127.0.0.1"` to your ip from `ifconfig en0`
- Port: 5902
- Host: docker-host.localhost
- Use Docker container for PHP Cli Interpreter.
