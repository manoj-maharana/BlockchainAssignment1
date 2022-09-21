● Create at least 10 nodes as miners who are connected to each other. Each miner is connected to at least 2 usres.

● Create a wallet which contains private and public keys.

● Use the hash of the public key as the address of each user’s wallet. 

● Using digital signatures verify the sender and receiver.

● The header of a block in the blockchain should contain: block index, timestamp, previous block hash, and merkle root.

● The body of the block should contain the hash of each transaction.

● Store the transactions in UTXO format ( w.r.t. Bitcoin wallet).

## Create new Wallet:
http://192.168.1.8:5001/create_wallet
![image](https://user-images.githubusercontent.com/27220747/191544563-e8213085-1dce-474f-a627-0b685f6cb66f.png)

As you can see I created 7 wallet. To show all the balances -
http://192.168.1.8:5001/show_balances
![image](https://user-images.githubusercontent.com/27220747/191545308-5ebeeaca-71ce-4a28-b1ef-1461dd0715ab.png)
Display all the private keys:
![image](https://user-images.githubusercontent.com/27220747/191545858-52211f29-65dc-4a76-8d08-d7bfcf3ab33e.png)
 For create new transaction I used 
 
 http://192.168.1.8:5001/create_transaction (POST Method)
 
 It requires the private key as well as sender, receiver and amount.
 {
    "sender":"1",
    "receiver":"2",
    "amount":100,
    "private_key":"b911706bb470fdb4"
    
}

Here I am sending 100 amount from Wallet 1 to Wallet 2. For successfully transaction It will send us the newly created transaction Id.

![image](https://user-images.githubusercontent.com/27220747/191547027-ccd4b7ef-388c-4468-86e3-9ec3a0e6fb5d.png)

To Know the mem pool(as we know the mem pool is a smaller database of unconfirmed or pending transactions which every node keeps)
http://192.168.1.8:5001/show_mempool

![image](https://user-images.githubusercontent.com/27220747/191547633-f0b6390b-a354-4d73-ad9e-2e4c90c0d953.png)


 

### Run Code Steps
## http://192.168.1.8:5001/get_chain
## http://192.168.1.8:5001/mine_block
## http://192.168.1.8:5001/mine_block
## http://192.168.1.8:5002/replace_chain
## http://192.168.1.8:5001/connect_node
Connect Node requires previous and after node port like-

{
    "nodes":["http://192.168.1.8:5002",
             "http://192.168.1.8:5003"]
}

After 10 connect node we are connected each minor to atleast 2 nodes.
## http://192.168.1.8:5002/replace_chain
For merkle root -->

![image](https://user-images.githubusercontent.com/27220747/191543344-8e89d2b8-ce07-49ca-8a59-257e7fc61067.png)


For add transaction-->
## http://192.168.1.8:5001/add_transaction (POST Method)
In body It requires:
{
    "sender":"Adam",
    "receiver":"Sachin",
    "amount": 5000   
}
For Mine block: 
http://192.168.1.8:5001/mine_block
