---
layout: single
title: "Debugging PNDs on the OpenPandora, for 'Digital: A Love Story'"
excerpt: "A description of how to debug PND packages on the OpenPandora, to check broken script error output. I debugged 'Digital: A Love Story' via this method."
tags: [OpenPandora, Pocket PC, Linux, Visual Novel]
category: blog
modified: 2015-02-14
comments: true
---

The [OpenPandora](http://boards.openpandora.org/page/homepage.html) is the last great Linux Pocket PC/Ultraportable, a form factor that time forgot after the wave of iPhones and Android multitouch mobile devices. 

It's a fully-featured Linux computer running Angstrom Linux. It has a gamepad with two joysticks, and a full PC keyboard, making it the best way to emulate home computer games on the go.

## Scenario

For some reason, the RenPy game "Digital: A Love Story", no longer works on the latest Pandora OS.

Before I had a OpenPandora, I used the Nokia N900 to play this game (by unzipping the squashfs image). So why does it no longer work?

Here's how you debug a broken PND script on the OpenPandora.

## Command Line Output

The first step was to run the PND from the command line, so I could see exactly what was failing.

~~~ bash
    pnd_run /media/mmcblk0p1/pandora/menu/digital1.freamon.40n8e.pnd
~~~
    
This showed that the PND mounted correctly, but the starter script `startDALS.sh` was failing to run. However, `pnd_run` did not show me the actual error.

### Start Script Manually

The only way to see the actual error in the script is to run it directly from the command line. First, I had to actually mount the PND: but `pnd_run` kept automatically unmounting after the script failed.

Use the following command to mount the PND indefinitely:

~~~ bash
    /usr/pandora/scripts/pnd_run.sh -p /media/mmcblk0p1/pandora/menu/digital1.freamon.40n8e.pnd -m
~~~
    
Now we can access the PND like any normal folder. It's under `/mnt/utmp/` .

~~~ bash
    cd /mnt/utmp/digital1/
~~~
    
I ran the script `startDALS.sh`from the command line:

~~~ bash
    ./startDALS.sh
~~~
    
And now the error was clear. RenPy failed to find the Python 2.6 library, and could not start.

~~~ bash
    ImportError: libpython2.6.so.1.0: cannot open shared object file: No such file or directory
~~~
    
The reason why it cannot import Python 2.6 is because the Pandora OS upgraded to Python 2.7. Since Python 2.7 is fully compatible with previous editions, we can make a symlink:

~~~ bash
    sudo ln -s /usr/lib/libpython2.7.so.1.0 /usr/lib/libpython2.6.so.1.0
~~~
    
Now, the `startDALS.sh` script works perfectly, and we can go on our merry way.

Once you are done with your debugging, use the following command to unmount the PND:

~~~ bash
    /usr/pandora/scripts/pnd_run.sh -p /media/mmcblk0p1/pandora/menu/digital1.freamon.40n8e.pnd -u
~~~
    
## Edit a PND

Notice that the PND was not modified at all, this is just the debugging stage. To edit a PND, you need to use a special tool: or you can just put it together manually.
