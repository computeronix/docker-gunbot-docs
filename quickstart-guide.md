---
description: How to get up and going quickly
---

# Quickstart Guide

## How to Get Started[​](https://marketplace.gunthy.io/extras/GunbotDocker#how-to-get-started) <a href="#how-to-get-started" id="how-to-get-started"></a>

### Docker Hub Repo

Access the [Docker Hub](https://hub.docker.com/r/computeronix/gunbot) to review tags and all the details of the container.

### Quick Start[​](https://marketplace.gunthy.io/extras/GunbotDocker#quick-start) <a href="#quick-start" id="quick-start"></a>

For the automated, quick start route, with your container tool, simply run

```
docker run -d computeronix/gunbot:latest
```

Once the image is downloaded, it will run and auto-start in usually about one minute or less.

If the port, by default 5000, is open on the host, and pass-thru the container, go to https://IPofCONTAINER:5000 (localhost could be used if local environment)

{% hint style="info" %}
PRO TIP: if this is the first time using Gunbot, or you need assistance setting up the config, open the port and pass-it through the container, then use the Web GUI to set it up. The Gunbot team has done an outstanding job with the Web GUI! DO NOT forget to use the persistent data option below if you plan to keep your data
{% endhint %}

### Example with persistent data and pass-through

```
docker run -d computeronix/gunbot:latest -p 5000:5000 -v "/host/directory/to/volume:/mnt/gunbot"
```

