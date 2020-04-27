#### Make an optional String called myFavoriteSong.
#### If you have a favorite song, set it to a string representing that song.
#### If you have more than one favorite song or no favorite, set the optional to nil.
```
var myFavSong:String?
```

#### Create a constant called parsedInt and set it equal to Int("10") which tries to parse the string 10 and
#### convert it to an Int. Check the type of parsedInt using Option-Click. Why is it an optional?
```
var parsedInt = Int("10")
// parsedInt is optional because there is chance that Int casting of String may return nil i.e. Int("kkk") cant be parsed
```

#### Change the string being parsed in the above exercise to a non-integer (try dog for example).
#### What does parsedInt equal now?”
```
var parsedInt = Int("10")
// parsedInt is nil
```

#### Using your myFavoriteSong variable from earlier, use optional binding to check if it contains a value.
#### If it does, print out the value. If it doesn’t, print "I don’t have a favorite song."
```
var myFavSong:String?

if let song = myFavSong {
    print(song)
}
else {print("I don’t have a favorite song.")}
```

#### Change myFavoriteSong to the opposite of what it is now.
#### If it’s nil, set it to a string; if it’s a string, set it to nil. 
#### Observe how your printed result changes.
```
var myFavSong:String? = "Happy birthday to you"

if let song = myFavSong {
    print(song)
}
else {print("I don’t have a favorite song.")}
```
