# COMPSCI 377 Programming Environment

$script = <<-SCRIPT
echo I am provishioning...
apt-get update -y
apt-get upgrade -y
apt-get install -y python3-pip
apt-get install -y emacs vim git gdb splint valgrind astyle doxygen
apt-get install -y wget curl build-essential emacs vim git libgtest-dev zip
apt-get install -y cmake clang-format
cd /usr/src/gtest
cmake CMakeLists.txt
make
cp *.a /usr/lib
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", inline: $script
  config.vm.network "forwarded_port", guest: 8000, host: 8000
end
