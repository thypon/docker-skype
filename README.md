Docker! Skype! XPRA!
==========================

Run Skype inside an isolated [Docker](http://www.docker.io) container on your Linux desktop! See its sights via X11 forwarding! Hear its sounds through the magic of PulseAudio and SSH tunnels!

Known Issue: While audio works flawlessly during calls and Skype is perfectly usable, the notification sounds such as call ringing do not work.

Inspiration from [skype-pulseaudio](https://github.com/tomparys/docker-skype-pulseaudio)


Building Instructions
=====================

1. Build the container

        docker build -t skype .

2. Run the container and forward the appropriate port

        docker run -d -p 127.0.0.1:22222:22 skype

3. Run skype with XPRA

        xpra attach ssh:docker@localhost:22222:10

Frequently Asked Questions
==========================

Why would I want to do this?
----------------------------
There are a couple of reasons you might want to restrict Skype's access to your computer:

* It is proprietary Microsoft software
* The skype binary is disguised against decompiling, so nobody is (still) able to reproduce what it really does.
* It produces encrypted traffic even when you are not actively using Skype.
