# landr-buddy
Easily upload a website (such as one made with [Landr](https://getlandr.io/)) and browse it with a public URL. This project uses [balenaCloud](https://dashboard.balena-cloud.com/) which provides a zero-configuration secure public URL for each device. (The first 10 are free!) This is designed for a Raspberry Pi Zero 2 W or Pi4, but should also work on a Pi 3.

![buddy](https://raw.githubusercontent.com/alanb128/landr-buddy/main/photo.png)

## Installation
Set up a balenaCloud account, add a fleet and provision a device. Docs for getting started are [here](https://www.balena.io/docs/learn/welcome/introduction/). You can either clone this repo locally and use the [balenaCLI](https://www.balena.io/docs/reference/balena-cli/) to push to your device or use the deploy button below:

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/alanb128/landr-buddy/)

## Upload a site 
This project uses Minio to upload files. Browse to the local IP of your device, port 9000 to access the uploading tool. (i.e. 192.168.1.65:9000 replacing the IP with your device's IP)

Default username is `myminio` and password is `myminio123`

Select the "caddy" bucket (folder) from the left panel and then upload your site using the "+" icon in the lower left. If you have a lot of files, zipping them and uploading as one is helpful. (If you do that, ssh into the caddy service, go to `/usr/share/caddy` and unzip the file you uploaded.)

## Browse your site
Either browse directly to the local IP address of your device, or enable the public URL in your balenaCloud dashboard and use that link.

Note: The Caddyfile contained here is for reference only and is not used by the project. In the future I may add a way to modify it and include it in the project.

## Utility service
This service is used to access the shared site folder (`/usr/src/app/caddy` here) and perform optional configuration tasks. It also includes the [Minio client](https://docs.min.io/docs/minio-client-quickstart-guide.html). More functionality to come!
