# https://github.com/samayun/javascript-basic-problem-solving


* ### kilometerToMeter
``` js
/**
 * Kilometer to Meter Unit Conversion
 * @param Number km
 * @return Number meter
 */
function kilometerToMeter(km) {
    if (typeof km != "number") {
        return "Please Input Number Please! ";
    }
    if (km < 0) {
        return "Please Input Positive Unit";
    }
    // 1km = 1000 meter
    return km * 1000;
}
```
```js
   // TESTING 
    var getKilometerToMeterResult = kilometerToMeter(1);
    console.assert(getKilometerToMeterResult === 1000);
```
* ### budgetCalculator
``` js
/**
 * Budget Calculate for electronics store
 * @param Number clockQuantity , Number phoneQuantity , Number laptopQuantity ,
 * @return Number totalCost
 */
function budgetCalculator(clockQuantity, phoneQuantity, laptopQuantity) {
    // Validation
    if (
        typeof clockQuantity != "number" ||
        typeof phoneQuantity != "number" ||
        typeof laptopQuantity != "number"
    ) {
        return "Wrong Input! Please Provide all credentials properly";
    }
    if (clockQuantity <= 0 || phoneQuantity <= 0 || laptopQuantity <= 0) {
        return "Wrong Input! Please Provide valid quantity (minimum 1 quantity)";
    }

    var clockPrice  = clockQuantity * 50; // 1 clock = 50TK
    var phonePrice  = phoneQuantity * 100; // 1 phone = 100TK
    var laptopPrice = laptopQuantity * 500; // 1 laptop = 500TK

    var totalCost   = clockPrice + phonePrice + laptopPrice;
    return totalCost;
}
```
``` js
    // TESTING
    var getBudgetCalculatorResult = budgetCalculator(1,1,1);
    console.assert(getBudgetCalculatorResult == 650);
```


* ### hotelCost

``` js
/**
 * Hotel Booking cost calculation for some cases
 * @param Number stayDayCount
 * @return Number totalCost
 */
function hotelCost(stayDayCount) {
    if (typeof stayDayCount != "number") {
        return "Input Number Please!";
    }
    if (stayDayCount < 0) {
        return "Invalid Input, You can't stay minus day";
    }
    var totalCost = 0;
    var first10DayCost = 10 * 100;
    var second10DayCost = 10 * 80;

    // firstCase - first 10 stay days cost is 100TK/1Day
    if (stayDayCount <= 10) {
        totalCost = stayDayCount * 100;
    }
    // secondCase - 11-20 stay days cost is 80TK/1Day -(firstCaseCost included like VAT)
    else if (stayDayCount <= 20) {
        var remaining = stayDayCount - 10;
        var second10DayCost = remaining * 80;
        totalCost = first10DayCost + second10DayCost;
    }
    // thirdCase - 20+ stay days cost is 50TK/1Day -(firstCaseCost & secondCaseCost included like VAT)
    else {
        var remaining = stayDayCount - 20;
        var thirdCaseCost = remaining * 50;
        totalCost = first10DayCost + second10DayCost + thirdCaseCost;
    }
    return totalCost;
}
```

``` js
    // TESTING
    var getHotelCostResult = hotelCost(12);
    console.assert(getHotelCostResult == 1160);

```

* ### megaFriend
``` js
/**
 * Finding Longest Named friend's name from an array
 * @param Array friends
 * @return String largestNamedFriend
 */
function megaFriend(friends) {
    // Santization of Input
    if (typeof friends !== "object") {
        return "Input must be a valid array of strings";
    }
    // empty array Santization
    if (!friends.length) {
        return "Please marry first :) You need a friend to make life easier";
    }
    var largestNamedFriend = friends[0];
    for (var i = 0; i < friends.length; i++) {
        var friendName = friends[i];
        if (typeof friendName == "number" || friendName == "" || friendName == " " || friendName == "  ") {
            return "Minimum one friend name is  or not proper String, Please provide valid names";
        }
        if (friendName.length > largestNamedFriend.length) {
            largestNamedFriend = friends[i];
        }
    }
    return largestNamedFriend;
}
```

``` js
    // TESTING
    
    var friends = ["Samayun","Mohammad","Abdullah Mohammad"];
    var getMegaFriendResult = megaFriend(friends);
    console.log(getMegaFriendResult);

```