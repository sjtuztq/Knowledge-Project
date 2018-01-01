# Setting Up SSH
For a long time, I got stuck with ssh  x forwarding issues on my Macbook Pro. This article will demonstrate the process to properly setup ssh, enable X Forwarding on Macbook. (Hopefully on Linux client as well)

## Prevent SSH timeout
Edit `/etc/ssh/sshd_config`, add this line:
```bash
ClientAliveInterval 120     # avoid ssh timeout
```
Then the client will send a dummy package to the server every 2 minutes, keeping the connection alive

## SSH X forwarding
### Client Side
Edit `/etc/ssh/sshd_config`, make sure you have these lines:
```bash
X11Forwarding yes           # enable X11 forwarding
```

### Server Side
Usually server side works OOB, however, if anything unexpected happens, it is always useful to check server ssh configuration `/etc/ssh/ssh_config`
```bash
ForwardAgent yes        # default value should be yes
ForwardX11 yes          # default value should be yes
ForwardX11Trusted yes   # default value could be no? not sure    
```

## Slow SSH connection?
I have tried a few tweaks, dns, authentication, etc.
However, It turns out that slow ssh connection is caused by either slow network or slow machine. So there is no better solution than changing network or changing machine...

Good luck.
