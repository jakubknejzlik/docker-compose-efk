# EFK Stack

This repository contains prepared compose file and fluent config for use with kontena log forwarder.

You can find more information at [Kontena logs documentation](https://www.kontena.io/docs/using-kontena/logs.html)

## Installation

First you need to install docker and docker compose on your server.

Then clone this repository:
```
git clone https://github.com/jakubknejzlik/kontena-efk.git
cd kontena-efk
```

And run the docker-compose:
```
docker-compose up -d
```

After a while you should be able to access kibana on port `80` (to change port, just update the docker-compose.yml)

## Kontena fluent forwarder

After installation you can forward your kontena grid to your newly created stack by running following command:

```
kontena grid update --log-forwarder fluentd --log-opt fluentd-address=logs.example.com my-grid
```

*NOTE: fluentd-address is ip or hostname of your server where efk stack is running*
