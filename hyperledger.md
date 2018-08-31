#Commands for install Hyperledger Fabric

sudo apt-get install curl
sudo apt-get install golang-go
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt-get install python
sudo apt-get install docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
apt-cache policy docker-ce
sudo apt-get install -y docker-ce
sudo apt-get install docker-compose
sudo apt-get upgrade
--------------------

curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
--------------------

sudo add-apt-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git -y
--------------------

curl -O https://hyperledger.github.io/composer/latest/prereqs-ubuntu.sh
chmod u+x prereqs-ubuntu.sh
--------------------

Installation completed, versions installed are:

Node:           v8.11.4
npm:            6.4.0
Docker:         Docker version 18.06.0-ce, build 0ffa825
Docker Compose: docker-compose version 1.13.0, build 1719ceb
Python:         Python 2.7.12

Please logout then login before continuing.
---------------------

