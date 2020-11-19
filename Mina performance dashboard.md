## MINA NODE PERFORMANCE DASHBOARD OPEN!!

Happy Wednesday everyone! We are extremely excited to present our Mina node performance dashboard to all of mina community members.
We are DSRV, a validator and blockchain infrastructure provider based in South Korea. As a cohort 1 genesis founding member and testnet MVP of Mina, we have been making technical & community contributions since the start of Mina protocol.  
As part of our contribution, we built an essential tool for node management and monitoring at Mina protocol and would like to introduce to all of you :)

## What is Mina performance dashboard?
Mina performance dashboard is a node monitoring tool, crucial for all block producers and snarkers at Mina protocol who operates a node. 
With this dashboard, node operators can easily monitor all of the key metrics in running a mina node.
In a single screen, the dashboard shows you the node uptime, current operational status, how many blocks or snarks are produced and many more!
And all of this amazing features will be presented to mina community members in testnet 4.1 for FREE.

## Why should I use it?
Mina performance dashboard is an open-sourced project and anyone can visit the repository at the link (https://github.com/dsrvlabs/mina-performance-dashboard), follow the setup instructions and run their own hosting server.
However, running a monitoring server in addition to your block producer & snarker node is a very huge burden both in terms of time and money.
As a team for developing the dashboard, DSRV would like to share our technical and operational knowledge with community members and help you to better run your own node.
Mina community members can use our service for FREE and better run & operate nodes to produce more blocks and snarks! 

## How can I receive the benefits?
We will start providing our service from testnet 4.1 and so on (in the mainnet as well of course) and would have a seperate website for any mina community member to submit their application.
Unfortunately, we would have to receive your application via google form just for testnet 4.1, until our platform is ready. (We are preparing something all mina community members would LOVE SO MUCH!!)
Sign up right now to enjoy our service, we will send you your own personal ID and password to access the performance dashboard.
You can start by clicking this link (https://forms.gle/VQPzKvoZpK5jud838).

# MINA performance dashboard application: https://forms.gle/VQPzKvoZpK5jud838

## Step by step guide
1. Enable prometheus option
2. Install node exporter
3. Open ports for prometheus server and node exporter (Firewall settings configuration)
4. Fill in the google form

## 1. Enable prometheus option
Prometheus enables you to monitor all of the "MINA blockchain" related statistics.
- Include the option to enable your mina node to send the informaiton to performance dashboard with this flag: `--metrics-port 6060` (강조)

  - Daemon sample code :
'''
coda daemon -peer-list-file ~/peers.txt -block-producer-key ~/keys/my-wallet -block-producer-password "password" -generate-genesis-proof true --metrics-port 6060
'''

  - Docker sample code :
'''
sudo docker run --name mina -d \
-p 8301-8305:8301-8305 \
--publish 3085:3085 \
--metrics-port 6060 \
--restart=always \
--mount "type=bind,source=`pwd`/keys,dst=/keys,readonly" \
--mount "type=bind,source=`pwd`/.coda-config,dst=/root/.coda-config" \
--mount type=bind,source="`pwd`/peers.txt,dst=/root/peers.txt",readonly \
minaprotocol/mina-daemon-baked:4.1-turbo-pickles-mina757342b-auto811bf26 daemon \
-peer-list-file /root/peers.txt \
-block-producer-key /keys/my-wallet \
-block-producer-password "YOUR PASSWORD HERE" \
-insecure-rest-server \
-log-level Info
'''
- How to check: http://{$YOUR_NODE_IP_ADDRESS}:6060

## 2. Install node exporter
The node exporter allows you to monitor all of the "System" related statistics (source: https://github.com/prometheus/node_exporter#using-docker)
- Command (You need to run a seperate docker container for node exporter) :
docker run -d \
  --net="host" \
  --pid="host" \
  -v "/:/host:ro,rslave" \
  quay.io/prometheus/node-exporter \
  --path.rootfs=/host
- How to check : http://NODE_IP_ADDRESS:9100/metrics

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
- Discord : MINA Discord > Performance dashboard
@Jongkwang @Seok Hyun (Danny) will be happy to help you out.

Thank you and happy stakinging! 
