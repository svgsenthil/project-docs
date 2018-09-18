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

## Re-Generate and Deploy your Business Network

After changing the files in a business network, open the package.json file in the tutorial-network directory and
update the version from 0.0.1 to 0.0.2.

```
cd ~/tutorial-network/
composer archive create --sourceType dir --sourceName . -a tutorial-network@0.0.2.bna
```

Switch to the terminal, change directory to the folder containing the tutorial-network@0.0.2.bna.

```
cd ~/tutorial-network/
composer network install --card PeerAdmin@hlfv1 --archiveFile tutorial-network@0.0.2.bna
composer network upgrade -c PeerAdmin@hlfv1 -n tutorial-network -V 0.0.2
composer network ping -c admin@tutorial-network | grep Business
composer-rest-server
```
Refer [Hyperledger Tutorial Pages](https://hyperledger.github.io/composer/latest/tutorials/queries).

