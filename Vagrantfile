Vagrant.configure("2") do |config|
  # Download latest kalilinux/rolling box using url as box isn't listed correctly
  config.vm.box = "kali-linux/2022.1.0"
  config.vm.box_url = "https://app.vagrantup.com/kalilinux/boxes/rolling/versions/2022.1.0/providers/vmware_desktop.box"
  # Set vmware provider config
  config.vm.provider :vmware_desktop do |vm|
    vm.vmx["displayname"] = "Kali-Vagrant-Additions"
    vm.vmx["numvcpus"] = "2"
    vm.vmx["memsize"] = "4096"
    ## Pick one of the below networking scenarios ##
    # Disable NAT and enable Bridged Networking Autodetect
    vm.vmx['ethernet0.connectiontype'] = nil
    vm.vmx['ethernet0.linkStatePropagation.enable'] = "TRUE"
    # # Enable NAT and disable Bridged Networking Autodetect
    # vm.vmx['ethernet0.connectiontype'] = "nat"
    # vm.vmx['ethernet0.linkStatePropagation.enable'] = nil
  end
  # Provision ansible playbooks
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "ansible/site.yml"
  end
  # Reboot host after ansible provisioning has completed
  config.vm.provision :shell do |shell|
    shell.name = "Reboot after provisioning"
    shell.reboot = true
  end
end
