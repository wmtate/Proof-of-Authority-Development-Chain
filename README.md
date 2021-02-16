# Proof-of-Authority-Development-Chain

For this assignment, you will take on the role of a new developer at a small bank.
Your mission, should you choose to accept it, will be to set up a testnet blockchain for your organization.
To do this, you will create and submit four deliverables:


Set up your custom testnet blockchain.


Send a test transaction.


Create a repository.


Write instructions on how to use the chain for the rest of your team.



Background
You have just landed a new job at ZBank, a small, innovative bank that is interested in exploring what
blockchain technology can do for them and their customers.
Your first project at the company is to set up a private testnet that you and your team of developers
can use to explore potentials for blockchain at ZBank.
You have decided on setting up a testnet because:
There is no real money involved, which will give your team of developers the freedom to experiment.
Testnets allows for offline development.
In order to set up a testnet, you will need to use the following skills/tools we learned in class:


Puppeth, to generate your genesis block.


Geth, a command-line tool, to create keys, initialize nodes, and connect the nodes together.


The Clique Proof of Authority algorithm.


Tokens inherently have no value here, so we will provide pre-configured accounts and nodes for easy setup.
After creating the custom development chain, create documentation for others on how to start it using the pre-configured
nodes and accounts. You can name the network anything you want, have fun with it!
Be sure to include any preliminary setup information, such as installing dependencies and environment configuration.

Instructions

Setup the custom out-of-the-box blockchain 


Create a new project directory for your new network. Call it whatever you want!
I created E:\Blockchain Homework as a folder on my network and added files from (Downloads | Go Ethereum
geth.ethereum.org). I also created a Blockchain Tools notepad for my Mnemonic Phrase, Private keys, Address, and nodes, along with public address and path of secret key. 


Create a "Screenshots" folder inside of the project directory.

![image](https://user-images.githubusercontent.com/69773959/108016106-ff2cbc00-6fce-11eb-8c23-1ee738422254.png)

Create accounts for two (or more) nodes for the network with a separate datadir for each using geth.

![image](https://user-images.githubusercontent.com/69773959/108016575-2041dc80-6fd0-11eb-9d35-a68ba0956b3b.png)

Your folder should have 2 nodes 

Run puppeth, name your network, and select the option to configure a new genesis block.


Choose the Clique (Proof of Authority) consensus algorithm.


Paste both account addresses from the first step one at a time into the list of accounts to seal.


Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.


You can choose no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.


Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.


Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.


You can delete the networkname-harmony.json file.


Screenshot the puppeth configuration once complete and save it to the Screenshots folder.

![image](https://user-images.githubusercontent.com/69773959/108016741-7b73cf00-6fd0-11eb-8893-15b7106fc3b0.png)

![image](https://user-images.githubusercontent.com/69773959/108016783-8a5a8180-6fd0-11eb-873e-142d46eb2aa4.png)



Initialize each node with the new networkname.json with geth.

./geth init gensis.json --datadir node1
./geth init gensis.json --datadir node2
![image](https://user-images.githubusercontent.com/69773959/108017223-93981e00-6fd1-11eb-9b59-78d6b6daf047.png)

Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.


Set a different peer port for the second node and use the first node's enode address as the bootnode flag.


Be sure to unlock the account and enable mining on the second node!


You should now see both nodes producing new blocks, congratulations!

![image](https://user-images.githubusercontent.com/69773959/108017266-b0345600-6fd1-11eb-933e-24b741ef7619.png)

![image](https://user-images.githubusercontent.com/69773959/108017299-c8a47080-6fd1-11eb-8a94-3e627f3a6639.png)



Send a test transaction


Use the MyCrypto GUI wallet to connect to the node with the exposed RPC port.


You will need to use a custom network, and include the chain ID, and use ETH as the currency.

![image](https://user-images.githubusercontent.com/69773959/108017384-fbe6ff80-6fd1-11eb-9744-e78c6d7b82fb.png)

Import the keystore file from the `node1/keystore` directory into MyCrypto. This will import the private key.

* Send a transaction from the `node1` account to the `node2` account.

* Copy the transaction hash and paste it into the "TX Status" section of the app, or click "TX Status" in the popup.

* Screenshot the transaction metadata (status, tx hash, block number, etc) and save it to your Screenshots folder.

![image](https://user-images.githubusercontent.com/69773959/108017503-4ff1e400-6fd2-11eb-8427-29e51d296044.png)

![image](https://user-images.githubusercontent.com/69773959/108017518-56805b80-6fd2-11eb-916e-fd846ed48695.png)

![image](https://user-images.githubusercontent.com/69773959/108017531-5c763c80-6fd2-11eb-9452-12b31b029e77.png)

![image](https://user-images.githubusercontent.com/69773959/108017543-613af080-6fd2-11eb-94df-5e4cfea6beea.png)

![image](https://user-images.githubusercontent.com/69773959/108017560-6d26b280-6fd2-11eb-82d7-1cc495dd6d70.png)

![image](https://user-images.githubusercontent.com/69773959/108017571-7283fd00-6fd2-11eb-9fd8-7de760b7d859.png)

![image](https://user-images.githubusercontent.com/69773959/108017577-77e14780-6fd2-11eb-8299-66770eefc0ba.png)

* Celebrate, you just created a blockchain and sent a transaction!

### Create a repository, and instructions for launching the chain

* Create a `README.md` in your project directory and create documentation that explains how to start the network.

* Remember to include any environment setup instructions and dependencies.

* Be sure to include all of the `geth` flags required to get both nodes to mine and explain what they mean.

* Explain the configuration of the network, such as it's blocktime, chain ID, account passwords, ports, etc.

* Explain how to connect MyCrypto to your network and demonstrate (via screenshots and steps) and send a transaction.

* Upload the code, including the `networkname.json` and node folders.

### Remember, *never* share your mainnet private keys! This is a testnet, so coins have no value here!

