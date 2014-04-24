linux-pc-developer-setup-guide
===============================

This guide will help software developers to set up a Linux based PC to be used as a workstation.

# Overview

OK, so there's a ton of different ways to set up a workstation - and all developer's needs will be different.  This guide is meant to describe various tools and configurations which will be of use to developers.  Developers are expected to mix and match the tools described in this guide and select the ones most useful to their requirements.

Each tool or configuration is described first in generic detail - and then more specific instructions are added for different distributions.

Please send through any patches etc to improve/correct the document - especially how to make the changes for different distributions.

# Prerequisites

The initial Linux PC installation should have been completed.  This could be any distribution or version of Linux - this guide is intended to be generic as well as having distribution/version specific code snippets.

The main points about the pc which should already have been set up are:

* Linux base operating system installed.
* BIOS clock set correctly and datetime set correct within a couple of minutes.

Basically, the developer should be able to login to the pc and to carry out tasks as the administrator.

# Tools and configuration

## Get Richt-click/Alt to resize windows

This is extremely useful and saves time when trying to resize windows.

NB - Alt-Leftclick anywhere in a Window to move it is generally set as the default.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

Open Applications -> System tools -> dconf Editor.

Under org.gnome.desktop.wm.preferences tick resize-with-right-button.

## Give terminal a dark background

It's much easier on the eyes to have a dark background on terminal sessions.  

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

Open terminal and go to Edit-profiles and edit the default profile - select a dark background.

## Install a developer editor

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install emacs emacs-goodies-el

## Install an IDE

An integrated development environment can provide a great deal of functionality to a developer.  This is how to install Netbeans 8.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    $ cd ~
    $ wget http://download.netbeans.org/netbeans/8.0/final/bundles/netbeans-8.0-php-linux.sh
    $ chmod 744 netbeans-8.0-php-linux.sh
    $ su -
    # apt-get install openjdk-7
    # exit
    $ ./netbeans-8.0-php-linux.sh
    
NB - installing openjdk-7 will make java 7 available for the installer.  Java will be at 1.6 and javac will be att 1.7.  It looks like Netbeans runs on its own version of java once it is installed.    


