### Challenge 1: Grow a Circle
#### Given the Circle structure below:
```
struct Circle {
  
  var radius = 0.0

  var area: Double {
    .pi * radius * radius
  }

  init(radius: Double) {
    self.radius = radius
  }
}
```
#### Write a method that can change an instance’s area by a growth factor.
#### For example, if you call circle.grow(byFactor: 3), the area of the instance will triple.
#### Hint: Add a setter to area.
```
// as usual instead of giving equation author is giving useless hint which everyone would think of that if they need to set seomthing 
// then they would need some sort of setter
// i will break down a little bit in comments 

struct Circle {
  var radius = 0.0
  var area: Double {
    get{
        .pi * radius * radius}
    set{ // here it gets newValue from grow function and because area property needs to recalculate new value 
         //from get we are doing this math to set radius, then get is doing its job with new radius value.
         // the most helpful/ hinty part was to get the equation but not that we must use "set in area"
        radius = (newValue / .pi).squareRoot()
    }
    }
    mutating func grow(byFactor:Double) { // for this function to be able to change properties of the instance it needs to be 
    // mutating function
        self.area *= byFactor  // by calling grow method area should be set to whatever it is * factor
    }
   
  init(radius: Double) {
    self.radius = radius
  }
}
```
### Challenge 2: A more advanced advance()
#### Here is a naïve way of writing advance() for the SimpleDate structure you saw earlier in the chapter:
```
let months = ["January", "February", "March",
             "April", "May", "June",
             "July", "August", "September",
             "October", "November", "December"]

struct SimpleDate {
 var month: String
 var day: Int

 mutating func advance() {
   day += 1
 }
}

var date = SimpleDate(month: "December", day: 31)
date.advance()
date.month // December; should be January!
date.day // 32; should be 1!
```
#### What happens when the function should go from the end of one month to the start of the next?
#### Rewrite advance() to account for advancing from December 31st to January 1st.
```
