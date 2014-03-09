# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "serverci.okochang.com" do |host|
    host.vm.box = "centos"
    host.vm.provider :aws do |aws, override|
      aws.access_key_id = ENV['AWS_ACCESS_KEY']
      aws.secret_access_key = ENV['AWS_SECRET_KEY']
      aws.region = "ap-northeast-1"
      aws.keypair_name = "okochang-key"
      aws.subnet_id = "subnet-f9076490"
      aws.private_ip_address = "10.0.2.100"
      aws.elastic_ip = true
      aws.security_groups = ["sg-b72d31db"]
      aws.ami = "ami-b5c0b1b4"
      override.ssh.username = "root"
      override.ssh.private_key_path = "~/.ssh/okochang-key.pem"
    end
  end
end

