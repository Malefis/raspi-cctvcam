# Malefis' RPi webcam stream
My school had multiple Raspberri Pi 3s lying around, all being unused.
After experimenting with hosting an NGINX powered RTMP server on my windows PC so that I could live stream from my phone to my PC - I realised this would work well on a Pi.

## The Server
This is not normally used, but I recommend doing all of this as root to skip the use of Sudo

    $ sudo su

Next, we need to install all of the pre-requisites for NGINX to work on our raspberry pi

    sudo apt-get install build-essential libpcre3 libpcre3-dev libssl-dev unzip

NGINX is a a web-server application that does not normally come with the ability to do RTMP streaming, we will need to set this up for ourselves.

 1. Find the version number of the latest stable model of NGINX using [this link](http://nginx.org/en/download.html)
 2. Download the latest version using wget, for this example I am using 1.15.8 
     `$ wget https://nginx.org/download/nginx-1.15.8.tar.gz`
 3. Download the NGINX RTMP source code from github
     `$ wget https://github.com/sergey-dryabzhinsky/nginx-rtmp-module/archive/dev.zip`
 4. Unzip & Unpack both of these, then enter the NGINX directory
     `$ tar -zxvf nginx-1.15.8.tar.gz && unzip dev.zip && cd nginx-1.15.1`
5. Build NGINX
    `$ tar -zxvf nginx-1.15.8.tar.gz`  
    `$ unzip dev.zip`  
    `$ cd nginx-1.15.8`
6. Use this command to run your server
    `$ sudo /usr/local/nginx/sbin/nginx`

## Setting up RTMP on the Pi

We need to manually add in the RTMP module to our server to be able to stream to it



