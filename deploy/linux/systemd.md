## hostsite.caddy

```bash
[Unit]
Description=Caddy
Documentation=https://caddyserver.com/docs/
After=network.target network-online.target
Requires=network-online.target

[Service]
Type=notify
User=hostsite
Group=hostsite
ExecStart=/usr/bin/caddy run --environ --config /home/hostsite/CaddyServer/Caddyfile
ExecReload=/usr/bin/caddy reload --config /home/hostsite/CaddyServer/Caddyfile --force
TimeoutStopSec=5s
LimitNOFILE=1048576
LimitNPROC=512
PrivateTmp=true
ProtectSystem=full
AmbientCapabilities=CAP_NET_BIND_SERVICE

[Install]
WantedBy=multi-user.target
```

## hostsite.filebrowser

```bash
[Unit]
Description=Hostsite Filebrowser
After=network.target network-online.target
Requires=network-online.target

[Service]
Type=simple
User=hostsite
Group=hostsite
ExecStart=python /home/hostsite/FileBrowser/main.py
TimeoutStopSec=5s

[Install]
WantedBy=multi-user.target
```

