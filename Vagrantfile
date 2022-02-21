Vagrant.configure("2") do |config|
  # Set box to latest kalilinux/rolling
  config.vm.box = "kalilinux/rolling"
  # Set vmware provider config
  config.vm.provider :vmware_desktop do |vmware|
    vmware.vmx["displayname"] = "Kali-Vagrant-Additions"
    vmware.vmx["numvcpus"] = "2"
    vmware.vmx["memsize"] = "4096"
  end
  # Provision ansible playbooks
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "ansible/main.yml"
  end
  # Reboot host after ansible provisioning has completed
  config.vm.provision :shell do |shell|
    shell.name = "Reboot after provisioning"
    shell.reboot = true
  end
end
