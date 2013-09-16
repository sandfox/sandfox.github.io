---
title: "Building Nginx with RTMP Support"
layout: post
---


This post will hopefully guide you through building a stable version of Nginx with RTMP support for Ubuntu 12.04 LTS.
For anyone who has no idea what RTMP is look at [wikipedia](http://en.wikipedia.org/wiki/RTMP) and for those who don't get why it could have anything to do with Nginx check out [this site](http://rarut.wordpress.com/about/) and the [Github Repo](https://github.com/arut/nginx-rtmp-module). This end product should be a collection of deb files which can be installed on any other Ubuntu 12.04 server running the same architecture (might work on other architectures but I've never tried).


Before anyone goes overboard in pointing out any flaws, this is just a quick 'n' dirty guide. Ideally it would be nice if this was added to the semi-official nginx PPA or added as it's own PPA. Also please note that this adds the rtmp module to every build (light, full and extras), if you are after efficiency or cleanliness you will probably want to either alter the 'light' build or produce your own variant.


###Preparation

I'll be using a clean install of ubuntu server 12.04 (64bit) for this demo. This can be running anywhere (Amazon EC2, VirtualBox, KVM), I personally prefer using VirtualBox on my macbook to keep everything cleans yet local.
In case anyone is interested my current rig for this is VirtualBox 4.1.22 running on OSX 10.8.2 and the VM has 1GB RAM with 2 1.6 Ghz cores.

For this procedure I'll be using a non-root user (sandfox) that gets created by default during installation, so if you don't have one please create one. You generally shouldn't build/compile stuff as root.

To get my vm tooled up I ran the following commands:


	sudo apt-get dist-upgrade -y  
	sudo apt-get install build-essential git python-software-properties devscripts  
	sudo add-apt-repository ppa:nginx/stable -y  
	sudo apt-get update

which installs all the necessary build tools bits and bobs and allows us to use the unofficial but well maintained Nginx PPAs


###Building the Debs

1.	First off lets make a folder for a our build activities to take place in and allow our non-root user access:
`sudo mkdir /build && sudo chown sandfox:sandfox /build'
2.	Lets move into the build folder and and unpack the nginx source and while we are at it grab the build dependencies
`cd /build && sudo apt-get source nginx`
3.	Move into the source dir
`cd nginx-x-y-z && sudo apt-get build-dep nginx-full`
4.	Grab the nginx-rtmp-module source from github and put it into modules folder for the nginx source.
`cd debian/modules && git clone git://github.com/arut/nginx-rtmp-module.git`
Optionally if you want to go for a particular tag or branch you should run a `git checkout X` in the `nginx-rtmp-module` directory
5.	Move back debian directory ('/build/nginx-x-y-x/debian' in my case)
`cd ..`
6.	Add the module to the `configure` rules in the `rules` file in the current directory for all the versions (light full, extras). Look for a line similar to the following `--add-module=$(MODULESDIR)...` for each version and add this line beneath it
`--add-module=$(MODULESDIR)/nginx-rtmp-module \`
7.	Make an update to the changelog (as long as it's in a valid format anything goes) using this command
`dch -i`
8.	Move up one directory (to and rebuild the packages (grab some tea at this point)
`cd .. && sudo dpkg-buildpackage -uc -b`

Move up one directory and you should find a collection of debs that can be installed using `sudo dpkg -i PACKAGE_NAME.deb` (you'll need to move all the debs to where-ever you wish to install nginx+rtmp)
  

  
###Further Work

There is probably alot that can be improved upon with this process so if anyone has any suggestions or finds any problems with the above please let me know either by twitter, email, or raise an issue/PR on the GitHub repo for this blog.


