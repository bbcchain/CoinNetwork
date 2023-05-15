# Run a BBC Validator
## Setting up a node
1. Git clone https://github.com/bbcchain/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/BBC  /root/
```
3. Create an Account

```
cd /root/BBC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake BBC coin, all you should do is sending your BBC coin to the BBC Consensus contract address over the BBC network from the validator address.
    The BBC Consensus contract address: 0xC226f0AeA65942AB94434997bd0B98b30FF1d53d
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BBC and send the BBC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BBC/nodes/validator/keys/BBC/UTC--xxxx
    /BBC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
