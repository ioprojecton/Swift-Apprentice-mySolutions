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
let months = ["January", "February", "March",
              "April", "May", "June",
              "July", "August", "September",
              "October", "November", "December"]

struct SimpleDate {
    var month: String
    var day: Int {
        didSet {
            switch month {
            case "January":
                if day > 31 {
                    month = "February"
                    day = 1
                }
                
            case "February":
                if day > 28{ // dont have year to calculate leap
                    month = "March"
                    day = 1
                }
                
            case "March":
                if day > 31{
                    month = "April"
                    day = 1
                }
                
            case "April":
                if day > 30{
                    month = "May"
                    day = 1
                }
                
            case "May":
                if day > 31{
                    month = "June"
                    day = 1
                }
                
            case "June":
                if day > 30{
                    month = "July"
                    day = 1
                }
                
            case "July":
                if day > 31{
                    month = "August"
                    day = 1
                }
                
            case "August":
                if day > 31{
                    month = "September"
                    day = 1
                    
                }
                
            case "September":
                if day > 30{
                    month = "October"
                    day = 1
                }
                
            case "October":
                if day > 31{
                    month = "November"
                    day = 1
                }
                
            case "November":
                if day > 30{
                    month = "December"
                    day = 1
                }
                
            case "December":
                if day > 31{
                    month = "January"
                    day = 1
                }
            default:
                return
            }
        }
    }
    
    mutating func advance() {
        day += 1
    }
    
}
```
### Challenge 3: Odd and Even Math
#### Add type methods named isEven and isOdd to your Math namespace that return true if a number is even or odd respectively.
```
struct Math {
    //empty
}

extension Math {
   static func isEven(number: Int) -> Bool {
    number % 2 == 0
  }
   static func isOdd(number: Int) -> Bool {
    number % 2 != 0
  }
}
```

### Challenge 4: Odd and Even Int
#### It turns out that Int is simply a struct.
#### Add the computed properties isEven and isOdd to Int using an extension.
```
extension Int{
    var isEven: Bool{
        self % 2 == 0 ? false : true
    }
    var isOdd: Bool{
        self % 2 != 0 ? false : true
    }
}
```
### Challenge 5: Prime Factors
#### Add the method primeFactors() to Int.
#### Since this is an expensive operation, this is best left as an actual method.
```
//solution was provided in in chapter 12 on page 473 
// so just copying and pasting primefactor function to extension to Int
extension Int{
     func primeFactors() -> [Int] { // no need to take any arguments
        // 1
        var remainingValue = self // changed from value to self cos there is no variable named value is here it just refers to self
        // 2
        var testFactor = 2
        var primes: [Int] = []
        // 3
        while testFactor * testFactor <= remainingValue {
            if remainingValue % testFactor == 0 {
                primes.append(testFactor)
                remainingValue /= testFactor
            }
            else {
                testFactor += 1
            }
        }
        if remainingValue > 1 {
            primes.append(remainingValue)
        }
        return primes
    }
}
```
