## Proxy
```shell
ssh -D 8080 username@sshd_server 
```
Provides proxy on localhost:8080, Requires SOCKS v5 proxy

## LocalPort forwarding
```shell
ssh -L 9000:imgur.com:80 user@sshd_server
```
When accessing localhost:9000, the traffic will be forwarded to imgur.com:80 through sshd_server

## RemotePort Forwarding
```shell
ssh -R 9000:localhost:3000 user@sshd_server 
```
When user access sshd_server:9000, it will be equal to access localhost:3000

The remote port forwarding is disabled by default, to use the feature, follow below steps:
1. /etc/ssh/sshd_config
1. add GatewayPorts yes
1. sudo service ssh restart

If you don't want the ssh shell, add ```-nNT```
e.g. 
```shell
ssh -nNT -L 9000:imgur.com:80 user@example.com
```