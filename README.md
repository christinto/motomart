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

# How to Setup

1. Run on a local development server 

    ganache-cli test blockchain on port 8545

    - ganache-cli --noVMErrorsOnRPCResponse

2. Connect metamask to ganache-cli

    Metamask should be connected to the local ganache-cli environment on port 8545. 

3. Start lite-server by invoking npm dev

    lite-server is setup in bs-config.json to serve the files required. 