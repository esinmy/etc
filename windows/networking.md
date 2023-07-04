## Issue with ports availability

For example, when running a container with exposed ports one can receive the following message:
```
Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:6379 -> 0.0.0.0:0: listen tcp 0.0.0.0:6379: bind: An attempt was made to access a socket in aions.
```

Check all ports that in use:
```
netstat -aon
```

If the required port is not in the previous list, then check excluded port range list:
```
netsh int ipv4 show excludedportrange protocol=tcp
```

If the port is in excluded port range list it can be because of variety reasons. One of them is Windows NAT. Solution is stop and run WinNAT:
```
net stop winnat
net start winnat
```

Reference:
- [docker: Error response from daemon: Ports are not available](https://github.com/docker/for-win/issues/9272)
- [Solve excluded port range](https://superuser.com/questions/1604199/find-who-excluded-port-range)




