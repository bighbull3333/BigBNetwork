# Run a BigbChain Validator
## Setting up a node
1. git clone https://github.com/bighbull3333/BigBNetwork.git

2. Copy source form node-example to root folder
```
cp -r BigBNetwork/node-example/BigbChain  /root/
```
3. Create an Account
note: Please change validator password in node.pwd before do this step

```
cd /root/BigbChain
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
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

    To stake BIGB coin, all you should do is sending your BIGB coin to the BigB Consensus contract address over the BigB network from the validator address.
    The BigB Consensus contract address: 0x4f38869d5e6bD5E069ca878aA3016268501e7Fc5
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BigB and send the BIGB coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BigbChain/nodes/validator/keys/BigbChain/UTC--xxxx
    /BigbChain/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
