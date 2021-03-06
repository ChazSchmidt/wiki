Welcome to the exciting world of building applications on the [Ethereum Blockchain](https://www.ethereum.org/). With Ethereum you can deploy applications or "Smart Contracts" that perform operations and persist state using a decentralized network of computers. Ethereum is often described as a platform for programming digital money. A transaction executes and is confirmed and verified by hundreds of different machines (nodes) distributed around the world. If you want to understand the how blockchains fundamentally work checkout [this visual explanation](https://anders.com/blockchain/). If you'd like to read more about Ethereum specifically, visit this [beginners guide to Ethereum](https://blog.coinbase.com/a-beginners-guide-to-ethereum-46dd486ceecf).

Now that you have a basic understanding of what Ethereum is and does, let's talk about tokens. Fungible tokens (commonly referred to as [ERC20](https://github.com/ethereum/EIPs/issues/20)) are simple smart contracts that track the transfer of a unit of account. You can request this smart contract to [transfer](https://github.com/OpenZeppelin/zeppelin-solidity/blob/master/contracts/token/ERC20/BasicToken.sol#L31) tokens from your account to anyone else's. Others may also transfer tokens from their account to you. All of these requests are transactions on the Ethereum blockchain and cost a small transaction fee. For more information check out the [beginner's guide to Ethereum Tokens](https://blog.coinbase.com/a-beginners-guide-to-ethereum-tokens-fbd5611fe30b).

### 0x protocol

The 0x Protocol extends on this functionality by performing multiple balance transfers in a single atomic operation. If Alice wants to exchange 100 units of TokenA for 200 units of TokenB with Bob, Alice would want to make sure Bob was going to keep his end of the deal. Rather than Alice sending her amount of TokenA to Bob and hoping Bob will send TokenB to Alice sometime in the future, the 0x Protocol performs this exchange in a guaranteed atomic operation. So Alice and Bob will get exactly what they expect. The 0x Protocol is designed to minimize the amount of transactions (and fees) required for Alice and Bob to successfully exchange tokens. 0x protocol uses a process involving off-chain orders with on-chain settlement. You can find more information on the 0x Protocol by reading our [whitepaper](https://0xproject.com/pdfs/0x_white_paper.pdf) or the [beginners guide to 0x](https://blog.0xproject.com/a-beginners-guide-to-0x-81d30298a5e0).

### Interacting with the Ethereum blockchain

As web browsers do not natively support interacting with the Ethereum Blockchain, a browser extension called [Metamask](https://metamask.io/) is one way to fill that gap. Metamask will handle the users private keys and allow them to submit transactions to the network via an Ethereum node. Metamask communicates with the sites a user visits by injecting a Javascript object through which the site can communicate with the wallet and blockchain. For mobile users there are applications like [Toshi](https://www.toshi.org/) and [Cipher Browser](https://www.cipherbrowser.com/) that do the same thing on mobile.

In order to interact with dApps (distributed applications) a user must have Ether in a wallet they control. The user cannot interact with dApps from an exchange such as Coinbase. They must control the private keys associated with their Ethereum address.

### Development

<div align="center">
    <a href="https://codesandbox.io/s/github/0xproject/0x-codesandbox" target="_blank" rel="Sandbox">
        <img src="https://s3.eu-west-2.amazonaws.com/0x-wiki-images/sandbox.png" style="padding-bottom: 20px; padding-top: 20px; max-width: 761px;" width="80%" />
    </a>
</div>

#### Test networks

Development and testing are aided by running in your own local test Ethereum node. This allows you to quickly deploy and interact with contracts without spending real ETH. [Ganache](https://github.com/trufflesuite/ganache) simulates an Ethereum node locally and provides the same JSON RPC interface as a real node. Since there can still be small differences between it and a real Ethereum node (e.g [Geth](https://github.com/ethereum/go-ethereum) or [Parity](https://github.com/paritytech/parity)) so we recommend you also test your application on a live testnet (i.e Kovan, Rinkeby, or Ropsten) before deploying on to the main Ethereum network.

Rather than spinning up your own Ethereum node infrastructure to connect to the network, many developers use [INFURA](https://infura.io/). They provide public, scalable Ethereum nodes as a service. Since Ethereum nodes were not designed to handle thousands of requests per second, Infura has built out infrastructure around the nodes to make them more performant.

It can be difficult to get a sufficient amount of test Ether to deploy your contracts on test networks and begin testing them. Because of this, we have created a faucet which can dispense small amounts of Ether to your account. Navigate over to the [0x Portal](https://0xproject.com/portal/balances) with Metamask installed and click "Request" to receive some free test Ether (make sure you're connected to a testnet)!

<div align="center">
    <a href="https://0xproject.com/portal/balances">
        <img src="https://s3.eu-west-2.amazonaws.com/0x-wiki-images/network_screenshot.png" style="padding-bottom: 20px; padding-top: 20px; max-width: 761px;" width="80%" />
    </a>
</div>

### Wrapped ETH

By now you are likely familiar with the ERC20 standard, Ether (aka ETH) and the plethora of ERC20 tokens out there. Unfortunately, ETH is not an ERC20 token and because of this cannot interact directly with the 0x protocol. What we can do however, is deposit ETH into an ERC20-compliant smart contract which credits your account with the same amount of WETH (wrapped Ether) tokens as the amount of ETH you deposited. These tokens are also redeemable 1-to-1 for Ether. In this ERC20-compliant form, Ether can be traded for other tokens using 0x protocol. This work-around for Ether is becoming increasingly common in the entire ecosystem. More information on WETH and how it works can be found [here](https://weth.io/).

Now that you have a high-level overview of Ethereum Blockchain development, it is time to check out our other tutorials and examples. Be sure to try out our [Sandbox](https://codesandbox.io/s/1qmjyp7p5j) which provides a development environment ready for you to experiment with.

### Next steps

Now that you've got a basic understanding of what is involved when developing on Ethereum, you're now ready to go onto the next step of [Building a Relayer](#Build-A-Relayer). If you'd rather jump right in, you can skip straight to learning how to [Create, Validate and Fill Orders](https://0xproject.com/wiki#Create,-Validate,-Fill-Order) on 0x.
