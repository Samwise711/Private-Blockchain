# Private-Blockchain
This repository contains a simple list of steps to create your own private Blockchain, much like JPM's Quorum, allowing for a restricted group of users to access the network. Solidity smart contracts can be published to this private blockchain, just as with the MainNet and TestNet, using the Mist browser.

The 'chaindata' folder generates a log of all the blockchain's transactions / confirmations / etc. 

Nodes (i.e. users and their computers) in this private network must use mining to confirm transactions and finalize smart contract deployment. Since this is a private network, with limited authorized users, block times are much quicker than Ethereum at ~1 sec. Of course, this block confirmation speed has the tradeoff of less decentralization (Ethereum has over 17,000 nodes worldwide on it's network, which reinforces security). 

# Here are the steps on how to create your own private blockchain and interact with it using the Mist browser: 

1) Download and install geth & Mist: https://geth.ethereum.org/downloads/ https://github.com/ethereum/mist/releases
2) Download the genesis.json file from this repository, place it in a new empty folder you create anywhere on your computer
3) Open the command line and cursor to the path directory of the folder you just created, which houses the genesis.json file
4) Open command line as admin, and run the following: geth --datadir=./chaindata init genesis.json
5) Congrats! You just created Block 1 of your very own private blockchain network!!
6) Now, to run your private blockchain node, enter the following in command line: geth --datadir=./chaindata
7) Open Mist (run as administrator). It should automatically detect your private blockchain network running and connect to it.
8) In Mist, follow the steps to "Add an Account" 
9) Open a second command line window, leaving the first open and running. Repeat step 3 and cursor to the proper folder directory.
10) In the second command line window, access the Geth Javascript console by entering: geth attach ipc:\\.\pipe\geth.ipc
11) In Mist, you can also "Deploy a New Contract" to your private network under the contracts tab. This accepts the same Solidity smart contact code as the MainNet or TestNet. 
12) You must "mine" to confirm and officially deploy any new contract / transaction to the private network. Do this by:
  a) In your second command prompt window, enter: miner.setEtherbase(eth.accounts[0]);
  b) then: miner.start(3);
13) In Mist, on the "Wallets" tab, you'll see your account start earning Ether as you mine. You'll also see your pending transactions start to be confirmed (after 12 confirmaitons they will be officially written to the private blockchain). 
14) Once contract is deployed, interact with it on the 'Contracts' tab by clicking on the appropriate contract name
15) From there, you can call any of the functions embedded in your Solidity code, just like in Remix. 
16) Be sure to keep mining in your second command prompt window so that all transactions get processed / confirmed fully.
17) You can stop mining at any time by entering: miner.stop();

Enjoy!

*note how in Mist it is not connected to the MainNet or TestNet but our Private Blockchain Network!!
![image](https://user-images.githubusercontent.com/29802069/41245192-5ee7bd52-6d75-11e8-99e5-ba79ee0f0852.png)

*example of how to mine with your private blockchain
![image](https://user-images.githubusercontent.com/29802069/41245236-7888d084-6d75-11e8-8d0d-bfe5de147cbf.png)


