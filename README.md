# Private-Blockchain
This repository contains the simplest steps to create a private / permissioned Blockchain, much like JPM's Quorum, that allows for a restricted group of network users / nodes. Solidity smart contracts can be published to this private chain just as with the MainNet and TestNet using Mist.

The 'chainData' folder includes a log of all the private blockchain's transactions / confirmations / etc. 

Nodes in this private network must use mining to confirm transactions and smart contract deployment. Since this is a private network, with fewer authorized users, block confirmation times are much quicker than Ethereum at ~1 sec. Of course, this block confirmation speed has the tradeoff of less decentralization (Ethereum has over 17,000 nodes worldwide on it's network, which reinforces security). 

Below are a list of the steps taken to create the private blockchain and interact with it using the Mist browser: 

1) Download and install geth: https://geth.ethereum.org/downloads/
2) Download the genesis.json file in this repository, place it in a new folder
3) Open the command line and cursor to the path directory of the new folder you created in step 2 that houses the genesis.json file
4) Run the following in the command line: geth --datadir=./chaindata init genesis.json
5) You just created Block 1 of your very own private blockchain network!!
6) Now to access your private blockchain network node enter in the command line: geth --datadir=./chaindata
7) Open a second command line window, leaving the first one open and running. Repeat step 3 to cursor to the right directory.
8) Access the Geth Javascript console by entering in the command line: geth attach ipc:\\.\pipe\geth.ipc
9) Open Mist (run as administrator). It should automatically detect your private blockchain network running and connect to it.
10) In Mist, follow the steps to "Add an Account" 
11) In Mist, you can also "Deploy a New Contract" to your private network under the contracts tab. This accepts the same Solidity smart contact code as the MainNet or TestNet. 
12) You must "mine" to confirm and officially deploy any new contract / transaction to the private network. Do this by:
  a) In your second command prompt window, enter: miner.setEtherbase(eth.accounts[0]);
  b) then: miner.start(3);
13) In Mist, on the "Wallets" tab, you'll see your account start earning Ether as you mine. You'll also see your pending transactions start to be confirmed (after 12 confirmaitons they will be officially written to the private blockchain). 
14) Once contract is deployed, interact with it on the 'Contracts' tab by clicking on the contract name your interested in
15) From there you can call any of the functions embedded in your Solidity code, just like Remix. 
16) Be sure to keep mining so that all transactions get processed / confirmed properly.
17) You can stop mining at any time by entering: miner.stop();

Enjoy!

*note how in Mist it is not connected to the MainNet or TestNet but our Private Blockchain Network!!
![image](https://user-images.githubusercontent.com/29802069/41245192-5ee7bd52-6d75-11e8-99e5-ba79ee0f0852.png)

*example of how to mine with your private blockchain
![image](https://user-images.githubusercontent.com/29802069/41245236-7888d084-6d75-11e8-8d0d-bfe5de147cbf.png)


