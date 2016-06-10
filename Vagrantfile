VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # box-config
  config.vm.box = "devops007"
  config.vm.box_url = "http://box.3wolt.de/devops007/"
  config.vm.box_check_update = true
  config.vm.box_version = "~> 1.1.0"

  # network-config
  config.vm.network "public_network", type: "dhcp"
  config.vm.boot_timeout = 600

  # SSH-config
  config.ssh.username = "root"
  config.ssh.insert_key = true

  # hostname
  config.vm.hostname = "RepoTemplate"

  # provisioners
  # ------------

  # nginx configs, copy and link
  config.vm.provision "file", source: "env/nginx.default.conf", destination: "/etc/nginx/sites-available/default", run: "always"
  config.vm.provision "file", source: "env/nginx.pma.conf", destination: "/etc/nginx/sites-available/pma", run: "always"

  # shell commands
  config.vm.provision "shell", path: "env/bootstrap.sh", run: "always"

end
