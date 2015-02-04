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

## Get Right-click/Alt to resize windows

This is extremely useful and saves time when trying to resize windows.

NB - Alt-Leftclick anywhere in a Window to move it is generally set as the default.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

Open Applications -> System tools -> dconf Editor.

Under org.gnome.desktop.wm.preferences tick resize-with-right-button.

| Distribution | Versions |
| --- | --- |
| Ubuntu | 12.04 |

Install dconf-editor.

Open Applications -> System tools -> dconf Editor.

Under org.gnome.desktop.wm.preferences tick resize-with-right-button.

## Get live window resizing

This resizes the contents of a window as the window is being resized.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

Default behaviour.

| Distribution | Versions |
| --- | --- |
| Ubuntu | 12.04 |

Install compizconfig-settings-manager.

Find the Resize Window plugin; it's under Window Management. Open it and go to the General tab. The top setting is Default Resize Mode.

Normal resizes the windows content on-the-fly.

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

    # apt-get install emacs emacs-goodies-el php-elisp
 
## Install an IDE

An integrated development environment can provide a great deal of functionality to a developer.  This is how to install Netbeans 8.

After installing Netbeans Drupal specific code formatting can be implemented by: https://www.drupal.org/node/1019816

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    $ cd ~
    $ wget http://download.netbeans.org/netbeans/8.0.2/final/bundles/netbeans-8.0.2-php-linux.sh
    $ chmod 744 netbeans-8.0.2-php-linux.sh
    $ su -
    # apt-get install openjdk-7
    # exit
    $ ./netbeans-8.0.2-php-linux.sh
    
NB - installing openjdk-7 will make java 7 available for the installer.  Java will be at 1.6 and javac will be att 1.7.  It looks like Netbeans runs on its own version of java once it is installed.

Use

    # update-java-alternatives -l
    
to see the java runtimes available.

And use:

    # java -version
    # javac -version
    
to see which are the current default versions.

And use:

    # update-java-alternatives -s java-1.7.0-openjdk-amd64
    
to get all java runtimes to use java 1.7.    

| Distribution | Versions |
| --- | --- |
| Ubuntu | 12.04 |

NB - Before installing Netbeans it may be best to install icetea to prevent an error when running the line update-java-alternatives.

    # apt-get install icedtea-7-plugin

Then install Netbens with:

    $ cd ~
    $ wget http://download.netbeans.org/netbeans/8.0/final/bundles/netbeans-8.0.2-php-linux.sh
    $ chmod 744 netbeans-8.0.2-php-linux.sh
    $ sudo su -
    # apt-get install openjdk-7-jdk
    # update-java-alternatives -s java-1.7.0-openjdk-amd64
    # exit
    $ ./netbeans-8.0.2-php-linux.sh
    
NB - installing openjdk-7 will make java 7 available for the installer.  Java will be at 1.6 and javac will be att 1.7.  It looks like Netbeans runs on its own version of java once it is installed.

Use

    # update-java-alternatives -l
    
to see the java runtimes available.

And use:

    # java -version
    # javac -version
    
to see which are the current default versions.

And use:

    # update-java-alternatives -s java-1.7.0-openjdk-amd64
    
to get all java runtimes to use java 1.7.    

## Install an IRC client

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install xchat

## Geting a java applet to run in a browser

This may be useful to access remote consoles etc.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install icedtea-7-plugin
    
Then restart the browser.

## Add some tools to generate passwords

Always useful to quickly generate decent passwords.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install gpw pwgen

## Graphical diffing tool

Always useful - the ability to visually see the differences between files and code shippets.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install meld
    
## Graphical hexeditor

Always useful - the ability to open files in a simple hex editor.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install hexedit ghex
    
## Graphical git viewer

It's very helpful to be able to see a visualisation of local git trees.  Gitg is a nice simple git repository viewer - but others are available.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install gitg
        
## Midnight commander

Useful file management tool.

| Distribution | Versions |
| --- | --- |
| Debian | 7 |

    # apt-get install mc

| Distribution | Versions |
| --- | --- |
| Ubuntu | 12.04 |

    # apt-get install mc

It is useful to turn off the keyboard shortcuts.  However, on Ubuntu 12.04 pressing F10 will bring up the context (right-click) menu.  To turn this off create a new file: ~/.config/gtk-3.0/gtk.css and add the following

    @binding-set NoKeyboardNavigation {
     unbind "<shift>F10"
    }

    * {
     gtk-key-bindings: NoKeyboardNavigation
    }

NB - Maybe on newer versions of Ubuntu - or just on Lubuntu - there is a setting under the 'Avanced' tab of the terminal settings which works well.
