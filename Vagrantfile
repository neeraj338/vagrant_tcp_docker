Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/focal64'
  config.vm.hostname = 'docker.local'
  config.vm.network 'private_network', ip: '192.168.66.4'
  config.vm.network 'forwarded_port', guest: 2375, host: 2375, id: 'dockerd', auto_correct: true
  config.vm.provider 'virtualbox' do |vb|
    vb.name = 'ubuntu-docker'
    vb.memory = '2048'
    vb.cpus = '2'
  end
  config.vm.provision 'shell', path: 'provision.sh'
  
  # Configuration for Port Forwarding
  # Uncomment or add new ones here as required
  config.vm.network 'forwarded_port', guest: 6379, host: 6379, id: 'redis'
  config.vm.network 'forwarded_port', guest: 8001, host: 8002, id: 'redisinsight'
  config.vm.network 'forwarded_port', guest: 8000, host: 8000, id: 'temp'
  config.vm.network 'forwarded_port', guest: 9000, host: 9000, id: 'temp2'
  config.vm.network 'forwarded_port', guest: 8681, host: 8681, id: 'pubSub-emulator'
end
