### Challenge 1: Which is valid
#### Which of the following are valid statements?
```
1. let array1 = [Int]() //valid
2. let array2 = [] // invalid
3. let array3: [String] = [] // valid
```
#### For the next five statements, array4 has been declared as:
```
let array4 = [1, 2, 3]
4. print(array4[0]) // valid 
5. print(array4[5]) // invalid
6. array4[1...2] // valid
7. array4[0] = 4 // invalid
8. array4.append(4) // invalid
```
#### For the final five statements, array5 has been declared as:
```
var array5 = [1, 2, 3]
9. array5[0] = array5[1] // valid
10. array5[0...1] = [4, 5] // valid
11. array5[0] = "Six" // invalid
12. array5 += 6 // invalid
13. for item in array5 { print(item) } // valid
```

### Challenge 2: Remove the first number
#### Write a function that removes the first occurrence of a given integer from an array of integers. 
### This is the signature of the function:
```
func removingOnce(_ item: Int, from array: [Int]) -> [Int]
```
```
func removingOnce(_ item: Int, from array: [Int]) -> [Int] {
    guard !array.isEmpty else {
        return []
    }
    
    var newArray = array
    
    if let index = newArray.firstIndex(of: item){
        newArray.remove(at: index)
    }    
    return newArray
}
```

### Challenge 3: Remove the numbers
#### Write a function that removes all occurrences of a given integer from an array of integers.
#### This is the signature of the function:
```
func removing(_ item: Int, from array: [Int]) -> [Int]
```
```
func removing(_ item: Int, from array: [Int]) -> [Int]{
    
    guard !array.isEmpty else {
        return array
    }
    
    var newArray = array
    
    for value in newArray{
        if value == item {
            newArray.remove(at: newArray.firstIndex(of: item)!)
        }
    }
    return newArray
}
```

### Challenge 4: Reverse an array
#### Arrays have a reversed() method that returns an array holding the same elements as the original array, in reverse order.
#### Write a function that does the same thing, without using reversed(). This is the signature of the function:
```
func reversed(_ array: [Int]) -> [Int]
```
```
func reversed(_ array: [Int]) -> [Int]{

var newArray:[Int] = []

var counter = array.endIndex - 1

for _ in array{
    newArray.append(array[counter])
    counter -= 1
}

return newArray
    
}
```

### Challenge 5: Return the middle
#### Write a function that returns the middle element of an array.
#### When array size is even, return the first of the two middle elememnts.
```
func middle(_ array: [Int]) -> Int?
```
```
func middle(_ array: [Int]) -> Int? {
    array[array.count / 2]
}
```

### Challenge 6: Find the minimum and maximum
#### Write a function that calculates the minimum and maximum value in an array of integers.
#### Calculate these values yourself; don’t use the methods min and max.
#### Return nil if the given array is empty.
#### This is the signature of the function:
```
func minMax(of numbers: [Int]) -> (min: Int, max: Int)?
```
```
func minMax(of numbers: [Int]) -> (min: Int, max: Int)? {
    guard !numbers.isEmpty else {
        return nil
    }
    
    var min = numbers[0]
    var max = numbers[0]
    
    for value in numbers{
        if value > max {
            max = value
        }
        if value < min {
            min = value
        }
    }
    return (min,max)
}
```

### Challenge 7: Which is valid
#### Which of the following are valid statements?
```
1. let dict1: [Int, Int] = [:] //invalid
2. let dict2 = [:] //invalid
3. let dict3: [Int: Int] = [:] //valid
```
#### For the next four statements, use the following dictionary:
```
let dict4 = ["One": 1, "Two": 2, "Three": 3]
4. dict4[1] // invalid
5. dict4["One"] // valid
6. dict4["Zero"] = 0 // invalid
7. dict4[0] = "Zero" // invalid
```
#### For the next three statements, use the following dictionary:
```
var dict5 = ["NY": "New York", "CA": "California"]
8. dict5["NY"] // valid
9. dict5["WA"] = "Washington" // valid
10. dict5["CA"] = nil // valid
```

### Challenge 8: Long names
#### Given a dictionary with two-letter state codes as keys, and the full state names as values, 
#### write a function that prints all the states with names longer than eight characters. 
#### For example, for the dictionary ["NY": "New York", "CA": "California"], the output would be California.
```
func printStates (dictionary:[String:String]) {
    for (_,value) in dictionary{
        if value.count > 8 {
            print(value)
        }
    }
}
```

### Challenge 9: Merge dictionaries
#### Write a function that combines two dictionaries into one. 
#### If a certain key appears in both dictionaries, ignore the pair from the first dictionary.
#### This is the function’s signature:
```
func merging(_ dict1: [String: String], with dict2: [String: String]) -> [String: String]
```
func merging(_ dict1: [String: String], with dict2: [String: String]) -> [String: String] {
    guard !dict1.isEmpty && !dict2.isEmpty else{
        return [:]
    }  
    var newDict = dict1
    
    for(key,value) in dict2{
        newDict[key] = value
    }
    return newDict
}

### Challenge 10: Count the characters
#### Declare a function occurrencesOfCharacters that calculates which characters occur in a string,
#### as well as how often each of these characters occur. Return the result as a dictionary. This is the function signature:
```
func occurrencesOfCharacters(in text: String) -> [Character: Int]
```
#### Hint: String is a collection of characters that you can iterate over with a for statement.
#### Bonus: To make your code shorter, dictionaries have a special subscript operator that let you add a default
#### value if it is not found in the dictionary.
#### For example, dictionary["a", default: 0] creates a 0 entry for the character "a" if it is not found instead of just returning nil.
```
func occurrencesOfCharacters(in text: String) -> [Character: Int]{
    guard !text.isEmpty else {
        return [:]
    }
    var newDict: [Character:Int] = [:]   
    for characters in text{
        if let x = newDict[characters]{
            newDict[characters] = x+1
            continue
        }
        newDict[characters] = 1
    }
    return newDict
}
```

### Challenge 11: Unique values
#### Write a function that returns true if all of the values of a dictionary are unique.
#### Use a set to test uniqueness. This is the function signature:
```
func isInvertible(_ dictionary: [String: Int]) -> Bool
```
```
func isInvertible(_ dictionary: [String: Int]) -> Bool{
    guard !dictionary.isEmpty else{
        return false
    }
    var newSet = Set<Int>()
    
    for (_,values) in dictionary{
        if newSet.contains(values){
            return false
        }
        else {
            newSet.insert(values)
        }
    }
    return true
}
```
### Challenge 12: Removing keys and setting values to nil
#### Given the dictionary:
```
var nameTitleLookup: [String: String?] = ["Mary": "Engineer", "Patrick": "Intern", "Ray": "Hacker"]
```
### Set the value of the key "Patrick" to nil and completely remove the key and value for "Ray".”
```
nameTitleLookup["Ray"] = nil
nameTitleLookup.updateValue(nil, forKey: "Patrick")
```
