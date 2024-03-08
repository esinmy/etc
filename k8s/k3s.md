# k3s specific commands

To see what images have been pulled locally:

```
k3s crictl images
```

To delete any images no currently used by a running container:

```
k3s crictl rmi --prune
```

Reference:
- [How to clean unused images, just like docker system prune](https://github.com/k3s-io/k3s/issues/1900)