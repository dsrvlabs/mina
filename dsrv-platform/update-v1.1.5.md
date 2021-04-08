# Release: v1.1.5 Mainnet Stability Fixes - Migratation Notice

As Mina mainnet is updated, you need to execute the command below.
- Until : Not specified
- Notice : https://discord.com/channels/484437221055922177/816099272859844638/829402925469532171

```
systemctl stop mina

echo "deb [trusted=yes] http://packages.o1test.net release main" | sudo tee /etc/apt/sources.list.d/mina.list
sudo apt-get update -y
sudo apt-get install -y curl unzip mina-mainnet=1.1.5-a42bdee

systemctl start mina

mina version
```

You should see something like this on your screen.

```
Commit a42bdeef6b0c15ee34616e4df76c882b0c5c7c2a on branch master
```

## Any question
- E-Mail : jongkwang.kim@dsrvlabs.com
- Discord Channel : Mina Protocol > #node-dashboard
- Discord DM : Jongkwang | DSRV#5619

Thank you
