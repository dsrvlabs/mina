# Join Coda testnet beta3 with DSRV!

![enter image description here](https://user-images.githubusercontent.com/21022937/87610675-f6c28900-c740-11ea-8446-a2cf1ddde1a5.png)

### 1. Create your node 
https://www.dsrvlabs.com/en/iaas.html
1. Enter your e-mail address & click coda button
2. After 5 minute, you will receive e-mail 

![enter image description here](https://user-images.githubusercontent.com/21022937/92073904-c5d10d00-edef-11ea-891e-dd6f5400ac6c.png)

### 2. Access to your node with link in e-mail recieved.
Login with your ID & Password.

![enter image description here](https://user-images.githubusercontent.com/21022937/92074045-1183b680-edf0-11ea-9313-962a4633267d.png)


Run initial script.
```
$./0.update_scripts.sh
```
![enter image description here](https://user-images.githubusercontent.com/21022937/92074155-527bcb00-edf0-11ea-8da1-d41ee889a61f.png)

### 3. Create your keypair
```
$coda-generate-keypair-phase3 -privkey-path keys/my-wallet
```
![enter image description here](https://user-images.githubusercontent.com/21022937/92074209-78a16b00-edf0-11ea-8fa0-a379859d2ff8.png)

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
