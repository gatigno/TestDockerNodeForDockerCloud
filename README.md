# The Synereo Social Platform

#### WARNING

This is **experimental**, pre-release software and should be used **for testing purposes only**.

While the software is in pre-release phase, there is a **high likelihood of data loss** and **features will change** without notice.

## Requirements
* Basic knowledge of [Docker](https://www.docker.com)
  * New users should start [here](https://docs.docker.com/engine/understanding-docker/)
* A machine capable of running [Docker](https://www.docker.com), with at least 4 GB RAM (> 8 GB recommended)
  * For Linux users, installation information is [available here](https://docs.docker.com/engine/installation/linux)
  * For Mac users, system requirements and installation information is [available here](https://docs.docker.com/docker-for-mac/)
  * For Windows users, system requirements and installation information is [available here](https://docs.docker.com/docker-for-windows/)

## Installation

```
$ docker build -t synereo-node github.com/synereo/dockernode
```

The build process will take 10-30 minutes depending on your machine and network connection.

It will download around 750 MB of data.

## First Time Usage

After the build completes, run the following command:
```
$ docker run -itd -p 443:9876 -h mynodehost --dns 8.8.8.8 --name synereo-node-01 synereo-node
```

## Accessing the Synereo Social Platform

To access the application, you must first know the IP address of your running container.

On Mac machines, the IP address of your running container will be `127.0.0.1` (aka `localhost`).

On Linux and Windows machines, you can get the IP address of your running container with the following command:

```
$ docker inspect --format '{{ .NetworkSettings.IPAddress }}' synereo-node-01
```

You can then access the application with your web browser at:
```
https://<IP address>/
```

**NOTE**: When accessing the application for the first time, your browser will warn you that the site is insecure.  This happens because the pre-release version of this software uses a self-signed TLS certificate.  You should follow your browser's instructions about approving the site's certificate.

**Congratulations!**, you can now log in using the administrator account:

Username|Password
--------|--------
admin@localhost|a

**NOTE**: This username and password can be changed by editing the `eval.conf` file inside the running container.

Information on how to do this will be made available shortly.

## Stopping the Container

To stop the container:

```
$ docker stop synereo-node-01
```

## General Usage

To restart the container:

```
$ docker start synereo-node-01
```

## Further Help

Please visit the `#docker-testing` channel on [our Slack](https://slack.synereo.com).
