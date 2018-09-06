# Hyperledger Tutorial Network Project Commands

## First time Configuration Setup Commands

### Install Hyperledger Fabric Development Server
```
mkdir ~/fabric-dev-servers && cd ~/fabric-dev-servers
curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz
tar -xvf fabric-dev-servers.tar.gz
cd ~/fabric-dev-servers
export FABRIC_VERSION=hlfv12
./downloadFabric.sh
./startFabric.sh
./createPeerAdminCard.sh
composer-playground
```
Refer [Hyperledger Tutorial Pages](https://hyperledger.github.io/composer/latest/installing/development-tools.html).

### Deploying the Business Network & Generating Rest Server
```
cd ~/tutorial-network/
composer archive create -t dir -n .
composer network install --card PeerAdmin@hlfv1 --archiveFile tutorial-network@0.0.1.bna
composer network start --networkName tutorial-network --networkVersion 0.0.1 --networkAdmin admin --networkAdminEnrollSecret adminpw --card PeerAdmin@hlfv1 --file networkadmin.card
composer card import --file networkadmin.card
composer network ping --card admin@tutorial-network
composer-rest-server
```
Refer [Hyperledger Tutorial Pages](https://hyperledger.github.io/composer/latest/tutorials/developer-tutorial.html).

### Start Project
```
cd ~/tutorial-network/tutorial-network/
npm start
```

## Re-Run After Project Setup

### Start Fabric dev Server
```
cd ~/fabric-dev-servers/fabric-scripts/hlfv12/composer/
$ docker-compose stop
$ docker-compose start
```

### Start Rest Server
```
cd ~/tutorial-network/
composer network ping --card admin@tutorial-network
composer-rest-server -c admin@tutorial-network -n never -w true
```

### Start Project
```
cd ~/tutorial-network/tutorial-network/
npm start
```

