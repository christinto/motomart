# MotoBike Market / Registry
Tools & Framework needed.
Metamask-wallet
Truffle framework

# What does this project do

A motorbike mart for people to list their motorbikes and set them for sale. 

Owners of a motorbike can set the price in ETHER when they put a motorbike up for sale.

Metamask integration will allow you to see which motorbikes are owned by you / can be purchased if owned by another address.

Metamask should be connected to the local ganache-cli environment on port 8545. 

Select the address you want to use from metamask when interacting with the motorbike mart. 

1. List motorbike for sale and set the price asking for
2. Bike owner can also transfer the ownership of their listed motorbike to another address.
3. Someone can buy the listed motorbikes that is not their's by sending in ETH that covers the price asked.
4. Purchase motorbike by sending the price in Ether and any extra will be refunded back to buyer. 

5. motorbike Mart contract owner will take a small fee out of the purchase price when a motorbike gets sold. (5%).
6. Circuit breaker will stop people from selling and buying motorbikes / allow owner to withdraw the balance from contract.

# Example Inputs 

 - VIN: 1100225125
 - Make: Kawaski 
 - Model: Ninja
 - Year: 2018
 - Capacity: 2100
 
1. Submit new vehicle 
2. Owner can set a sell Price in ETH and press sell to list the item up as For Sale.

3. Search car details up via VIN
4. User can do a on-chain transfer of their motorbike to another Address on the blockchain so that they become the new owner. 
5. Switch accounts on Metamask and reload the app

6. Ability to buy a motorbike that is listed and ownd by another address. 
7. Takes ETHER as payment and if enough is paid, transfers the ownership over to the buyer.

# Search function

Ability to search information about any motorbike by inputting the VIN identification number 

#
 
# How to Setup

1. Run on a local development server 

    ganache-cli test blockchain on port 8545

    - ganache-cli --noVMErrorsOnRPCResponse

2. Truffle compile & Truffle migrate

3. Connect metamask to ganache-cli

    Metamask should be connected to the local ganache-cli environment on port 8545.
    
    Select Private Network - localhost:8545 
    
    Metamask will inject the account into the app

4. Start lite-server by invoking npm run dev

    lite-server is setup in bs-config.json to serve the files required. 
    
5. Browse to URL - localhost:3000 to run app