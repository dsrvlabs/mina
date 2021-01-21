# Watch Your Node

> Watch Your Node has created a feature that makes it easy to view the Metrics information of nodes.  
> It will be provided for free to Mina nodes.  

<img src="https://user-images.githubusercontent.com/897510/105396121-ded54000-5c62-11eb-8aaf-b8669d4cca70.png" width="60%">


## Settings
You have to do two things.
1. Enable daemon's Metrics(port: 6060) function
2. Open the firewall to allow server access

## 1. Enable daemon's Metrics(port: 6060) function

#### 1-1. When running the node with command
- Original: <code>CODA_PRIVKEY_PASS="password from email" coda daemon -peer-list-file ~/peers.txt -block-producer-key ~/keys/my-wallet -generate-genesis-proof true -file-log -level Debug -super-catchup</code>
  - Reference: https://minaprotocol.com/docs/connecting
- New: <code>CODA_PRIVKEY_PASS="password from email" coda daemon -peer-list-file ~/peers.txt -block-producer-key ~/keys/my-wallet -generate-genesis-proof true -file-log -level Debug -super-catchup -metrics-port 6060</code>
  - (<code>-metrics-port 6060</code> was added at the end)

#### 1-2. When running node with docker

Original
```bash
docker run --name mina -d \
-p 8302:8302 \
--restart=always \
--mount "type=bind,source=`pwd`/keys,dst=/keys,readonly" \
--mount "type=bind,source=`pwd`/.coda-config,dst=/root/.coda-config" \
--mount "type=bind,source=`pwd`/peers.txt,dst=/root/peers.txt,readonly" \
-e CODA_PRIVKEY_PASS="YOUR PASSWORD HERE" \
gcr.io/o1labs-192920/coda-daemon-baked:0.2.6-5c08d6d-5c08d6d-testworld-2258826 \
daemon \
-peer-list-file /root/peers.txt \
-block-producer-key /keys/my-wallet \
-insecure-rest-server \
-file-log-level Debug \
-log-level Info \
-super-catchup
```

New
```
docker run --name mina -d \
-p 8302:8302 \
--restart=always \
--mount "type=bind,source=`pwd`/keys,dst=/keys,readonly" \
--mount "type=bind,source=`pwd`/.coda-config,dst=/root/.coda-config" \
--mount "type=bind,source=`pwd`/peers.txt,dst=/root/peers.txt,readonly" \
-e CODA_PRIVKEY_PASS="YOUR PASSWORD HERE" \
gcr.io/o1labs-192920/coda-daemon-baked:0.2.6-5c08d6d-5c08d6d-testworld-2258826 \
daemon \
-peer-list-file /root/peers.txt \
-block-producer-key /keys/my-wallet \
-insecure-rest-server \
-file-log-level Debug \
-log-level Info \
-super-catchup \
-metrics-port 6060
```

## 2. Open the firewall to allow server access
| Please open the firewall so that the DSRV Platform can collect metrics information.

- Server IP Address : 118.67.130.234
- Port : 6060(tcp)

Reference : https://www.digitalocean.com/docs/networking/firewalls/how-to/configure-rules/

## Contact us
- Discord : https://discord.com/channels/484437221055922177/779045297745690644
- E-Mail : platform@dsrvlabs.com 
