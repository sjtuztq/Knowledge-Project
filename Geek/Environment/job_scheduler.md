# Setting up Torque/PBS job scheduler on Linux server

## Arch Linux
Consult [Arch wiki: torque](https://wiki.archlinux.org/index.php/TORQUE) for more infomation.


## Ubuntu
### Software installation
```bash
$ sudo apt-get install torque-server torque-client torque-mom torque-pam
```

### Configuration

Installation will set up torque with a default setup that helps in no way, you will have to stop the services and recreate a clean setup.
```bash
$ /etc/init.d/torque-mom stop
$ /etc/init.d/torque-scheduler stop
$ /etc/init.d/torque-server stop
```

Then, create a new database with:
```
$ pbs_server -t create
```


