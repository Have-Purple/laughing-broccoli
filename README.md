# laughing-broccoli
mjpg_Streamer Docker File

open terminal

clone this repo git clone https://github.com/Have-Purple/laughing-broccoli.git

cd into /laughing-broccoli folder

run docker-compose up -d

after some minutes octoprint is running on http://{LOCALHOST or HOSTNAME}:5000 and mjpg-streamer on https://{LOCALHOST or HOSTNAME}:8080/?action=stream

Navigate to http://{LOCALHOST or HOSTNAME}:5000 and fill out the welcome wizard

When arrived at the webcam part fillout the following values:

Stream URL: http://{IP or HOSTNAME}:8080/?action=stream

Snapshot URL: http://{IP or HOSTNAME}:8080/?action=snapshot

Path to FFMPEG: /usr/bin/ffmpeg

TIP: use docker inspect {container-name of mjp-stream} to find the IP adress for the snapshot url

Start Octoprint and mjpg-streamer on boot

Add docker to systemctl by running: sudo systemctl enable docker

run docker-compose up -d once in the clone repo location

you should now have a working Octoprint with webcam support. Don't forget to update the usb devices and webcam locations when necessary

My setup is based on X64 laptop running an octoprint docker container and this mjpg_streamer container with an attached Logitech C920 USB webcam.  Everything is colocated next to my PRUSA.

