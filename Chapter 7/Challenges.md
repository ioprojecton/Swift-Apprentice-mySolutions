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
