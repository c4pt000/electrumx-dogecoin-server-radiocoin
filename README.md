
 for electrum-radiocoin wallet

https://github.com/c4pt000/electrum-radiocoin

for electrum-dogecoin wallet

https://github.com/c4pt000/electrum-dogecoin

for crontab -e (crontab-stuff goes in crontab -e )

```
https://github.com/c4pt000/electrumx-dogecoin-server-radiocoin-4.1.4/blob/main/crontab-stuff
https://github.com/c4pt000/electrumx-dogecoin-server-radiocoin-4.1.4/blob/main/electrum-radc-server
https://github.com/c4pt000/electrumx-dogecoin-server-radiocoin-4.1.4/blob/main/reset-electrumx-server
```



# (fedora 34)

create ssl cert in /etc
```
cd /etc
 openssl genrsa -out server.key 2048
 openssl req -new -key server.key -out server.csr
 openssl x509 -req -days 1825 -in server.csr -signkey server.key -out server.crt
```
edit banner.txt
copy banner.txt to /etc
mkdir /var/electrumx-db
edit electrumx.source
change rpc and remote ip

change 172.104.64.180 to your FQDN and rpcuser:yourpasswordhere to radiocoin.conf


```
#export ELECTRUMX = dir-to/electrumx_server

export DB_DIRECTORY=/var/electrumx-db
export DB_ENGINE=leveldb

export COST_SOFT_LIMIT=0
export COST_HARD_LIMIT=0


export DAEMON_URL=http://rpcuser:yW70pssqLGVeqbjekl@127.0.0.1:9332/
export COIN=Radiocoin

export ALLOW_ROOT=YES

export PEER_DISCOVERY=ON

export SERVICES=tcp://172.104.64.180:50001,ssl://172.104.64.180:50002,wss://172.104.64.180:50004,rpc://
export REPORT_SERVICES=tcp://172.104.64.180:50001,ssl://172.104.64.180:50002,wss://172.104.64.180:50004
export MAX_SESSIONS=2000
export CACHE_MB=1800
export SSL_CERTFILE=/etc/server.crt
export SSL_KEYFILE=/etc/server.key
export DAEMON_VERSION=radiocoin-electrumX-for.2.2.1
export BANNER_FILE=/etc/banner.txt
export DONATION_ADDRESS=DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B
#export ANON_LOGS=whats a log


# cp server.* /etc
# cp banner.txt /etc
#echo "ulimit -n 10000" >> ~/.bash_profile
# source ~/.bash_profile
```






as root: or electrumx user 
if not already in the bashrc

```
echo "ulimit -n 10000" >> ~/.bash_profile
source ~/.bash_profile
```

cd /opt/electrumx-dogecoin-server-radiocoin-4.1.4
source electrumx.source
python3 -m pip install .
./electrumx_server

See `readthedocs <https://electrumx-spesmilo.readthedocs.io/>`_.

