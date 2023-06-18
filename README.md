*******🟢UPDATE banksyd 🟢******* 18.06.23
```python
cd $HOME/composable-centauri
git pull
cd $HOME
rm -rf composable-centauri
git clone https://github.com/notional-labs/composable-centauri/
cd composable-centauri
git checkout v3.1.0
make build
cd bin
mv centaurid $HOME/go/bin/banksyd
banksyd version --long | grep -e commit -e version
#version: 3.0.3-testnet
#commit: fa8396c245ac495dd4707552dd13abf25217a9f6
#version: v3.0.3-testnet
#commit: 1bc799bd823dae4579bc925c51ede67a7411a43f
sudo systemctl restart banksyd && sudo journalctl -u banksyd -f -o cat
curl -s http://localhost:26657/consensus_state  | jq '.result.round_state.height_vote_set[0].prevotes_bit_array'
```
