ALPACA CITY BUG BOUNTY  - Alpaca Squad Transaction Cost Too High
--------------------------------------------------------------------

When sending Alpaca's to the Alpaca Squad the function onERC1155BatchReceived is being called by the Alpaca Squad contract to let the 
contract know how to handle the incomming ERC1155 tokens. 

What I noticed is that for every Alpaca incomming the contract gives permission to breed to the original owner. I get why you did this, so 
the users can breed with their Alpaca while it is still in the Squad Farm. But not all users might want to breed with all Alpaca's in there Squad. 

One way to fix this is by splitting up the transactions. Maybe just let them send it the the farm. And then later they can call a function to approve
the Alpacas to breed. You can even do this in the same window in the front end. It would work like Uniswap approving and then swapping. 

This would save significant gas, as almost 70% is spent on approving to breed and storing the user data inside the contract. So I can see a 30% gas 
reduction here. 

A more in debth soloution would be to use a other ERC1155 implementation. But this wont work now as you already have all other contracts deployed. See articles below; 
    - https://github.com/arcadeum/multi-token-standard
    - https://medium.com/horizongames/going-beyond-erc20-and-erc721-9acebd4ff6ef


