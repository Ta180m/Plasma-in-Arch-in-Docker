# Plasma in Arch in Docker

#### Because why not?

[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/ta180m/plasma-in-arch-in-docker)](https://hub.docker.com/r/ta180m/plasma-in-arch-in-docker)
[![Docker Image Size](https://badgen.net/docker/size/ta180m/plasma-in-arch-in-docker)](https://hub.docker.com/r/ta180m/plasma-in-arch-in-docker)

A docker image of Arch Linux with KDE desktop and VNC support.

## Screenshots

![Figure 1](./screenshots/1.png)


## Pull image

```
docker pull ta180m/archlinux-vnc
```

The tag can be one of those listed above.

## Usage

Simple usage:

```
docker run -d -p 5900:5900 -p 6080:6080 -e VNC_PASSWD=password ta180m/plasma-in-arch-in-docker
```

Then visit <http://localhost:6080> to visit noVNC UI.
Or you can use a different VNC client (like TigerVNC client)
and connect to localhost:5900.

If `VNC_PASSWD` is not set,
then the security type of vncserver is set to None,
it is **insecure** when exposing the container on the Internet.

## Exposed ports

* 5900: Used for VNC interface
* 6080: Used for noVNC Web UI

## Installed applications

* plasma-meta
* kde-system-meta
* konsole
* tigervnc
* noVNC
* wget
* firefox

## Build

```
docker build -t plasma-in-arch-in-docker .
```


## FAQ

### Scaling

By default, noVNC's scaling mode is set to None.
It can be changed in the noVNC panel easily.

