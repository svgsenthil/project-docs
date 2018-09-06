# Hyperchain Labs Truck Network Project Commands

## First time Configuration Setup Commands

### Start Fabric dev Server
```
cd ~/fabric-dev-servers/
export FABRIC_VERSION=hlfv12
./startFabric.sh
./createPeerAdminCard.sh
composer-playground
```
Refer [Hyperledger Tutorial Pages](https://hyperledger.github.io/composer/latest/installing/development-tools.html).

### Deploying the Business Network & Generating Rest Server
```
cd ~/truck-network/dist/
composer archive create -t dir -n .
composer network install --card PeerAdmin@hlfv1 --archiveFile hyperchainlabs-truck-network@0.1.2.bna
composer network start --networkName hyperchainlabs-truck-network --networkVersion 0.1.2 --networkAdmin admin --networkAdminEnrollSecret adminpw --card PeerAdmin@hlfv1 --file networkadmin.card
composer card import --file networkadmin.card
composer network ping --card admin@hyperchainlabs-truck-network
composer-rest-server
```
Refer [Hyperledger Tutorial Pages](https://hyperledger.github.io/composer/latest/tutorials/developer-tutorial.html).

### Start Project
```
cd ~/truck-network/dist/hyperchainlabs-truck-network/
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
cd ~/truck-network/dist/
composer network ping --card admin@hyperchainlabs-truck-network
composer-rest-server -c admin@hyperchainlabs-truck-network -n never -w true
```

### Start Project
```
cd ~/truck-network/dist/hyperchainlabs-truck-network/
npm start
```

