Tutorial for the DECK36 Plan9 Workshop
======================================
[1]: https://www.virtualbox.org/wiki/Downloads "Virtual Box"
[2]: http://www.vagrantup.com/downloads.html "Vagrant"
[3]: https://github.com/DECK36/plan9_workshop_tutorial/archive/master.zip "Workshop Repo"
[4]: http://www.jetbrains.com/idea/download "IntelliJ Download"
[logo]: ./deck36.png "Deck36 Logo"
[PHPTUTORIAL]: ./README_php.md "PHP Tutorial"
[NODETUTORIAL]: ./README_nodejs.md "Node.js Tutorial"

![Deck36 Logo][logo]

[DECK36](http://www.deck36.de) offers the workshop in two varieties: one where Storm components are implemented in `PHP` and a second one using `node.js`.


## Install Vagrant Image

Both workshops are based on the same Vagrant image. 

Please install the Vagrant image before the workshop:

1. Install [Virtualbox][1]
2. Install [Vagrant][2]
3. Restart Host (Windows only)
4. Download the zipped [repository][3] to your $HOME or just C:\ or ~
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

    You will need to enter your user password to mount the sources folder into the guest system!
8. Enter the VM

    ```
    vagrant ssh
    ```

9. Edit the rabbit-mq config file
    
    ```
    sudo vi /etc/rabbitmq/rabbitmq.config
    ```

    Empty the file and paste

    ```
    [ 
        {rabbit, [ 
            {default_user, <<"guest">>}, 
            {default_pass, <<"guest">>}, 
            {loopback_users, []} 
        ]} 
    ].
    ```
    
    Save the file.
10. Restart the rabbit-mq service
    
    ```
    sudo /etc/init.d/rabbitmq-server restart
    ```

### Install IDE (IntelliJ)
1. Download [IntelliJ Community Edition][4]
2. Install the IDE

### Install git
Just install a git client of your choice, suitable for your system.



## Choose Tutorial

To continue, please choose the tutorial you are interested in :

[PHP Tutorial][PHPTUTORIAL]
[Node.js Tutorial][NODETUTORIAL]

