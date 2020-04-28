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
4. dict4[1]
5. dict4["One"]
6. dict4["Zero"] = 0
7. dict4[0] = "Zero
```
#### For the next three statements, use the following dictionary:
```
var dict5 = ["NY": "New York", "CA": "California"]
8. dict5["NY"]
9. dict5["WA"] = "Washington"
10. dict5["CA"] = nil
```
