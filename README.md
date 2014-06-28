Tutorial for the DECK36 Plan9 Workshop
======================================
[1]: https://www.virtualbox.org/wiki/Downloads "Virtual Box"
[2]: http://www.vagrantup.com/downloads.html "Vagrant"
[3]: https://github.com/DECK36/plan9_workshop_tutorial/archive/master.zip "Workshop Repo"
[4]: https://github.com/DECK36/deck36-php-web-app "Plan9 Web Application"
[5]: https://github.com/DECK36/deck36-api-backend "Plan9 NodeJS API Backend"
[6]: https://github.com/DECK36/deck36-storm-backend-nodejs "Plan9 Storm Backend with NodeJS"

## Introduction
This tutorial is dedicated to the workshops held by DECK36. 
It can be used to setup a local developmentenvironment to follow the workshop.

## Installation
The workshop assumes the p9fok VM to be up and running and the sources mounted in the VM.

### Dev-Environment
1. Install [Virtualbox][1]
2. Install [Vagrant][2]
3. Restart Host (Windows only)
4. Downlod the zipped [repository][3] to your $HOME or just C:\ or ~
5. Unzip
```
cd ~; unzip plan9_workshop_tutorial-master.zip
```
6. Enter the plan9_workshop_tutorial-master directory
```
cd plan9_workshop_tutorial-master
```
7. Start the VM
```
vagrant up
```
! You will need to enter your user password to mount the sources folder into the guest system !

*********
This part is under construction. You will not be able to use it currently.
*********
### Install IDE (IntelliJ)
1. Downdload IntelliJ

### Install git
1. Just install a git client of your choice

### Sources 
1. Enter the plan9_workshop_tutorial-master/source/plan9 directory
```
cd ~/unzip plan9_workshop_tutorial-master/source/plan9
```
2. Clone the [web application][4]
```
git clone
```
3. Clone the [nodejs api backend][5]
4. Clone the [storm backend][6]

### Package Storm Topology

## Start all components

## Play Plan9 From Outer Space

## Add your own Badge!
