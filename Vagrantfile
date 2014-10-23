Vagrant.require_version ">= 1.5.0"

Vagrant.configure("2") do |config|
    #config.ssh.private_key_path = "./vagrant"
    config.ssh.forward_agent = true

    config.vm.define :p9fok do |machine|
        # Box settings
        machine.vm.box_url = "deck36/plan9"
        machine.vm.box = "deck36/plan9"

        # Guest settings
        machine.vm.hostname = "plan9.local"

        # Network settings
        config.vm.network :private_network, ip: "192.168.42.2"
        config.vm.network :forwarded_port, host:  8000, guest:    80
        config.vm.network :forwarded_port, host:  8080, guest:  8080
        config.vm.network :forwarded_port, host:  5672, guest:  5672
        config.vm.network :forwarded_port, host: 15672, guest: 15672

        # VirtualBox Specific Customization
        config.vm.provider :virtualbox do |vb|
              vb.customize ["modifyvm", :id, "--memory", "2048"]
              vb.customize ["modifyvm", :id, "--cpus", "2"]
              vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]

              # Peformance tweaks that should help with hardware clock problems
              vb.customize ["modifyvm", :id, "--hpet", "on"]
              vb.customize ["modifyvm", :id, "--ioapic", "on"]
              vb.customize ["guestproperty", "set", :id, "--timesync-set-on-restore", "1"]

              # ensure acpi is enabled in the machine
              vb.customize ["modifyvm", :id, "--acpi", "on"]

              # Virtualization performance tweaks: force use of hardware virtualization features of i5 and i7 processors
              vb.customize ["modifyvm", :id, "--hwvirtex", "on"]
              vb.customize ["modifyvm", :id, "--nestedpaging", "on"]
              vb.customize ["modifyvm", :id, "--vtxvpid", "on"]
              vb.customize ["modifyvm", :id, "--largepages", "on"]

              vb.gui = true
        end

        if Vagrant::Util::Platform.windows?
              config.vm.synced_folder "./source/plan9", "/home/vagrant/plan9", type: "smb"
              config.vm.synced_folder "./source/m2", "/home/vagrant/.m2", type: "smb"
        else
              machine.vm.synced_folder "./source/plan9", "/home/vagrant/plan9", { :nfs => true, nfs_version: 3 }
              machine.vm.synced_folder "./source/m2", "/home/vagrant/.m2", { :nfs => true, nfs_version: 3 }
        end
    end

    # Branding
    config.vm.provision :shell, :inline => <<-PREPARE
      /bin/cat /vagrant/source/ascii-logo.txt
    PREPARE
end
