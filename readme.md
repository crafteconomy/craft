# Craft Economy
**Craft Economy** is a blockchain based economy where value is derived from playing Minecraft. In Craft players are able to leverage the $CRAFT token to buy and sell items that exist as NFT's on the blockchain. Craft also serves as an educational platform for people interested in learning DEFI. Craft is built on the Cosmos SDK in order to provide users with an easy and cost effective expereince. 

## Get started

```Shell
git clone https://github.com/crafteconomy/craft
cd craft
cd cmd/craftd
go mod tidy
go install .
mv $HOME/go/bin/craftd /usr/bin
craftd init <moniker>
cd $HOME/.craftd/config
rm genesis.json
wget -O genesis.json https://cloudflare-ipfs.com/ipfs/QmcuMhkRVyhTdRmsx5Mh8tBVA7145KQwvfrNiTE8FzMGFM
```
Persistent Peers
`0b9b1eedc4cd011bc03320a4fa4876b863ec263c@143.198.94.140:1337`

Service File
```Shell
[Unit]
Description=Craft Node
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=$HOME
ExecStart=$HOME/go/bin/craftd start
Restart=on-failure
StartLimitInterval=0
RestartSec=3
LimitNOFILE=65535
LimitMEMLOCK=209715200

[Install]
WantedBy=multi-user.target
```
Start the chain
```Shell
systemctl daemon-reload
systemctl enable craft
systemctl start craft
```



