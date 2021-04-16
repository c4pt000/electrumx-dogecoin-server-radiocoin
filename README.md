 
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



export DB_DIRECTORY=/var/electrumx-db
export DAEMON_URL=http://rpcuser:yourpasswordhere@127.0.0.1:22555/
export COIN=Dogecoin
export ALLOW_ROOT=YES
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
