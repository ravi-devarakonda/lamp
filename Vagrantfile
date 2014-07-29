Vagrant::Config.run do |config|
  config.vm.box       = "centos-6.3-x86_64"
  config.vm.box_url   = "https://saleseng.s3.amazonaws.com/boxfiles/CentOS-6.3-x86_64-minimal.box"
  config.vm.host_name = "development.puppetlabs.vm"
  config.vm.network :hostonly, "192.168.33.10"
  config.vm.forward_port 80, 8084
  config.vm.provision :shell, :path => "centos_6_x.sh"

  # Puppet Shared Folder
  config.vm.share_folder "puppet_mount", "/puppet", "puppet"

  # Puppet Provisioner setup
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path    = "puppet/modules"
    puppet.manifest_file  = "site.pp"
  end
end
