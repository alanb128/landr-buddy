# landr-buddy
Easily upload a website and test with a public URL. This project uses [balenaCloud](https://dashboard.balena-cloud.com/) which provides a zero-configuration secure public URL for each device. (The first 10 are free!) This is designed for a Raspberry Pi Zero 2 W or Pi4, but should also work on a Pi 3.

## Installation
Set up a balenaCloud account, add a fleet and provision a device. Docs for getting started are [here](https://www.balena.io/docs/learn/welcome/introduction/).

## Upload a site 
This project uses Minio to upload files. Browse to the local IP of your device, port 9000 to access the uploading tool. (i.e. 192.168.1.65:9000 replacing the IP with your device's IP)

Select the "caddy" bucket (folder) from the left panel and then upload your site using the "+" icon in the lower left. If you have a lot of files, zipping them and uploading as one is helpful. (If you do that, ssh into the caddy service, go to `/usr/share/caddy` and unzip the file you uploaded.

## Browse your site
Either browse directly to the local IP address of your device, or enable the public URL in your balenaCloud dashboard and use that link.
