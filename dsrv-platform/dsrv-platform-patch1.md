## One setting in the file is missing.
This is our mistake and please correct it as follows. sorry.


## vi /etc/systemd/system/mina.service
| `--block-producer-key /root/keys/my-wallet \` missing line

```
[Unit]
Description=Mina Daemon Service
After=network.target
StartLimitIntervalSec=60
StartLimitBurst=3

[Service]
EnvironmentFile=/root/.mina-env
Type=simple
Restart=always
RestartSec=15
ExecStart=/usr/local/bin/mina daemon \
  --generate-genesis-proof true \
  --peer-list-url https://storage.googleapis.com/mina-seed-lists/mainnet_seeds.txt \
  --log-level Info \
  --file-log-level Info \
  --block-producer-key /root/keys/my-wallet \
  $EXTRA_FLAGS
ExecStop=/usr/local/bin/mina client stop-daemon

[Install]
WantedBy=multi-user.target
```

## daemon-reload
```
systemctl daemon-reload 
```

## daemon restart
```
systemctl restart mina 
```
