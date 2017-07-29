VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "DreiWolt/devops007"
  config.vm.network :private_network, ip: "ProjectIP"
  config.vm.hostname = "ProjectName"
  config.hostsupdater.aliases = ["dev.ProjectDomain.de", "pma.ProjectDomain.de", "readis.ProjectDomain.de"]
  config.vm.synced_folder ".", "/vagrant", type: "nfs"
  config.vm.provision "shell", path: "env/bootstrap.sh", run: "always"

end
