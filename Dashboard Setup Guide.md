## Step by step guide
1. Enable prometheus option
2. Install node exporter
3. Open ports for prometheus server and node exporter (Firewall settings configuration)
4. Fill in the google form

## 1. Enable prometheus option
Prometheus enables you to monitor all of the "MINA blockchain" related statistics.
- Include the option to enable your mina node to send the informaiton to performance dashboard with this flag: `-metrics-port 6060`

  - Daemon sample code :
```
coda daemon -peer-list-file ~/peers.txt \
  -block-producer-key ~/keys/my-wallet \
  -block-producer-password "YOUR PASSWORD HERE" \
  -generate-genesis-proof true \
  -metrics-port 6060
```

  - Docker sample code :
```
sudo docker run --name mina -d \
-p 8301-8305:8301-8305 \
-p 6060:6060 \
--restart=always \
--mount "type=bind,source=`pwd`/keys,dst=/keys,readonly" \
--mount "type=bind,source=`pwd`/.coda-config,dst=/root/.coda-config" \
--mount type=bind,source="`pwd`/peers.txt,dst=/root/peers.txt",readonly \
minaprotocol/mina-daemon-baked:4.1-turbo-pickles-mina757342b-auto811bf26 daemon \
-peer-list-file /root/peers.txt \
-block-producer-key /keys/my-wallet \
-block-producer-password "YOUR PASSWORD HERE" \
-insecure-rest-server \
-log-level Info \
-metrics-port 6060
```
- How to check: http://YOUR_NODE_IP_ADDRESS:6060/metrics
- Key settings
1. chmod 700 ~/keys
2. chmod 600 ~/keys/my-wallet

  - Systemd sample code:
  ```
  sudo nano .mina-env
  
  CODA_PRIVKEY_PASS="your password here"
  EXTRA_FLAGS="-metrics-port 6060"
  
  [Exit with ctrl+x]
  
  systemctl --user daemon-reload
  systemctl --user start mina
  
  journalctl --user -u mina -n 1000 -f 
  ```

## 2. Install node exporter
The node exporter allows you to monitor all of the "System" related statistics (source: https://github.com/prometheus/node_exporter#using-docker)
- Command (You need to run a seperate docker container for node exporter) :
```
docker run -d \
  --net="host" \
  --pid="host" \
  -v "/:/host:ro,rslave" \
  quay.io/prometheus/node-exporter \
  --path.rootfs=/host
 ```
- How to check : http://YOUR_NODE_IP_ADDRESS:9100/metrics

## 3. Open ports for prometheus server and node exporter (Firewall settings configuration)
- TCP Port 6060 (from 101.101.216.236) : mina daemon metrics port
- TCP Port 9100 (from 101.101.216.236) : node_exporter port

## 4. Fill in the google form
- URL : https://forms.gle/VQPzKvoZpK5jud838
(We DO NOT use your email and private information other than servicing purposes and DSRV does not collect, store or share your personal information to 3rd party)
(All of the information will be deleted immediately after the testnet period.)

## What next?
- You will receiver the URL for the dashboard website along with your own personal ID and Password.
- If you have any technical problems or questions, feel free to reach out  at contact@dsrvlabs.com or at the discord channel.
- Discord : MINA Discord > Node dashboard
@Jongkwang @Seok Hyun (Danny) will be happy to help you out.

Thank you and happy staking! 