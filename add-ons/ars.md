# ARS

GitHub Repository: [https://github.com/computeronix/docker-](https://github.com/computeronix/docker-zyb0t)[ars](https://github.com/computeronix/docker-ars)

Docker Hub: [https://hub.docker.com/r/computeronix/](https://hub.docker.com/r/computeronix/zyb0t)[ars](https://hub.docker.com/r/computeronix/ars)

## Overview

ARS is an add-on for the Gunbot trading system.

## Highlights

Key capabilities of this container:

* Auto-builds with the latest **stable** version of Gunbot, use the tag `:latest`
* Auto-builds with the latest **beta** version of Gunbot, use the tag `:beta`
* Multi-platform support ( `amd64` and `arm64` )
* Supports the latest version of the ARS releases.

## Licensing

ARS requires a license. A license can be acquired from the [Gunthy Marketplace](https://marketplace.gunthy.io/for-gunbot-market-maker/ars-intelligent-trend-algo).

## How to Get Started[​](https://marketplace.gunthy.io/extras/GunbotDocker#how-to-get-started) <a href="#how-to-get-started" id="how-to-get-started"></a>

### Docker Hub Repo

Access the [Docker Hub](https://hub.docker.com/r/computeronix/ars) to review tags and all the details of the container.

### Quick Start[​](https://marketplace.gunthy.io/extras/GunbotDocker#quick-start) <a href="#quick-start" id="quick-start"></a>

For the automated, quick start route, with your container tool, simply run

```
docker run -d computeronix/ars:latest
```

Once the image is downloaded, it will run and auto-start in usually about one minute or less.

If the port, by default 5000, is open on the host, and pass-thru the container, go to `https://IPofCONTAINER:5000` (localhost could be used if local environment)

{% hint style="info" %}
PRO TIP: if this is the first time using Gunbot, or you need assistance setting up the config, open the port and pass it through the container, then use the Web GUI to set it up. The Gunbot team has done an outstanding job with the Web GUI!

DO NOT forget to use the persistent data option below if you plan to keep your data
{% endhint %}

### Example with persistent data and pass-through

```
docker run -d computeronix/ars:latest -p 5010:5000 -v "/host/directory/to/volume:/mnt/gunbot"
```

In the above example, Gunbot would be available on `https://IPofCONTAINER:5010` and data would persist on the mounted directory `/host/directory/to/volume`.

## Support

* Review the ARS documentation for setup, ask crazymop or bestnaf for a copy of it
* Join the Telegram Community, ask crazymop or bestnaf for access to it.
* Submit issues/feedback/feature requests at the \[[GitHub site](https://github.com/computeronix/docker-ars/issues)]
