$script = <<-SCRIPT
echo I am provishioning...
apt-get update -y
apt-get upgrade -y
apt-get install -y python3-pip
apt-get install -y emacs vim git gdb splint valgrind astyle doxygen
apt-get install -y wget curl build-essential emacs vim git libgtest-dev zip
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.box_version = "201803.24.0"
  config.vm.provision "shell", inline: $script
  config.vm.network "forwarded_port", guest: 8000, host: 8000
end
