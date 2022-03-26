# [PI CRUST](https://github.com/LafeLabs/picrust)
 
## by [TRASH ROBOT](https://www.trashrobot.org)

![](https://i.imgur.com/fmUlljl.png)

![](https://i.imgur.com/1ujLhzq.png)

![](https://i.imgur.com/Y5OekAp.png)

### ***GUERILLA LIBRARY***

## [link to http://localhost/](http://localhost/)

## [join the discord to put together a local crew](https://discord.gg/U6nT4eNX3y)

Share:

 - images
 - articles
 - music files
 - podcast files
 - video files
 - text games
 - pdfs of books and academic papers
 - private web pages
 - zines
 - ad boards
 - generative art
 - instructions

Over a local wifi network using a [Raspberry Pi](https://www.raspberrypi.org/).


PI CRUST lets us share media over wifi with a simple web interface and all cheap off the shelf hardware.  It requires no logins, no web pages, no apps or cloud or indeed any Internet access at all.  It merely requires that everyone sharing media be on the same local network, be it wifi or a wired local network.  Once set up, one drags and drops files into the image and media folders and they're posted.


### [replicator.php code](https://raw.githubusercontent.com/LafeLabs/picrust/main/php/replicator.txt)
 

## Get the parts you need

 - Find a donated Raspberry Pi if you can, they are now hard to buy, any model works. Ask nerds and ask nerds to ask their nerd friends, people get Pi's as gifts and then do nothing with them, find someone with an unused Pi.  Be sure to ask if it's a Pi 4 or an earlier model, that affects the power suppoly and HDMI cable you need to get.
 - [microSD Card and SD adapter($7, pishop.us)](https://www.pishop.us/product/microsd-card-32-gb-class-10-blank/)
 - [SD card reader($3, Pishop.us)](https://www.pishop.us/product/high-speed-micro-sd-card-reader-maximum-128gb-black/)
 - [raspberry pi wall power supply for Pi 4($8, pishop.us)](https://www.pishop.us/product/raspberry-pi-15w-power-supply-us-black/) **OR**
 - [Raspberry Pi wall power supply for 1/2/3](https://www.pishop.us/product/raspberry-pi-12-5w-power-supply-us-white/)
 - Any screen with an HDMI input
 - HDMI cable or HDMI micro cable if it is a Raspberry Pi 4
 - USB mouse
 - USB keyboard


## Flash the microSD card 

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
 - Click through the various startup menus which come up on boot to finish setup. In spite of dire warnings, keep the default password, this is an insecure-by-design machine, which should *never* have personal or private information ever.  If a pi is corrupted by hacking, just wipe the SD card and re-install.


## Install PI CRUST

If this looks overwhelming, ask around to find someone who does tech things to do this. Open a command prompt(black link on menu bar) and copy and paste each line one by one(right click on the terminal window to paste):


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
ln -s /var/www/html/media media
```

Now you should be able to drag and drop files into a pair of folders on the desktop marked "images" and "media" and they will appear in the server.  Open a web browser on the Pi and point it to [http://localhost/](http://localhost/) and you will see the server.  

This QR Code will not scan from localhost until the IP address has been set.  Hover the mouse over the wifi icon on the menu bar, copy down the IP address.  This will either be a series of numbers separated by dots(ipv4 address) or colons(ipv6 address).  For the Pi it will probably be the former.  Click the button with the wifi logo in the upper right hand corner of the main PI CRUST page to open the IP address input.  Replace whatever is in there with the current correct IP address of the pi and hit enter.  Click the button a second time to hide this input.  Now the QR code should scan for everyone on the wifi(but only if they're on the same wifi network!).  

Alternatively, you can write down the address, point the web browser of another computer to it, and disconnect the screen from the Pi, running it in "headless" mode.  

## Put Files on Server

 - put files on a thumb drive and transfer them to the folders **or**
 - download from other servers on the network or on the Internet to the folders **or**
 - set up an email account for the operator, log onto that dedicated email on the Pi, and as emails come in with attachments, download them and put them in the folders(NO PERSONAL or private information should be on the Pi ever).  This is how we can do real time music posts in a venue with a human on location.
 
## Windows and Mac Installation

 Download and install [XAMPP](https://www.apachefriends.org/index.html)
 
 ![](https://i.imgur.com/G90zeyE.png)
 
 Start it and run Apache. You should see a control panel like this:
 
 ![](https://i.imgur.com/wgpIqfH.png)
 
 Click on "Explorer" to get access to where the files are.  From the main directory called xamp, you want the sub-directory "htdocs".  
 
 Open htdocs and  delete the index.php file.
 
download the file [php/replicator.txt](https://raw.githubusercontent.com/LafeLabs/picrust/main/php/replicator.txt) by right clicking this link, then save it as "replicator.php" in the htdocs folder.  
 
 
 ![](https://i.imgur.com/EpHYYOd.png)

Point a web browser on the same computer to [http://localhost/](http://localhost), then click on replicator.php.  This should replicate the whole system into the directory.  When this is done, click the link to go to the main page.  Now localhost should be a standard PI CRUST server.  Edit the wall to say which physical machine this is.  

Now click on the "settings" for your wifi, and look for the "ipv4" IP address, which should be a sequence of four numbers separated by periods.  Click the wifi symbol in the upper right corner of the web browser to open the IP address input, replace the IP address there with your current IP address and hit enter, then click the wifi logo again to close the input.  The QR code should now scan to that machine.

To put media on the server, create shortcuts on your desktop to the two media folders, "images" and "media".  Drag and drop images into the image folder, drag and drop all other media files into the media directory.  Carry around a thumb drive with the two media folders, and you can quickly transfer all the files from one server to another, from pc to mac to pi.  

Now just leave your screen where people can see it and they can scan the QR code to copy the server page, then they can see all the imges, read and write to the wall, and download all the files.

On windows, the locations can be "c:\xampp\htdocs\media" and "c:\xampp\htdocs\images".  On any system, you can use the file explorer to find the path, then use that from whatever the shortcut creation method is(right click the desktop on Windows and select create new shortcut).

Keep media files on thumb drives to drop into folders on different servers and deliver on different networks.

## Web 1.0 Pages

Choose a location, like a street, a creek, a pond or lake, lagoon, boardwalk, public library, truck stop etc.  Think of a domain name for that place that ends with something other than .com. Install a Web 1.0 page from the repository for that at [github.com/lafelabs/web](https://github.com/LafeLabs/web).  Point that page to whatever PI CRUST servers are around.  Share and enjoy.
