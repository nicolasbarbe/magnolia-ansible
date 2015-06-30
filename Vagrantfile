Vagrant.configure(2) do |config|
  
  config.vm.box = "ubuntu/vivid64"
  config.vm.box_url = "ubuntu/vivid64"
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  {
    'instance1.local' => '192.168.33.10',
    'instance2.local' => '192.168.33.11',
    'instance3.local' => '192.168.33.12'
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.network 'private_network', ip: ip
    end
  end

end


