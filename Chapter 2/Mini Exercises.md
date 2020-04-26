### Create a string constant called firstName and initialize it to your first name.
### Also create a string constant called lastName and initialize it to your last name.

```

let firstName = "Surepic"

let lastName = "Pluto"

```

### Create a string constant called fullName by adding the firstName and lastName constants together, separated by a space.

```

let firstName = "Surepic"

let lastName = "Pluto"

let fullName = firstName + " " + lastName

```

### Using interpolation, create a string constant called myDetails that uses the fullName constant to create a 
### string introducing yourself. For example, my string would read: "Hello, my name is Matt Galloway.".”

```

let firstName = "Surepic"

let lastName = "Pluto"

let fullName = firstName + " " + lastName

let myDetails = "Hello, my name is \(fullName)"


```

### Declare a constant tuple that contains three Int values followed by a Double. 
### Use this to represent a date (month, day, year) followed by an average temperature for that date.

```

let date:(Int,Int,Int,Double) = (5,22,1920,55)

```

### Change the tuple to name the constituent components. 
### Give them names related to the data that they contain: month, day, year and averageTemperature.”

```

let date:(Int,Int,Int,Double) = (day:5,month:22,year:1920,temp:55)

```

### In one line, read the day and average temperature values into two constants. You’ll need to employ the underscore to 
### ignore the month and year.

```

let (day,_,_,average) = date

```

### Up until now, you’ve only seen constant tuples. But you can create variable tuples, too. 
### Change the tuple you created in the exercises above to a variable by using var instead of let.
### Now change the average temperature to a new value.

```

let date:(Int,Int,Int,Double) = (day:5,month:22,year:1920,temp:55)

var (day,_,_,average) = date

average = 5.5

```

