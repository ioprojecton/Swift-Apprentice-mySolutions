### Challenge 1: Character count
#### Write a function that takes a string and prints out the count of each character in the string.
#### For bonus points, print them ordered by the count of each character.
#### For bonus-bonus points, print it as a nice histogram.
#### Hint: You could use # characters to draw the bars.
```
func countChars (str:String){
    guard !str.isEmpty else {
        return
    }
    
    var dict:[Character: Int] = [:]
    
    for chars in str {
        if let _ = dict[chars]{
            dict[chars]! += 1
        }
        else {dict[chars] = 1}
    }
    
    for (key,value) in dict{
        if key.isLetter {
            print(key, value)}
    }
}
```
### Challenge 2: Word count
#### Write a function that tells you how many words there are in a string. 
#### Do it without splitting the string.
#### Hint: try iterating through the string yourself.”
```
func numberOfWords(in sentence: String) -> Int {
    var count = 0
    
    var word = false
    
    for value in sentence{
        if value.isWhitespace || value.isPunctuation{
            if word {
                count += 1
            }
                word = false
        }
        else {
            word = true
        }
    }
    
    if word{
        count += 1
    }
    return count
}
```
### Challenge 3: Name formatter
#### Write a function that takes a string which looks like "Galloway, Matt" and returns one which looks like "Matt Galloway"
#### , i.e., the string goes from "<LAST_NAME>, <FIRST_NAME>" to "<FIRST_NAME> <LAST_NAME>".”
```
func inswap(in sentence: String) -> String {
    guard sentence.contains(",") else {
        return ""
    }
    
    var newStr = sentence
    var firstName = ""
    var lastName = ""
    
    for counter in newStr{
        if counter == "," {break}
        lastName.append(newStr.remove(at: newStr.startIndex))
    }
    
    for counter in newStr{
        if counter == " " || counter == ","{continue}
        firstName.append(counter)
    }
    
    
    return firstName + " " + lastName
}
```
### Challenge 4: Components
#### A method exists on a string named components(separatedBy:) that will split the string into chunks,
#### which are delimited by the given string, and return an array containing the results.
#### Your challenge is to implement this yourself.
#### Hint: There exists a view on String named indices that lets you iterate through all the indices (of type String.Index) in the string.
#### You will need to use this.
```
// if function already exists no need to waste time and reinvent the wheel just use 
// let myArray = name_of_your_string.components(separatedBy: ",")

func separate (str:String, delimiter:Character) -> [String] {
    
    guard str.contains(delimiter) else {
        return []
    }
    
    var newArray = [String]()
    
    var firstIndex = str.startIndex
    
    for chars in str.indices{
        if str[chars] == delimiter{
            let substring = str[firstIndex..<chars]
            newArray.append(String(substring))
            firstIndex = str.index(after: chars)
        }
    }
    let substring = str[firstIndex..<str.endIndex]
    newArray.append(String(substring))
    
    return newArray
}
```
### Challenge 5: Word reverser
#### Write a function which takes a string and returns a version of it with each individual word reversed.
#### For example, if the string is “My dog is called Rover” then the resulting string would be "yM god si dellac revoR".
#### Try to do it by iterating through the indices of the string until you find a space, and then reversing what was before it.
#### Build up the result string by continually doing that as you iterate through the string.
#### Hint: You’ll need to do a similar thing as you did for Challenge 4 but reverse the word each time.
#### Try to explain to yourself, or the closest unsuspecting family member,
#### why this is better in terms of memory usage than using the function you created in the previous challenge.
```
//better to use built in methods and functions then to waste time reinventing same thing
//its better in terms of memory usage because its included standard library
func rev(_ myStr:String) -> String{

guard !myStr.isEmpty else {return ""}

var newArray = myStr.components(separatedBy: " ")

var myStr2 = ""

for (index,value) in newArray.enumerated(){
    myStr2.append(String(value.reversed()))
    if index < newArray.endIndex - 1 {myStr2.append(" ")}
}
}
```

