## [Pi Crust](https://github.com/LafeLabs/picrust)
 
 1. flash the raspberry pi SD card
 2. Set up Raspberry pi hardware
 3. put Apache web server on the pi
 4. set up picrust server on pi
 4. create desktop shortcuts to mp3 and images folders on pi
 5. install xampp web server on home machine
 6. setup picrust server on home machine
 7. Create desktop shortcuts for mp3 and images  folders on home machine
 8. put home machine on private wifi with pi, point pi to home machine, download files into correct folder on pi
 9. put pi on wifi network in venue
 10. print out QR code to scan onto the pi based on its IP address
 11. point a web 1.0 page to the venue, machine, person, event, server, place
 12. the pi should get mail to operator at the web 1.0 page, and the operator can just save attachments to the image or sound folders
 13. anyone in the venue can scan qr code or link on web 1.0 to get to picrust server, then download and listen to songs, see images

Put mp3's in the mp folder.  Put images in the image folder. 

 - [editor.php](editor.php)
 - [localhost/editor.php](http://localhost/editor.php)
 - [README.md](readme.html)
 - [Global replicator link](https://github.com/LafeLabs/picrust/blob/main/README.md)
 - [http://localhost/](http://localhost/)
 - [www.trashrobot.org](https://www.trashrobot.org)

## Basic Raspberry Pi kit with screen:

 - [Raspberry Pi 4 4 gb($55, pishop.us)](https://www.pishop.us/product/raspberry-pi-4-model-b-4gb/)
 - [microSD Card and SD adapter($7, pishop.us)](https://www.pishop.us/product/microsd-card-32-gb-class-10-blank/)
 - [SD card reader($3, Pishop.us)](https://www.pishop.us/product/high-speed-micro-sd-card-reader-maximum-128gb-black/)
  - [HDMI Screen($102, Sundfounder)](https://www.sunfounder.com/collections/monitors/products/7-inch-hdmi-monitor)
 - [raspberry pi keyboard and mouse, official, from sunfounder($36)](https://www.sunfounder.com/collections/keyboard-gamepad/products/keyboard-mouse)
 - [raspberry pi wall power supply($8, pishop.us)](https://www.pishop.us/product/raspberry-pi-15w-power-supply-us-black/)


## Terminal Assembly

![](https://i.imgur.com/Y46szlG.jpg)

![](https://i.imgur.com/N4ItAdo.jpg) 

## Solar power kit

 - [solar panel and charger, (Amazon $60)](https://www.amazon.com/SOLPERK-Controller%EF%BC%8C-Automotive-Motorcycle-Powersports/dp/B07TTMF3FZ)
 - [barrel connector pigtails ($10 for 10 pack)](https://www.amazon.com/dp/B0915T6NLL)
 - [12 V 9 A-h lead acid battery($40 Amazon)](https://www.amazon.com/Mighty-Max-Battery-Replacement-Electric/dp/B00KAVH1GU/)
 - [12 V to USB charger converter, (Amazon $16)](https://www.amazon.com/dp/B09FKHK5MY)
 - [adafruit panel voltmeter $8](https://www.adafruit.com/product/575)


##  Set up the Raspberry Pi

Get a SD card with 8 GB or more storage and a SD card USB reader

Download and install, then use the Raspberry Pi Imager:

[https://www.raspberrypi.org/software/](https://www.raspberrypi.org/software/)

Turn on the pi click through all the things, put it on the wifi network.

## Install Apache and PHP so that geometron can run

Open a command prompt(black link on menu bar) and type:

```
sudo apt update
sudo apt install apache2 -y
sudo apt install php libapache2-mod-php -y
```


## Install geometron with this document for self-documentation and replication

```
cd /var/www/html
sudo rm index.html
sudo curl -o replicator.php https://raw.githubusercontent.com/LafeLabs/picrust/main/php/replicator.txt
cd ..
sudo chmod -R 0777 *
cd html
php replicator.php
sudo chmod -R 0777 *
```

## Create desktop shortcuts to the mp3 and image directories

```
cd ~/Desktop
ln -s /var/www/html/images images
ln -s /var/www/html/mp3 mp3
```


## Install on Windows or Mac

First, install XAMPP, a free open source web server for all platforms.  [Download from www.apachefriends.org](https://www.apachefriends.org/index.html).  Click on windows to download, and click through to install everything.

![](https://i.imgur.com/G90zeyE.png)

After you download and install it, run it and start Apache.  You should see a control panel like this:

![](https://i.imgur.com/wgpIqfH.png)

Click on "Explorer" to get access to where the files are.  From the main directory called xamp, you want the sub-directory "htdocs".  Open this, delete the index.php file, and create a new file called replicator.php which you copy and paste the replicator at [php/replicator.txt](php/replicator.txt) into, and save.  

![](https://i.imgur.com/EpHYYOd.png)

Point a web browser on the same computer to [http://localhost/](http://localhost), then click on replicator.php.  This should replicate the whole system into the directory.  When this is done, click the link to go to the main page.  You should see a new Geometron instance:

![](https://i.imgur.com/b8iZDRF.png) 

When this loads, you need to get the IP address of this machine, which you do by clicking from the main XAMPP screen(shown at the top of this scroll) to "netstat".  You will now see a bunch of processes on various IP addresses.  Look at the web browser you opened which you pointed to "localhost" and you will see the IP address of this machine.  Create a link to it by starting with "http://" and then adding the IP address.  Share this link with yourself and anyone else on the local wifi network via email or text message or link on an existing server.

![](https://i.imgur.com/XqBnJIY.png)

Also, to have a record of it which is easy to share, add a link to it at the top of the home scroll for the new server.  You can also add a link to qrcode.html at the top of the new home scroll so that it is easy to replicate a link from one mobile device to another when they are all on the same wifi network, all looking at the same Windows server.

To understand what this is for, read the [Book of Geometron](scrolls/bookofgeometron.md).  Learn to use the Factories. 


```