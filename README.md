# vbox

## What is vbox?

vbox is a perl script that is a VirtualBox command-line interactive
interface. I'm a long-time developer and do most everything from an xterm
(iTerm2 on the mac). No IDE's for me. And so I wanted to create a simple
command-line interactive interface for VirtualBox.


## How to install it?

I just copy the vbox script to my ~/bin directory and that's it. I don't
have a Makefile to do that for you since the commands are just:

 * mkdir -p ~/bin
 * cp vbox ~/bin


 Or just do this:


 * ln -s ~/github/vbox/vbox ~/bin

Which allows it to follow the updates without having to re-copy. I just "git
pull" from the repo and I'm updated to the latest.


## Requirements:

 * VirtualBox (tested thru 5.0.26)
 * vbox (this script)


## Host to use it?

Just run:
```
vbox
```

The only supported option is -v (for verbose) which will show UUIDs for VMs
and Snapshots in additions to the names.

And example run shows this:

```
% vbox
Using VBoxManage version: 5.0.26r108824

===============================================================================
 1 - win7
 2 - server1
 3 - client
 4 - docker

 * - running

action [HELP,   DESTROY, Headless, Info,  PAuse, POweroff, RESTArt,
        RESUme, REVert,  SNapshot, STArt, STOp,  Take]:
(or 'q' to quit):
```
The actions available on this screen are:
* CD <n>             - Change into VM's snapshot screen
* HELP|?             - Show this display
* DESTROY <n>        - Destroy the given VM(s) and storage
* Headless <n[,n]>   - Start the VM(s) in headless mode
* Info <n[,n]>       - Show all VM(s) info
* PAuse <n[,n]>      - Pause the VM(s)
* POweroff <n[,n]>   - Poweroff the given VM(s)
* RESTArt <n[,n]>    - Poweroff and start the given VM(s)
* RESUme <n[,n]>     - Resume the given VM(s)
* REVert <n[,n]>     - Poweroff, restore active snapshot, Start
* SNapshot|cd <n>    - Change to the snapshot menu for given VM
* STArt <n[,n]>      - Power on the given VM(s)
* STOp <n[,n]>       - Send ACPI signal to given VM(s)
* Take <n[,n]> <str> - Take a snapshot, use <str> to describe it


The snapshot screen looks like this:

```
(or 'q' to quit): cd 4
VM: docker

 1  InitialSnapshot
 2    installed docker based on STAGING.notes
 3      install perl mods for plugins
 4        ready for testing *

 * - active snapshot

action [HELP,    Del,    Headless, Info,  PAuse, POweroff, RESTArt,
        RESTOre, RESUme, REVert,   STArt, STOp,  Take]
```

The actions available on this screen are:

* HELP|?      - Show this display
* Delete <n>  - Delete the given snapshot
* Headless    - Start the VM in headless mode
* Info        - Show all VM info
* PAuse       - Pause the VM
* POweroff    - Poweroff the given VM
* RESTArt     - Poweroff and start the VM
* RESTore <n> - Restore the given snapshot
* RESUme      - Resume the VM
* REVert      - Poweroff, restore active snapshot, Start
* STArt       - Power on the VM
* STOp        - Send ACPI signal to VM
* Take <str>  - Take a snapshot, use <str> to describe it

## Notes:
* actions minimum abbreviations are shown in uppercased letters
* actions for a VM can be given on the command line for quicker action for example:
```
vbox start docker
```
