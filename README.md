#vbox

##What is vbox?

vbox is a perl script that is a VirtualBox command-line interactive
interface. I'm a long-time developer and do most everything from an xterm
(iTerm2 on the mac). No IDE's for me. And so I wanted to create a simple
command-line interactive interface for VirtualBox.


##How to install it?

I just copy the vbox script to my ~/bin directory and that's it. I don't
have a Makefile to do that for you since the commands are just:

 + mkdir -p ~/bin
 + cp vbox ~/bin
 
 I actually did this:

 + ln -s ~/git/vbox/vbox ~/bin

Which allows it to follow the updates without having to re-copy. I just "git pull" from the repo and I'm done.


##Requirements:

 + VirtualBox (I have 4.3.6 installed)
 + vbox (this script)


##Host to use it?

Just run:
```
vbox
```

The only supported option is -v (for verbose) which will show UUIDs for VMs
and Snapshots.

And example run shows this:

```
% vbox

===============================================================================
 1 - bsd10

 * - running

action [List, STArt <n>, STOp <n>, Headless <n>, Poweroff <n>,
        Revert <n>, SNapshot <n>, DESTROY <n>]:
(or 'q' to quit):
```
The actions available on this screen are:

 + List          - this command just lists the VMs again
 + STArt <n>     - start the specified VM
 + STOp <n>      - stop the specified VM by sending the ACPI signal
 + Headless <n>  - start the specified VM headless
 + Poweroff <n>  - power off the specified VM
 + Revert <n>    - revert the specified to the last saved snapshot (will reboot if running)
 + SNapahost <n> - change to the snapshot display for specified VM
 + DESTROY <n>   - destory specified VM and removed any directory still there
 + quit          - quit vbox

The snapshot screen looks like this:

```
(or 'q' to quit): cd 1

 1  No OS
 2    10-BETA3 installed
 3      svn head updated
 4        ports tree added
 5          Successfully build image for Pi
 6            buildkernel buildworld *

action [STArt, STOp, RESTArt, List, REVert, DELete <n>, RESTOre <n>, Take <name>]
(or 'q' to return, 'Q' to exit):
```
The actions available on this screen are:

 + STArt       - start the current VM
 + STOp        - stop the current VM by sending the ACPI signal
 + RESTart     - restart the current VM (poweroff and start)
 + List        - this command just lists the snapshots again
 + Revert      - revert the current VM to the last saved snapshot (will reboot if running)
 + DELete <n>  - delete the specified snapshot
 + RESTOre <n> - restore the specified snapshot (host must be down)
 + Take <name> - take a snapshot of the current VM and name it <name>
 + quit        - return to the VM display
 + Quit        - quit vbox altogether


##Notes:
+ actions miminum abbreviations are shown in uppercased letters
+ actions for a VM can be given on the command line for quicker action for example:
```
vbox start mytestvm
```

