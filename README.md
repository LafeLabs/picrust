## [Pi Crust](https://github.com/LafeLabs/picrust)
 
 ***Become the Media***
 
 1. flash the raspberry pi SD card
 2. Set up Raspberry pi hardware
 3. put Apache web server on the pi
 4. set up picrust server on pi
 4. create desktop shortcuts to mp3 and images folders on pi, use a thumb drive to drag and drop files into the folders
 5. put pi on wifi network in venue
 6. put the pi on a public screen so people can see the qr code and the files, scan qr code and download and scroll the images

## What is the Pi Crust?

The Pi Crust lets us share music and images over wifi with a simple web interface and all cheap off the shelf hardware.  It requires no logins, no web pages, no apps or cloud or indeed any Internet access at all.  It merely requires that everyone sharing media be on the same local network, be it wifi or a wired local network.  Once set up, one drags and drops files into the image and mp3 folders and they're posted.


## Get support

The Pi Crust needs several people to cooperate in order to work.  We need content creators who want to share their work.  They can be sharing directly or can have their work shared by fans or peers.  We also need a community who is actively engaged with the content of the creators already, and will put effort into getting their work.  We need Operators, who will select, curate, and maintain the collection of files.  

## Get the parts you need

 - Find a donated Raspberry Pi if you can, they are now hard to buy, any model works
 - [microSD Card and SD adapter($7, pishop.us)](https://www.pishop.us/product/microsd-card-32-gb-class-10-blank/)
 - [SD card reader($3, Pishop.us)](https://www.pishop.us/product/high-speed-micro-sd-card-reader-maximum-128gb-black/)
 - [raspberry pi wall power supply for Pi 4($8, pishop.us)](https://www.pishop.us/product/raspberry-pi-15w-power-supply-us-black/) **OR**
 - [Raspberry Pi wall power supply for 1/2/3](https://www.pishop.us/product/raspberry-pi-12-5w-power-supply-us-white/)
 - Any screen with an HDMI input
 - HDMI cable or HDMI micro cable if it is a Raspberry Pi 4
 - USB mouse
 - USB keyboard


## Flash the SD card 

 Connect the microSD card reader to a USB port(if you don't have a USB A, you will need a converter from C to A or a USB C SD card reader)

Download, install, then use the Raspberry Pi Imager:

[https://www.raspberrypi.org/software/](https://www.raspberrypi.org/software/)


## Set up the Raspberry Pi

 - assemble the case if you have a case
 - put the microSD card in the slot on the pi
 - plug in the USB mouse
 - plug in the USB keyboard
 - connect the Pi to a screen with the HDMI cable, preferable one everyone in the venue can easily see
 - Plug the Pi into the wall
 - Click through the various startup menus to finish setup on boot
 

## Install Pi Crust

Open a command prompt(black link on menu bar) and type:

```
sudo apt update
sudo apt install apache2 -y
sudo apt install php libapache2-mod-php -y

cd /var/www/html
sudo rm index.html
sudo curl -o replicator.php https://raw.githubusercontent.com/LafeLabs/picrust/main/php/replicator.txt
cd ..
sudo chmod -R 0777 *
cd html
php replicator.php
sudo chmod -R 0777 *
cd ~/Desktop
ln -s /var/www/html/images images
ln -s /var/www/html/mp3 mp3
```

Now you should be able to drag and drop files into a pair of folders on the desktop marked "images" and "mp3" and they will appear in the server.  Open a web browser on the Pi and point it to [http://localhost/](http://localhost/) and you will see the server.  

This QR Code will not scan until the IP address has been set, which you can do with [editor.php](editor.php).  Hover the mouse over the wifi icon on the menu bar, copy down the IP address, and change it to that address in the file called data/ipaddress.txt.  

Alternatively, you can write down the address, point the web browser of another computer to it, and disconnect the screen from the Pi, running it in "headless" mode.  

## Put Files on Server

 - put files on a thumb drive and transfer them to the folders **or**
 - download from other servers on the network or on the Internet to the folders **or**
 - set up an email account for the operator, log onto that dedicated email on the Pi, and as emails come in with attachments, download them and put them in the folders(NO PERSONAL or private information should be on the Pi ever)
 



## Install on Windows or Mac

Do not use this in public ever unless you have wiped all personal information from the machine and keep it that way.

First, install XAMPP, a free open source web server for all platforms.  [Download from www.apachefriends.org](https://www.apachefriends.org/index.html).  Click on windows to download, and click through to install everything.

![](https://i.imgur.com/G90zeyE.png)

After you download and install it, run it and start Apache.  You should see a control panel like this:

![](https://i.imgur.com/wgpIqfH.png)

Click on "Explorer" to get access to where the files are.  From the main directory called xamp, you want the sub-directory "htdocs".  Open this, delete the index.php file, and create a new file called replicator.php which you copy and paste the replicator at [php/replicator.txt](php/replicator.txt) into, and save.  

![](https://i.imgur.com/EpHYYOd.png)

Point a web browser on the same computer to [http://localhost/](http://localhost), then click on replicator.php.  This should replicate the whole system into the directory.  When this is done, click the link to go to the main page.  


When this loads, you need to get the IP address of this machine, which you do by clicking from the main XAMPP screen(shown at the top of this scroll) to "netstat".  You will now see a bunch of processes on various IP addresses.  Look at the web browser you opened which you pointed to "localhost" and you will see the IP address of this machine.  Create a link to it by starting with "http://" and then adding the IP address.  Share this link with yourself and anyone else on the local wifi network via email or text message or link on an existing server.

![](https://i.imgur.com/XqBnJIY.png)

Also, to have a record of it which is easy to share, add a link to it at the top of the home scroll for the new server.  You can also add a link to qrcode.html at the top of the new home scroll so that it is easy to replicate a link from one mobile device to another when they are all on the same wifi network, all looking at the same Windows server.

To understand what this is for, read the [Book of Geometron](scrolls/bookofgeometron.md).  Learn to use the Factories. 


```