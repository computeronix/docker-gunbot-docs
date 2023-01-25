---
description: Additional options and parameters available for advanced builds
---

# Advanced Setup

## Interrupt the startup

Interrupt the auto-start with the following command and feel free to do what you want: `docker run -it computeronix/gunbot:latest sh`

You will then get shell access to the container and can do what you want.

{% hint style="info" %}
Run the file `/opt/gunbot/startup.sh` when ready to fire off the bot
{% endhint %}

## Defaults

Default values that are out of the box:

* Port: 5000 (TCP)
* HTTPS is enabled with a self-signed certificate
* Gunbot Betas are supported (requires using Persistant Data)
* Supports custom SSL certificate (requires using Persistant Data)

## Command Options Supported

Supported command options as part of the Docker container:

### Support Host Time

Gunbot is a time sensitive application, as accurate timestamps are critical to communicate to exchanges, and depending on how long the container runs for you "may" want to allow the permission to change the system time, OR, you may want to consider getting a fresh container every so often (no longer than every 24 hours).

The parameter `--cap-add=SYS_TIME` is supported to allow the change time permission to occur on the container, but this may not work on all hosting platforms.

Supported parameter: `--cap-add=SYS_TIME`

### Support Website GUI Pass-Through Port

You may want to allow passing through your Website GUI port to getting access to the Website Management GUI of your Gunbot. By default the port is TCP 5000, run this command to pass-through the port `-p 5000:5000` and this can be customized as needed. The first `5000` is the HOST port and can be the port used to access from your host (Internet) and the second `5000` is the port configured in your Gunbot config (by default `5000`).

Supported parameter: `-p 5000:5000`

{% hint style="info" %}
Do not forget to open any firewall restrictions on your HOST network (5000 by default, port on left, source port).
{% endhint %}

{% hint style="warning" %}
Gunbot is intended to run on your local system. Making the Gunbot GUI available from outside networks is inherently risky, only do so on your own responsibility. Considerable efforts went into securing the GUI, but please understand that achieving 100% security is not realistic.
{% endhint %}

### Support Persistent Data

Containers are ephermal, which means when they complete their task, they end, and all associated data is lost. If there is data you want to keep as part of the container ending, you will want to mount a directory to preserve this data. Gunbot Docker container supports persistence if you decide you want to keep your Gunbot data. To support persistence add the parameter `-v "/host/directory/to/volume:/mnt/gunbot"` and the following directories and files in `/mnt/gunbot` will be redirected and saved to your mounted volume, `/host/directory/to/volume`.

Persistent Gunbot Directories and Files:

* ssl.config (to customize the created self-signed SSL certificate \[optional])
* localhost.key (to replace the self-signed SSL certificate)
* localhost.crt (to replace the self-signed SSL certificate)
* json directory
* logs directory
* backups directory
* customStrategies directory
* user\_modules directory
* config.js
* UTAconfig.json
* autoconfig.json
* gunbotgui.db
* new\_gui.sqlite

{% hint style="warning" %}
DO NOT use more than one instance to the exact same `/host/directory/to/volume/`, instead make sure you use different directories, for example you could use subdirectories in `/host/directory/to/volume/sub1 sub2 sub3 etc` so multiple running containers will not conflict with each other.
{% endhint %}

Supported parameter: `-v "/host/directory/to/volume:/mnt/gunbot"`

****
