SYNOPSIS
========

munin-freenet is a bunch of scripts that collect data about the freenet
daemon (fred) for munin.

USAGE
=====

Make sure the files can be read by the munin user (or whatever user munin is
running as), and that all its parent directories can by executed by the
same user.

You may want to edit the settings in the freenet_lib file, especially
the FCP port.

Once you get a result by running `sudo -u munin ./freenet_memory`, you
can symlink the plugins you want in the /etc/munin/plugins directory
(this may change according to your operating system).

The following plugins are availible :
	* freenet_bandwidth 
	* freenet_datastore_accesses
	* freenet_datastore_fill
	* freenet_memory
	* freenet_peers
	* freenet_ping
	* freenet_seeding
	* freenet_threads

DEPENDENCIES
============

Those scripts are written in PHP, so you will need to install it before
using anything. And, of course, you have to run the freenet daemon on your 
machine or you must be able to chat with it using FCP. This generally
means adding the IP of your computer to the allowed hosts list.

You also need GNU netcat to be in your $PATH.

Also, the scripts cache the FCP message for a few minutes (not to
overload the node). Make sure your /tmp is world-writeable (it should
be on most GNU/Linux distributions).
