### Challenge 1: Coordinates
#### Create a constant called coordinates and assign a tuple containing two and three to it.

```

let coordinates = (2,3)

```

### Challenge 2: Named coordinate
#### Create a constant called namedCoordinate with a row and column component.

```

let namedCoordinates = (row:5,columnt:5)

```

###Challenge 3: Which are valid?

```

let character: Character = "Dog" // Invalid
let character: Character = "🐶" // Valid
let string: String = "Dog" //Valid
let string: String = "🐶” //Valid

```

### Challenge 4. Does it compile? 

```

let tuple = (day: 15, month: 8, year: 2015)
let day = tuple.Day

// there is no member "Day" should be "day"
```

### Challenge 5: Find the error
####  What is wrong with the following code?

```

let name = "Matt"
name += " Galloway”
// name is a constant so cant be changed
```` 

### Challenge 6: What is the type of value?
#### What is the type of the constant named value?

```

let tuple = (100, 1.5, 10)
let value = tuple.1

// double
```

### Challenge 7: What is the value of month?
#### What is the value of the constant named month?

```

let tuple = (day: 15, month: 8, year: 2015)
let month = tuple.month
// Int
```

### Challenge 8: What is the value of summary?
#### What is the value of the constant named summary?

```

let number = 10
let multiplier = 5
let summary = "\(number) multiplied by \(multiplier) equals \(number * multiplier)"
//String

```

### Challenge 9: Compute the value
#### What is the sum of a and b, minus c?

```

let a = 4
let b: Int32 = 100
let c: UInt8 = 12

// Int32 and Int cant be added without casting first

```

### Challenge 10: Different precision 𝜋s
#### What is the numeric difference between Double.pi and Float.pi?

```
float has 6 digit precision after point
double has 15 digit precision after point

numeric difference = double - float


```
