#### Create a constant called myAge and set it to your age. 
#### Then, create a constant named isTeenager that uses Boolean logic to determine 
#### if the age denotes someone in the age range of 13 to 19.”

```

let myAge = 20

let isTeenager = myAge > 13 || myAge < 19

```

#### Create another constant named theirAge and set it to my age, which is 30.
#### Then, create a constant named bothTeenagers that uses Boolean logic to determine if both you and I are teenagers.

```

let myAge = 20

let isTeenager = myAge > 13 || myAge < 19

let theirAge = 30

let bothTeenagers = isTeenager || (theirAge > 13 && theirAge < 19)

```

#### Create a constant named reader and set it to your name as a string. 
#### Create a constant named author and set it to my name, Matt Galloway. 
#### Create a constant named authorIsReader that uses string equality to determine if reader and author are equal.

```

let reader = "Surepic"

let author = "Matt Galloway"

let authorIsReader = reader == author

```

#### Create a constant named readerBeforeAuthor which uses string comparison to determine if reader comes before author.

````

let reader = "Surepic"

let author = "Matt Galoway"

let authorIsReader = reader == author

let readerBeforeAuthor = reader > author ? author : reader

````

#### Create a constant named myAge and initialize it with your age. 
#### Write an if statement to print out Teenager if your age is between 13 and 19, 
#### and Not a teenager if your age is not between 13 and 19.

```

let myAge = 20

if myAge > 13 && myAge < 19 {
    print("Teenager")
}
else {
    print("Not Teenager")
}

```


#### Create a constant named answer and use a ternary condition to set it equal to the result you print out for the same cases in the above exercise. 
#### Then print out answer.
 
 ```
let myAge = 10

let answer = myAge > 13 && myAge < 19 ? "Teenager" : "Not Teenager"

print(answer)

 ```
 
