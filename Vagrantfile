VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.vm.define "django" do |django|
      django.vm.box = "ubuntu/trusty64"
	  django.vm.network :private_network, ip: "192.168.33.10"

	  django.vm.provision :ansible do |ansible|
	    ansible.playbook = "django.yml"
	    ansible.groups = {
  		  "django" => ["machine1"]
  		}
	    ansible.limit = "all"
	    ansible.verbose = "vvvv"
	    ansible.raw_arguments = ['--timeout=30']
	  end 
	end
  
end	