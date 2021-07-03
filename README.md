
 

 
 ```
 yum install python3-plyvel.x86_64 -y
 pip3 install aiorpcx attrs pylru aiohttp
 mkdir /var/electrumx-db
 python3 setup.py install
```


create ssl cert in /opt/electrumx-dogecoin-server/
```
 openssl genrsa -out server.key 2048
 openssl req -new -key server.key -out server.csr
 openssl x509 -req -days 1825 -in server.csr -signkey server.key -out server.crt
```
change radioblockchain.info to your FQDN
```
DB_DIRECTORY=/var/electrumx-db
DAEMON_URL=http://rpcuser:yourpasswordhere@127.0.0.1:22555/
COIN=Radiocoin
ALLOW_ROOT=YES
export SERVICES=tcp://:50001,ssl://:50002,wss://:50004,rpc://
export REPORT_SERVICES=tcp://radioblockchain.info:50001,ssl://radioblockchain.info:50002,wss://radioblockchain.info:50004
SSL_CERTFILE=/opt/electrumx-dogecoin-server/server.crt
SSL_KEYFILE=/opt/electrumx-dogecoin-server/server.key

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
