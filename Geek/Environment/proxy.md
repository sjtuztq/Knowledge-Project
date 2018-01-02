# Setup Shadowsocks on linux servers

## Install shadowsocks (CLI version)
```bash
$ sudo apt-get install shadowsocks
```


## Configuration
### Config file
create a file named shadowsocks.json, my current setup is:
```json
{
   "server":"c18cc.ams2.biuss.net",
   "server_port":15576,
   "local_port":1086,
   "password":"[password]",
   "timeout":600,
   "method":"aes-256-cfb"
}
```
### Start SS    
#### From the command line
The client is started with the `ss-local`/`sslocal` command. To start it using the configuration file `/etc/shadowsocks/config.json`:
```bash
# for arch linux
$ ss-local -c /etc/shadowsocks/config.json
# for ubuntu
$ sslocal -c /etc/shadowsocks/config.json
```
#### Using systemd
This only works if config files are under `/etc/shadowsocks/`. To start shadowsocks using `/etc/shadowsocks/foo.json`, execute:

![](https://placehold.it/15/f03c15/000000?text=+)Warning: This doesn't work under ubuntu (no such service name?)

```bash
$ sudo start shadowsocks-libev@foo.service
```
