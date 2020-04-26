### Challenge 1: Find the error
#### What’s wrong with the following code?

```
let firstName = "Matt"

if firstName == "Matt" {
  let lastName = "Galloway"
} else if firstName == "Ray" {
  let lastName = "Wenderlich"
}
let fullName = firstName + " " + lastName”

//lastName is out of scope of fullName
```

### Challenge 2: Boolean challenge
#### In each of the following statements, what is the value of the Boolean answer constant?
```
let answer = true && true //true
let answer = false || false // false
let answer = (true && 1 != 2) || (4 > 3 && 100 < 1) //true
let answer = ((10 / 2) > 3) && ((10 % 2) == 0) // true

```

### Challenge 3: Snakes and ladders
#### Imagine you’re playing a game of snakes & ladders that goes from position 1 to position 20. 
#### On it, there are ladders at position 3 and 7 which take you to 15 and 12 respectively. 
#### Then there are snakes at positions 11 and 17 which take you to 2 and 9 respectively.
#### Create a constant called currentPosition which you can set to whatever position between 1 and 20 which you like.
#### Then create a constant called diceRoll which you can set to whatever roll of the dice you want. 
#### Finally, calculate the final position taking into account the ladders and snakes, calling it nextPosition.

```
let currentPosition = Int.random(in: 1...20)

let diceRoll = Int.random(in: 1...6)

var finalPosition = currentPosition + diceRoll


if finalPosition == 3 {
    finalPosition = 15
}

else if finalPosition == 7 {
    finalPosition == 12
}

else if finalPosition == 11 {
    finalPosition = 2
}

else if finalPosition == 17 {
    finalPosition = 9
}

```

### Challenge 4: Number of days in a month
#### Given a month (represented with a String in all lowercase) and the current year (represented with an Int), 
#### calculate the number of days in the month. Remember that because of leap years, "february" has 29 days when the year 
#### is a multiple of 4 but not a multiple of 100. February also has 29 days when the year is a multiple of 400.

```
let month = "May"

let year = 1980

let daysInMonth:Int

if month == "Jan" || month == "Mar" || month == "May" || month == "Jul" || month == "Aug" || month == "Oct" || month == "Dec"{
    daysInMonth = 31
}
else if month == "Feb" {
    if (year % 4 == 0 && year % 100 != 0) || year % 400 == 0 {
        daysInMonth = 29
    }
        
    else {
        daysInMonth = 28
    }
}
    
else {
    daysInMonth = 30
}
```

### Challenge 5: Next power of two
#### Given a number, determine the next power of two above or equal to that number.

```
// Very redundant discription of the problem!
// Easy explanation :
// Given a number, determine how many times it is in term of 2 to the power of given number, 
// if its not equal find closest power of 2 to the given number in upper range

let number = 8

var counter = 1

while counter < number {
    counter *= 2 // or just counter <<= 1
}

```

### Challenge 6: Triangular number
#### Given a number, print the triangular number of that depth.
#### You can get a refresher of triangular numbers here: https://en.wikipedia.org/wiki/Triangular_number

```
//Another one which has nothing to do with the subject ... this is not a applied math lecture!

var z = 5

var counter = 1

var number = 0

while count <= z {
  number += counter
  counter += 1
}

```

### Challenge 7: Fibonacci
#### Calculate the n’th Fibonacci number. 
#### Remember that Fibonacci numbers start its sequence with 1 and 1, and then 
#### subsequent numbers in the sequence are equal to the previous two values added together. 
#### You can get a refresher here: https://en.wikipedia.org/wiki/Fibonacci_number

```
let fibonacci = 8
let fib:Double = (1 + sqrt(5)) / 2

let answer = Int(pow(fib, Double(fibonacci)) / sqrt(5))

```

### Challenge 8: Make a loop
#### Use a loop to print out the times table up to 12 of a given factor.

```
// Or in simple words make a time table of number with limit of up to 12

let number = 7

let limit = 12

var counter = 0

while counter <= limit {
    print("\(counter) * \(number) = \(counter * number)")
    counter += 1
}

```

### Challenge 9: Dice roll table
#### Print a table showing the number of combinations to create each number 
#### from 2 to 12 given 2 six-sided dice rolls. 
#### You should not use a formula but rather compute the number of combinations exhaustively
#### by considering each possible dice roll.

```
var from = 5

var to = 12

var found = 0

while from <= to {
var found = 0
var dice = 1
while dice <= 6 {
var secondDice = 1
while secondDice <= 6 {
if dice + secondDice == from {
 found += 1
 }
 secondDice += 1
 }
 dice += 1
 }

 print("\(from) (found)")

 from += 1
}

```
