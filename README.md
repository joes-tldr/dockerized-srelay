# Dockerized SRELAY

Ref: https://socks-relay.sourceforge.io

DockerHub: https://hub.docker.com/r/joestldr/srelay

GitHub: https://github.com/joestldr/dockerized-srelay

## TLDR; Sample usage: SOCKS Proxy

```bash
docker run \
    --name joestldr-relay \
    --detach \
    --restart=unless-stopped \
    --publish=1080:1080/tcp \
  joestldr/srelay:v1.0.0
```

## Use config file

Sample (default) `srelay.conf`:
```
0.0.0.0    any
```
Ref: https://socks-relay.sourceforge.io/samples.html

Run with `*.conf` file:
```bash
CONF_PATH='/path/to/srelay.conf'

docker run \
    --name joestldr-relay \
    --detach \
    --restart=unless-stopped \
    --publish=1080:1080/tcp \
    --mount="type=bind,source=${CONF_PATH},target=/etc/srelay.conf,readonly" \
  joestldr/srelay:v1.0.0
```

## Sample `docker compose` usage:

See "Dockerized VPN Proxy" - Magical HTTP and SOCKS4/SOCKS5 proxy behind VPN (without host being on VPN)

Link: https://github.com/joestldr/dockerized-vpn-proxy

# License

Copyright 2023 [joestldr](https://joestldr.com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
