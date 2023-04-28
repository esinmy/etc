# Nvidia System Management Interface #

Real-time insights on used resources updated (loop for -l) every second (if no argument is specified for the -l form a default interval of 5 seconds is used):
```
nvidia-smi -l 1
```

Another view of insights:
```
nvidia-smi -q -g 0 -d UTILIZATION -l 1
```

## Documentation reference ##
[Link](https://developer.download.nvidia.com/compute/DCGM/docs/nvidia-smi-367.38.pdf)


kubectl run --image=busybox load-generator  -i --tty -- /bin/sh

kubectl run --generator=run-pod/v1 run -i --tty load-generator --image=busybox /bin/sh
# Execute this while loop from inside the busybox pod
$ while true; do wget -q -O - http://php-apache; done