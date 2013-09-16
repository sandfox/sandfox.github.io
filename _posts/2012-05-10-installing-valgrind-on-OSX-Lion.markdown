---
title: "Installing valgrind 3.7.0 from source on OSX Lion 10.7.3 with Xcode 4.3.2"
layout: post
---

This should be very easy and take all of 2 mins but turns out it's full of minor hurdles due to wierd installation behaviour Xcode now exhibits. If you're wondering why `make` can't be found or for that matter any of the usual build tools you'd expect aren't to about then read on.

1. Install Xcode from the App store
2. Open Xcode, then go to the preferences menu and select the Downloads tab. You should be presented with 4 or 5 items of which the bottom one should be _Command Line Tools_. Click the install button to it's right, wait a bit for it finish.
3. Open a terminal session if you haven't already and enter this `sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer/` which will tell OSX where it can find Xcode's developer tools (bizare I know!)
4. Download the [valgrind source](http://www.valgrind.org/downloads/current.html) (3.7.0 at time of writing)
5. Unpack the source to a suitable directory. I unpacked mine to `/opt/valgrind` (don't ask why - i'm odd)
6. If you are not already, open a terminal session and `cd` into the directory where you put valgrind source 
7. Run this command `./configure --prefix=/usr` to configure the source (for some reason using `/usr/bin` stuck it in `/usr/bin/bin`)
8. And this command to make it `make`
9. Finally this command `sudo make install`
10. Test it works by opening a new terminal session and running this command `valgrind date`
11. Job done! Get writing and profiling some code.
