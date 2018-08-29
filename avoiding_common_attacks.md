# Avoiding Common Attacks

### Avoid 'reentry' recursive calls and Cross function race conditions

* We manage the state of the vehicle has to be in a FOR SALE / SOLD before another person can actually buy the bike. 

* Mitigates the risk of race condition where the owner of the bike can List a bike for sale and at the same time transfer the bike to another address when someone else has bought the bike. 

*transferBike has to be in RoadWorthy state and not in ForSale state as another user could be trying to buy a bike 

    `  function transferBike(uint _vin, address _newOwner) bikeOwnerOnly(motorbikeMap[_vin].owner) roadWorthy(_vin) stopInEmergency public returns (string) {
         emit TransferVehicle(_vin);
         motorbikeMap[_vin].owner = _newOwner;
         motorbikeMap[_vin].status = Status.RoadWorthy;
     }`

### Integer Arithmetic Overflow

We ensure that our uint data type variables are not allowed to be over-flowed by using the safeMath library to add and multiply the fees that we collect from the users when they sell / buy the bikes. 

We ensure that we don't transfer to the user more than the price they have set and also that the fee component we calculate using safeMath library to ensure that the number multiplied and divided are still valid integer. 

    `contract MotorbikeMart is Owned, CircuitBreaker {
     using SafeMath for uint;
     }
     
     uint fee = (motorbikeMap[vin].price).mul(SALE_FEE_PERCENT) / 100;

     emit Fee(fee);

     owner.transfer((motorbikeMap[vin].price).sub(fee));
 `
 
 ### Denial of Service prevention - reduce use of loops and running out of gas limit
 
 * The contract doesn't avoids any looping behaviour  
 * Avoids recursive calls in the contract 
 * Only the owner of the vehicle can change the state of the vehicle to be for sale 
 * Only vehicles with For Sale state can be bought with ETHER by a buyer
 
 ### Reduce malicious creator
 
 * The fee component of the motorbike mart is a constant value set in the construction of the contract. The owner of the contract can not alter the fee after creation of the contract. 
 
* Only allowing the contract owner to withdraw funds from the contract that is collected from the commission fees during the trading of motor bikes. 
 
 

