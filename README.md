 
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
export DAEMON_URL=http://rpcuser:yourpasswordhere@45.56.96.128:22555/
export COIN=Dogecoin
export ALLOW_ROOT=YES
```
as root: or electrumx user 

electrumx_server

See `readthedocs <https://electrumx-spesmilo.readthedocs.io/>`_.

