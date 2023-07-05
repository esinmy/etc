## SSH port forwarding (SSH tunneling)

```
ssh -L local_port:destination_server_ip:remote_port ssh_server_hostname
# example
ssh –L 5901:188.17.0.5:4492 pnap@ssh.server.com
```
