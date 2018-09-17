required_plugins = ["vagrant-hostsupdater"]

required_plugins.each do |plugin|
  exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin # 
end

Vagrant.configure("2") do |config| # Vagrant method configure that runs version 2 of vagrant
system "vagrant install vagrant-hostsupdater"
config.vm.box = "ubuntu/xenial64"
config.vm.network("private_network", ip: "192.168.10.100")
config.hostsupdater.aliases = ["development.local"] # goes into the Hosts file and looks at the specified aliase and assigns it the ip address specified above

end
