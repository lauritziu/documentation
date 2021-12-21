# Docker

# How to find the Mac host folder in the filesystem for anonymous docker volumes?
If you execute `docker inspect <containerId>` you can see Mountpoints for volumes the container is using.
The path shown is not an real path in the Mac OS filesystem, but relative to the Docker engine filesystem.
To translate this into a real filesystem path, do the following:

```
docker run --rm -it -v /:/docker alpine:edge
```

Once you have entered the container go to the directory:

```
cd docker/var/lib/docker/volumes/<name of volume>/_data
```





