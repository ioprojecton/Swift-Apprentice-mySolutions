### Challenge 1: Ice Cream
#### Rewrite the IceCream structure below to use default values and lazy initialization:
```
struct IceCream {
  let name: String
  let ingredients: [String]
}
```
Use default values for the properties.
Lazily initialize the ingredients array.
```
struct IceCream {
  var name: String = "Perl"
    lazy var ingredients: [String] = {
        ["Milk","Sugar","Stick"]
        }()
}
```

### Challenge 2: Car and Fuel Tank
#### At the beginning of the chapter, you saw a Car structure.
#### Dive into the inner workings of the car and rewrite the FuelTank structure below with property observer functionality:
```
struct FuelTank {
  var level: Double // decimal percentage between 0 and 1
}
```
#### Add a lowFuel stored property of Boolean type to the structure.
#### Flip the lowFuel Boolean when the level drops below 10%.
#### Ensure that when the tank fills back up, the lowFuel warning will turn off.
#### Set the level to a minimum of 0 or a maximum of 1 if it gets set above or below the expected values.
#### Add a FuelTank property to Car.
```
// very idiotic task
struct FuelTank {

  var lowFuel: Bool
  var level: Double { // decimal percentage between 0 and 1
    didSet {
      if level < 0 {
        level = 0
      }
      if level > 1 {
        level = 1
      }
      lowFuel = level < 0.1
    }
  }
}

struct Car {
  let make: String
  let color: String
  var tank: FuelTank
}
```
