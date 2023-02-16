# s390x-blockchain
Exploration into the application of running blockchain nodes on IBM s390x Z Mainframe architecture

## Resources 

### s390x and Blockchain
* [s390 Wiki](https://en.wikipedia.org/wiki/IBM_System/390)
* [s390x Ubuntu](https://wiki.ubuntu.com/S390X)
* [s390 Linux Kernel](https://docs.kernel.org/s390/index.html)

### Need to Read
* https://developer.ibm.com/tutorials/build-teku-and-web3signer-on-s390x-architecture/
* https://github.com/ethereum/go-ethereum/blob/master/common/bitutil/bitutil.go
* https://pkgs.alpinelinux.org/package/edge/community/s390x/geth
* http://rpmfind.net/linux/RPM/epel/8/s390x/Packages/b/bitcoin-core-desktop-23.0-1.el8.s390x.html
* https://docs.anaconda.com/anaconda/packages/py3.9_linux-s390x/
* https://www.coindesk.com/learn/ethereum-nodes-and-clients-a-complete-guide/ - try java and rust based options

### IBM Mainframes and Blockchain 
* [Blockchain for IBM Z](https://community.ibm.com/community/user/ibmz-and-linuxone/blogs/destination-z1/2019/12/23/blockchain-for-ibm-z)
* [Blockchain And The IBM zMainframe](https://planetmainframe.com/2021/08/blockchain-and-the-ibm-zmainframe-a-match-made-in-heaven/)
* [IBM Crypto Custody](https://www.coindesk.com/business/2022/02/18/inside-ibms-fast-growing-crypto-custody-play/)

### Ethereum Installation
* [Geth Client](https://geth.ethereum.org/docs)
* [Ethereum Node Video](https://www.youtube.com/watch?v=3H-KmO7Ce4I&ab_channel=EatTheBlocks)
* [Serum Ethereum Node Setup](https://stereum.net/ethereum-node-setup/)
* [Geth Guide](https://www.quicknode.com/guides/infrastructure/how-to-install-and-run-a-geth-node)
* [Polygon Docker](https://wiki.polygon.technology/docs/develop/network-details/full-node-docker)
* [Ethereum Node](https://ethereum.org/en/developers/docs/nodes-and-clients/run-a-node/)

## Compatible Dependencies for s390X

* Makefile - ```sudo apt install make```
* Git - ```sudo apt install git```
* Rust - ```curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh```
* Golang - ```sudo apt install golang-go```
* Snapd - ```sudo apt install snapd```
* Nodejs - ```sudo snap install node```
* NVM - ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash```
* NPM - ```sudo snap install npm```
* Python - ```sudo apt install python```
* Pip - ```sudo apt install python-pip```
* Pip3 - ```sudo apt install python-pip3```
* s390 Tools - ```s390-tools```
* Ansible - ```sudo apt install ansible``` - needed for polygon
* Build Tools - ```sudo apt-get install build-essential```
* Java - ```sudo apt install default-jre```

## Ethereum Installation

### Geth Dependencies
0. ssh into the server
```
ssh<user>@<ip-address>
```
1. Update your package library - 
```
sudo apt update && sudo apt upgrade
```
2. Install Makefile - 
```
sudo apt install make
```
3a. Add Ethereum repository to Apt
```
sudo add-apt-repository -y ppa:ethereum/ethereum
```
3b. Update package lists to reflect Ethereum repository
```
sudo apt-get update
```
### Geth Installation Guide - Ubuntu x86 - test on ARM? 
1. Install Geth Package
```
sudo apt-get install ethereum
```
2. Check to ensure installation was successful
```
geth version
```

```Output should be similar to the following: 
Geth
Version 1.11.1-stable
Git Commit <git commit here>
Architecture: amd64
Go Version: go1.20.1
Operating System: linux
GOPATH=
GOROOT=
```




#### Teku Deps
Java 
### Teku Installation Guide
1. 
```
$ git clone https://github.com/Consensys/teku.git
```
```
cd teku
```
```
$ ./gradlew distTar installDist
```

## Polygon

### Polygon Dependancies 
* make
* go
* ansible?

```
sudo apt-get update
sudo apt-get install build-essential
sudo apt install golang-go
```

### Polygon Installation
* https://wiki.polygon.technology/docs/develop/network-details/full-node-binaries
* https://wiki.polygon.technology/docs/develop/network-details/full-node/ - does not work
#### Heimdall
```
cd
```
```
git clone https://github.com/maticnetwork/heimdall
```
```
cd heimdall
```
```
make install
```
```
source ~/.profile
```
```
heimdalld version --long
```
#### Bor
```
cd
```
```
git clone https://github.com/maticnetwork/bor
```
```
cd bor
```
```
make bor
```
```
sudo ln -nfs ~/bor/build/bin/bor /usr/bin/bor
```
```
sudo ln -nfs ~/bor/build/bin/bor /usr/bin/bor
```
```
bor version
```

#### Configure
```
git clone https://github.com/maticnetwork/launch
```
```
cd
```
```
mkdir -p node
```
```
cp -rf launch/mainnet-v1/sentry/sentry/* ~/node
```
Errors past this point



