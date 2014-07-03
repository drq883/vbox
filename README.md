vbox (Mac only)
==========

What is syncmyhome?

vbox is a perl script that is a VirtualBox command-line interactive
interface. I'm a long-time developer and do most everything from an xterm
(iTerm2 on the mac). No IDE's for me. And so I wanted to create a simple
command-line interactive interface for VirtualBox.


How to install it?

I just copy the vbox script to my ~/bin directory and that's it. I don't
have a Makefile to do that for you since the commands are just:

   mkdir -p ~/bin
   cp vbox ~/bin

And only the 2nd is probably necessary as most users have a ~/bin directory.


Requirements:

*VirtualBox (I have 4.3.6 installed)
*vbox (this script)


Host to use it?

Just run:
  vbox

The only supported option is -v (for verbose) which will show UUIDs for VMs
and Snapshots.

TODO: more to come
