# PI CRUST Server

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/replicator.jpg)

### *Local media on local networks*

### [index.html](index.html)

### [Github repository at github.com/lafelabs/picrust](https://github.com/LafeLabs/picrust)

This is local media.  We can install web servers on *everything*: mac and Windows laptops and desktops, Raspberry Pi, and Android and iOS Devices.  Any device can be a server, and we drop files on it to share with others on the same wireless network.  When every device is a server as well as a client, people who share wireless networks can media without the Cloud.  

Digital media content creators are supported by brick and mortar venues.  When a wireless network is the source of a constant stream of interesting and original media content, that brings people into that space.  Creators can both get sponsorships from venues and direct material support.  

This is a way to share media on the Web without the Internet, without the Cloud, without e-commerce, without algorithms or apps or the app store.  There is no user data because there are no users, just files in folders which everyone on the network can download.  The only information we ever put on the network is information we want to share freely.  

The construction of this network represents the building of digital community that is always centered on physically shared spaces.  


## Use Cases

 - music and art publication/distribution in venues like bars, art galleries, and coffee shops(artists compensated by venues to produce content)
 - medical literature .pdf's in medical waiting rooms
 - local web pages shared from server to server of local organizations, people, places, businesses, artists, etc.(local web)
 - local classifieds and personals ads
 - media for exchange of physical goods: share, give away, buy, and sell crafts, technology, food, locally made goods and unwanted objects, facilitate upcycling 
 - local financial markets, moderating deals between physically local business people
 - music sharing in religious communities(record audio and post to wifi) 
 - local plant, animal, fungus, soil, weather and water knowledge sharing 
 - creating foundational documents for local organizations whose existence is primarily on these local wifi-based networks
 - Documenting self-replicating things made from trash: trash magic
 - Free sharing of books, local library infrastructure, extension of Public Library system
 - censorship-resistant news distribution, local news
 - rapid creation of historical documents during historical events on location for replication to archives afterward
 - immersive text-based games, mixed reality


Scroll down to see how to install the PI CRUST server on a machine.  If many people will use a server, we want something like a [Raspberry Pi](https://www.raspberrypi.org/) that is dedicated for this purpose.  Raspberry Pi is increasingly hard to buy, but they can often be found for donation from the community from people who have them but don't use them.  Also, we can take any old laptop or desktop, wipe the hard drive clean(to avoid security issues) and install Linux, then follow the same instructions as for the Pi to install the server on it.  

The main page of the PI CRUST server is just a simple list of links:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/picrust.png)

Click the link to the local web and you'll see a list of all the .html files in the "web/" directory on the server.  

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/localweb.png)

To make a new web page, click the link from the page web/index.html to "WEB EDITOR" and you can edit that main web page and build new web pages.  To destroy web pages you can click the link to "web destroyer".  

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/webeditor.png)

All web pages should end with ".html".   You can also use this editor to create [JavaScript](https://www.w3schools.com/js/default.asp) files(.js) and [CSS](https://www.w3schools.com/css/default.asp) files(.css) for local web development.  Teach yourself web development using the tutorials at [w3schools.com](https://www.w3schools.com/), starting with HTML(https://www.w3schools.com/html/default.asp).  You can follow along the tutorials by editing your own private home page on a PI CRUST server.

A very simple way to make a local media server on which people can share simple advertisements for literally anything is to host images of small screenshots and photographs.  We do this with the image feed, linked from the main page via the "Images" link.  The Image Feed has buttons to select an image to upload, then upload the image to the server.  Any image larger than about 1 megabyte won't upload.  For large images, either crop them or screen shot them and then crop the screenshot(this reduces the resolution and makes smaller files).

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/images.png)

Anyone can delete any image by turning "delete mode"  on, and then clicking the "DELETE" buttons.  Deletion is forever! Backup everything you care about!  Don't want to lose a thing? Copy it again and again.

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/images-delete.png)

In general, media files we want to share can be dropped into folders which are placed in the "media" folder on the servers.

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/media.png)

The entire system is self-editing, self-replicating, and self-contained.  Each server contains a code editor which can edit the whole system including itself.  Among the set of files on each system is also a set of scripts which clone the whole system.  Files are cataloged using the script [dnagenerator.php](php/dnagenerator.txt), which creates a file called [data/dna.txt](data/dna.txt) which is finally used by [replicator.php](php/replicator.txt) to copy all the code in the system from one server to the next.  Because all this is free Public Domain code we can host it on Github for free and replicate from there, but once it's replicating out in the wild, we can replicate from one server to another without referencing back to Github if we want. At any time, any instance can then be cloned to a local directory which is pushed out to a public Github repository which can the replicate out globally.  Thus we can move smoothly between totally local private replication and public replication to potentially billions of devices using Github's free hosting of open source projects(or anyone's random personal home pages on the public World Wide Web).

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/editorphp.png)

QR Codes allow us to quickly exchange a link from one mobile device to another for rapid sharing of links to local servers in a physical space.  These can also be printed out and posted in a public space for getting onto servers smoothly. When you first go to [qrcode.html](qrcode.html) it will load whatever web address is in the browser bar of whatever machine you're looking at it on.  

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/qrcode.png)

You can enter *any* address into the text input and hit "enter" to load any arbitrary QR code.  These can then be screen shotted and uploaded to the [Image Feed](images.html) for rapid sharing of a specific domain.

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/qrcode-trashrobot.png)

To point to a server, find the IP address of the machine by looking at the wifi settings:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/ip-address.png)

Then put into the qrcode page the address "http://your ipv4 address".  You can also put in an [IPv6 address](https://en.wikipedia.org/wiki/IPv6) by putting it inside square brackets. So for example link for a 4 number ip(ipv4) address

```
http://10.0.0.7
```

### Installation on Windows or Mac

First, install XAMPP, a free open source web server for all platforms.  [Download from www.apachefriends.org](https://www.apachefriends.org/index.html).  Click on windows to download, and click through to install everything.

![](https://i.imgur.com/G90zeyE.png)

After you download and install it, run it and start Apache.  You should see a control panel like this:

![](https://i.imgur.com/wgpIqfH.png)

Click on "Explorer" to get access to where the files are.  From the main directory called xamp, you want the sub-directory "htdocs".  Open this, delete the index.php file, and create a new file called replicator.php which you copy and paste the replicator at [php/replicator.txt](php/replicator.txt) into, and save.  

![](https://i.imgur.com/EpHYYOd.png)

Point a web browser on the same computer to [http://localhost/](http://localhost), then click on replicator.php.  This should replicate the whole system into the directory.  When this is done, click the link to go to the main page. 


Create a shortcut on the desktop to the "media" folder in order to make it very easy to drag and drop media into it. 

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/media-shortcut.png)

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/media-path.png)

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/readme-images/media-folders.png)


### Install on Pi

Raspberry Pi is now impossible to buy.  Find them donated from someone. Most people who have them don't use them or used them once and stopped due to lack of interest/time/need. Ask around!  Someone will be able to donate a Pi, keyboard, mouse, screen, power supply and whatever other random things you need to get set up.

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

## Install PI CRUST 

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

Check the IP address by hovering over the wifi icon, put that into the browser on another machine on the same local wifi network to see and edit the server.  Or open a browser on the pi and point it to [http://localhost](http://localhost)

 

### Install on Android


To run a Geometron Server on an Android, we will install the commercial software ksweb pro.

![](https://i.imgur.com/Q8Q7gaR.jpg)


[link to play store to install ksweb](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwiLrtjPw6fxAhUQu54KHWkyAjIQFjAAegQIBRAD&url=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dru.kslabs.ksweb%26hl%3Den_US%26gl%3DUS&usg=AOvVaw2ChVP4ojXIuGxVe-JjtEV3)

[https://www.kslabs.ru/](https://www.kslabs.ru/)

Install KSWEB on the Android, and turn it on.  Get the paid version. It is worth it, there are lots of broken web servers out there or ones with crappy features and tons of ads.  This is critical infrastructure for Geometron and it's worth supporting the developer of this useful tool.  Be sure PHP is also turned on.  

This is what it looks like when it is on:

![](https://i.imgur.com/EKjyekx.png)

Use the Editor built into the system to create a new file called replicator.php in the directory htdocs on the sd card as shown above, and to copy/paste into that the file in [php/replicator.txt](php/replicator.txt).  Save that, and delete index.php. Point a browser to the address [http://localhost:8080](http://localhost:8080).  Click on replicator.php and wait for the system to copy.  Sometimes it might time out, try it again.  When the system has replicated, make sure your phone is on a local wifi network, and turn the server off and on again, and you will get an IP address for the phone which is shown in the app.  The link for any other machine on the network other than the phone is the IP address followed by colon and then "8080".  E.g. http://192.168.0.19:8080/.  Share this link via email, text message, and links on other servers so that anyone on your network can see your server and edit it.  

### Replicate the Github using localhost

 - install PHP on your machine
 - create a new github repository on a CC0 PUBLIC DOMAIN license and clone it on your machine
 - copy the file [php/replicator.txt](php/replicator.txt) into a file called replicator.php in the new repo directory
 - run `php replicator.php` on your machine, wait for all the code to copy
 - push all that code up to your github repo
 - in the same directory, type `sudo php -S localhost:80`
 - go to [http://localhost](http://localhost) and you should get back to this screen, edit all elements of the system
 - use [editor.php](editor.php) to edit the file php/replicator.txt so that the two urls are the global url for *your* repo for both dna and replicator
 - after you've edited the code, click [text2php.php](text2php.php) to convert that to php
 - push your code to your github repo
 - use the new replicator code on your github repo to replicate out that instance to all other servers(linux, windows, mac, android) and forks
 - when you figure this out, make youtube videos showing other people how to copy the whole system 

# simplecube

We build cubes from corrugated cardboard and post links back to the document which describes how to make those cubes.

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/github.jpg)


The tools to replicate the cube: box cutter, pen, ruler

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/tools.jpg)

We cut 2 of these out:  

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/noholeside.jpg)

And 2 of these:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/holeside.jpg)

Then one of these:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/bottom.jpg)

And the 5 pieces look like this:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/layout.jpg)

Which are assembled into the Simple Cube:

![](https://raw.githubusercontent.com/LafeLabs/picrust/main/simplecube/uploadimages/simplecube.jpg)

Cubes are stacked. They are used to store the tools to make more cubes.  They are decorated with geometric fractals using the tools of Geometron and Action Geometry.  They can be linked with sharpie to social media accounts, web pages, physical places, or people.  This physical object is a physical hyperlink to anything you want it to be.  Cubes can be used to build robots, plant plants, create nano-compost projects and fungi growth projects, earthen walls, art tool holders, or anything else we can think of.  We link cubes with code and code with cubes.

### [Replicate Web 1.0 Pages](https://github.com/lafeLabs/web)



