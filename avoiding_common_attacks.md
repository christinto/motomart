# Avoiding Common Attacks

### Avoid 'reentry' recursive calls

We manage the state of the vehicle has to be in a FOR SALE / 


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
 
 ### Denial of Service prevention - reduce use of loops
 
 * The contract doesn't avoids any looping behaviour  
 * Only the owner of the vehicle can change the state of the vehicle to be for sale 
 * Only vehicles with For Sale state can be bought with ETHER by a buyer
 
 
 

