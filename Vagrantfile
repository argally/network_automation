# -*- mode: ruby -*-
# vi: set ft=ruby :

# Check required plugins
REQUIRED_PLUGINS = %w(vagrant-junos vagrant-host-shell)
exit unless REQUIRED_PLUGINS.all? do |plugin|
  Vagrant.has_plugin?(plugin) || (
    puts "The #{plugin} plugin is required. Please install it with:"
    puts "$ vagrant plugin install #{plugin}"
    false
  )
end

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.


	config.vm.define "p1" do |p1|
	p1.ssh.insert_key = false
	p1.vm.network "private_network", virtualbox__intnet: "net1"
	p1.vm.network "private_network", virtualbox__intnet: "net2"
	p1.vm.network "private_network", virtualbox__intnet: "net3"
    p1.vm.network "private_network", virtualbox__intnet: "net7"
	p1.vm.box = "juniper/ffp-12.1X47-D15.4-packetmode"
	p1.vm.provider :virtualbox  do |vb|
		vb.name = "router_p1"
		vb.memory = 1024
		end
	end

    config.vm.define "p2" do |p2|
    p2.ssh.insert_key = false
    p2.vm.network "private_network", virtualbox__intnet: "net1"
    p2.vm.network "private_network", virtualbox__intnet: "net4"
    p2.vm.network "private_network", virtualbox__intnet: "net5"
    p2.vm.network "private_network", virtualbox__intnet: "net7"
    p2.vm.box = "juniper/ffp-12.1X47-D15.4-packetmode"
    p2.vm.provider :virtualbox  do |vb|
        vb.name = "router_p2"
        vb.memory = 1024
        end
    end

    config.vm.define "pe1" do |pe1|
    pe1.vm.network "private_network", virtualbox__intnet: "net2"
    pe1.vm.network "private_network", virtualbox__intnet: "net4"
    pe1.vm.network "private_network", virtualbox__intnet: "net5"
    pe1.vm.network "private_network", virtualbox__intnet: "net7"
    pe1.vm.box = "juniper/ffp-12.1X47-D15.4-packetmode"
    pe1.vm.provider :virtualbox  do |vb|
        vb.name = "router_pe1"
        vb.memory = 1024
        end
    end

    config.vm.define "pe2" do |pe2|
    pe2.vm.network "private_network", virtualbox__intnet: "net3"
    pe2.vm.network "private_network", virtualbox__intnet: "net5"
    pe2.vm.network "private_network", virtualbox__intnet: "net6"
    pe2.vm.network "private_network", virtualbox__intnet: "net7"
    pe2.vm.box = "juniper/ffp-12.1X47-D15.4-packetmode"
    pe2.vm.provider :virtualbox  do |vb|
        vb.name = "router_pe2"
        vb.memory = 1024
        end
    end
end


