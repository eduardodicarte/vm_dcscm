# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_FILE_VERSION = 2

Vagrant.configure(VAGRANT_FILE_VERSION) do |config|
   
  config.vm.box = "puppetlabs/centos-7.0-64-puppet"

  config.vm.define :dcscm do |dcscm|
  	dcscm.vm.hostname = "dcscm.dicarte.com.br"	
	dcscm.vm.network "private_network", ip: "192.168.210.200"
  end

  config.vm.provision "puppet" do |puppet|
	  puppet.environment_path = "environments"
	  puppet.environment = "development"
	  
	  puppet.facter = {
	      "ip" => "192.168.210.200",
	      "hostname" => "dcscm.dicarte.com.br",
	      "httpserver" => "apache",
	      "iptables_config_accept" => "1:INPUT:80,2:INPUT:8080",
	      #"""servidorscm" => "svn",
	      "repository_path" => "svn",
	      "svn_user" => "admin",
	      "svn_pass" => "$apr1$hX2raDqx$9vfQm/eq/cv3YEUwSn38p1",
	      "svn_repo_name" => "repo",
	      "servidorscm" => "git"
      }
  end
end
