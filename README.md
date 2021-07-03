 ![s1](https://raw.githubusercontent.com/c4pt000/electrum-wallet-for-dogecoin/master/donate-about-deposit.png)

 
 for docker-dogecoind-full 50GB 
 
 * 04-16-2021 sync
 
 docker run -it -d -p 22555:22555 -p 22556:22556 c4pt/dogecoind-current-full
 
 docker exec -it <docker_vm_hash> bash
 
 
 ```
 yum install python3-plyvel.x86_64 -y
 pip3 install aiorpcx attrs pylru aiohttp
 mkdir /var/electrumx-db
 python3 setup.py install
```

```
#replace with your ip:port for ip:22555
place in /root/.bashrc
source /root/.bashrc
---------------------------------------------

--> also set /etc/electrum-doge.conf

export DB_DIRECTORY=/var/electrumx-db
export DAEMON_URL=http://rpcuser:yourpasswordhere@127.0.0.1:22555/
export COIN=Dogecoin
export ALLOW_ROOT=YES
export SERVICES=tcp://:50001,ssl://:50002,wss://:50004,rpc://
export REPORT_SERVICES=tcp://sv.yourip.com:50001,ssl://sv.yourip.com:50002,wss://sv.yourip.com:50004

```
as root: or electrumx user 

cd /

electrumx_server

See `readthedocs <https://electrumx-spesmilo.readthedocs.io/>`_.

# sample dogecoin.conf in /root/.dogecoin/dogecoin.conf
```
rpcpassword=yoursecretpasswordhere

rpcuser=rpcuser
prune=2200
mempoolexpiry=24
dbcache=1000
server=1
port=22556
rpcport=22555
```
