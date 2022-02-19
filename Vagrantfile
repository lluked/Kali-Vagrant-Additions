Vagrant.configure("2") do |config|
  # Download latest kalilinux/rolling box using url as box isn't listed correctly
  config.vm.box = "kali-linux/2022.1.0"
  config.vm.box_url = "https://app.vagrantup.com/kalilinux/boxes/rolling/versions/2022.1.0/providers/vmware_desktop.box"
  # Set vmware provider config
  config.vm.provider :vmware_desktop do |vmware|
    vmware.vmx["displayname"] = "Kali-Vagrant-Additions"
    vmware.vmx["numvcpus"] = "2"
    vmware.vmx["memsize"] = "4096"
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
