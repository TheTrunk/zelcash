# Zelcash 1.1.0
INNOVATIVE  INTELLIGENT  INSPIRING

Zelcash is a fork of 1.0.14 Zcash aiming to provide decentralised development platform via ZelNodes and ZelTreZ.

POW asic resistant with Equihash (144,5) also known as Zhash with personalisation string ZelProof. 

To speed up synchronisation you can also download our blockchain (state Fri 6. 7. 2018) at https://drive.google.com/file/d/1Vn8HWau24wjTtUc9QZU2stliKevaEFx1/view?usp=sharing (pw: zelcash).

## Build (Ubuntu 16.04 Tested)
```
sudo apt-get update
sudo apt-get install \
      build-essential pkg-config libc6-dev m4 g++-multilib \
      autoconf libtool ncurses-dev unzip git python python-zmq \
      zlib1g-dev wget bsdmainutils automake curl
```

```
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get install g++-4.9
```

```
cd
mkdir .zelcash
echo "rpcuser=username" >> ~/.zelcash/zelcash.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.zelcash/zelcash.conf
echo "addnode=node.zel.cash" >> ~/.zelcash/zelcash.conf
echo "addnode=explorer.zel.cash" >> ~/.zelcash/zelcash.conf
echo "addnode=explorer2.zel.cash" >> ~/.zelcash/zelcash.conf
echo "addnode=explorer.zelcash.online" >> ~/.zelcash/zelcash.conf
echo "addnode=node-eu.zelcash.com" >> ~/.zelcash/zelcash.conf
echo "addnode=node-uk.zelcash.com" >> ~/.zelcash/zelcash.conf
echo "addnode=node-asia.zelcash.com" >> ~/.zelcash/zelcash.conf
```

```{r, engine='bash'}
# pull
git clone https://github.com/zelcash/zelcash.git
cd zelcash
# fetch key
./zcutil/fetch-params.sh
# Build
./zcutil/build.sh -j$(nproc)
# Run a Zelcash node
./src/zelcashd
```
