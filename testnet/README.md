# Set up an account on a testnet (Rinkeby)

## Récapitulatif [de ce tuto](https://gist.github.com/cryptogoth/10a98e8078cfd69f7ca892ddbdcf26bc)


### Install geth

```
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum
```

### Download la blockchain Rinkeby de test (3.4GB)

```
$ geth --rinkeby
```

### Start console & create account

/!\ Le path varie en fonction de l'install

```
$ geth --datadir=$HOME/.ethereum/rinkeby attach ipc:$HOME/.ethereum/rinkeby/geth.ipc console

> personal.newAccount("YOUR_PASSWORD")
"0xb2e9fe08ca9a0323103883fe12c9609ed380f475"
```

### Request ETH

- poster son ID sur un réseau social en public.
- Copier le lien du post à cette adresse : [https://www.rinkeby.io/#faucet](https://www.rinkeby.io/#faucet).
- Ensuite cliquer sur `Give me Ehter` > `3 Ether / 8 hours`.
- Attendre 15sec que le bloc soit miné
- Retourner sur la console et :

```
> eth.getBalance(eth.coinbase)
3000000000000000000
```

On a 3 ETH.
