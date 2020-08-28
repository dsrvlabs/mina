# Join Coda testnet beta3 with DSRV!

![enter image description here](https://user-images.githubusercontent.com/21022937/87610675-f6c28900-c740-11ea-8446-a2cf1ddde1a5.png)

### 1. Create your node 
https://www.dsrvlabs.com/en/iaas.html
1. Enter your e-mail address & click coda button
2. After 5 minute, you will receive e-mail 

### 2. Access to your node with link in e-mail recieved.
Click & Login with your ID & Password.
Run initial script.
```
$./0.update_scripts.sh
```

### 3. Create your keypair
```
$coda-generate-keypair-phase3 -privkey-path keys/my-wallet
```
simple version:
```
$./1.generate_key.sh
```
After key genenration, Update your key into environment file
```
echo 'export $CODA_PK=<YOUR_PK>' >> ~/.bashrc 
source ~/.bashrc
```



*helpful link: https://forums.codaprotocol.com/t/testnet-beta-phase-3-staking-signups/225*

### 4.  Fill this form to join coda testnet beta phase3
https://docs.google.com/forms/d/e/1FAIpQLSePRIKR0o0LUGFg_jccYhn_29RBFym-3sID5wh18IUUMBgsoA/viewform

### 5. Waiting for announce!
Join Coda official channel:
[https://discord.com/invite/Vexf4ED](https://discord.com/invite/Vexf4ED)


### 6. Install latest binary & run
When testnet starting, doing below.
```
$./0.update_scripts.sh
$./2.download_and_install.sh
$./3.run_coda_node.sh 
```
