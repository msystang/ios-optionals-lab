# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

- Method two: Optional binding

- Method three: Nil coalescing

Answer:
```swift
var userName: String?
//- Method one: Check for nil and force unwrap

if userName != nil {
print(userName!)
} else {
print("No name")
}

//- Method two: Optional binding

if let userNameUnwrapped = userName {
print(userNameUnwrapped)
} else {
print("No name")
}

//- Method three: Nil coalescing
print(userName ?? "No name")

```

## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

Answer:
```swift
var backgroundColor: String?

if let backgroundColorUnwrapped = backgroundColor {
print(backgroundColorUnwrapped)
} else {
backgroundColor = "Yellow"
print(backgroundColor!)
}
```


## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?
```
Answer:
```swift
var width: Double?
var height: Double?

if let widthUnwrapped = width,
let heightUnwrapped = height {
let area = widthUnwrapped*heightUnwrapped
print(area)
} else {
print("There is an error.")
}

```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?
```
Answer:
```swift
var name: String?
var age: Int?
var height: Double?

if let nameUnwrapped = name,
let ageUnwrapped = age,
let heightUnwrapped = height {
print("\(nameUnwrapped) is \(ageUnwrapped) years old and is \(heightUnwrapped) tall.")
} else {
print("There is an error.")
}

```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
```
Answer:
```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

if let middleNameUnwrapped = middleName {
print("\(firstName) \(middleNameUnwrapped) \(lastName)")
} else {
print("\(firstName) \(lastName)")
}

```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

Answer:
```swift
let myIntString = "35"

if let myIntStringUnwrapped = Int(myIntString) {
print(myIntStringUnwrapped + 15)
}
```


## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)
```

Answer:
```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)?  = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)?  = (5, 10, 24)

var testCases = [testCaseOne, testCaseTwo, testCaseThree]

for testCase in testCases {
var sum = 0

if let testCaseUnwrapped = testCase {

if let num1 = testCaseUnwrapped.0 {
sum += num1
}

if let num2 = testCaseUnwrapped.1 {
sum += num2
}

if let num3 = testCaseUnwrapped.2 {
sum += num3
print(sum)
}
}
}
```



## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```

Answer:
```swift
var tuple: (Int, Int)?
if Bool.random() {
tuple = (5, 3)
}

if let tupleUnwrapped = tuple {
print(tupleUnwrapped)
}
```



## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}
```

Answer:
```swift
let myInt: Int?
if Bool.random() {
myInt = 5
if let myIntUnwrapped = myInt {
print(myIntUnwrapped*2)
}
} else {
print("There is an error.")
}
```



## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}
```

Answer:
```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
myDouble = 12
if let myDoubleUnwrapped = myDouble {
print(myDoubleUnwrapped * doubleTwo)
}
} else {
print("There is an error.")
}
```



## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```

Answer:
```swift
var isTheGreatest: Bool?

if Bool.random() {
isTheGreatest = true
if let isTheGreatestUnwrapped = isTheGreatest {
print(isTheGreatestUnwrapped)
}
} else {
isTheGreatest = false
if let isTheGreatestUnwrapped = isTheGreatest {
print(isTheGreatestUnwrapped)
}
}
```



## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
```

Answer:
```swift

var sum = 0

if Bool.random() {
myTuple.0 = 5
myTuple.2 = 14
} else {
myTuple.1 = 9
myTuple.3 = 10
}

if let myTupleUnwrapped0 = myTuple.0 {
sum += myTupleUnwrapped0
}

if let myTupleUnwrapped1 = myTuple.1 {
sum += myTupleUnwrapped1
}

if let myTupleUnwrapped2 = myTuple.2 {
sum += myTupleUnwrapped2
}

if let myTupleUnwrapped3 = myTuple.3 {
sum += myTupleUnwrapped3
}

print(sum)
```



## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
```

Answer:
```swift
func eStone() -> String {
let random = Int(arc4random_uniform(5))
switch random {
case 0:
return "Electric"
case 1:
return "Grass"
case 2:
return "Fire"
case 3:
return "Water"
default:
return "No Stone"
}
}

func starterPokemon() -> String {
let random = Int(arc4random_uniform(5))
switch random {
case 0:
return "Pikachu"
case 1:
return "Bulbasaur"
case 2:
return "Charmander"
case 3:
return "Squirtle"
default:
return "Not a Pokemon"
}
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

if let pokemonUnwrapped = pokemon,
let evolutionaryStoneUnwrapped = evolutionaryStone {
if pokemonUnwrapped == "Pikachu" && evolutionaryStoneUnwrapped == "Electric" {
print("Your \(pokemonUnwrapped) is evolving!")
} else if pokemonUnwrapped == "Bulbasaur" && evolutionaryStoneUnwrapped == "Grass" {
print("Your \(pokemonUnwrapped) is evolving!")
} else if pokemonUnwrapped == "Charmander" && evolutionaryStoneUnwrapped == "Fire" {
print("Your \(pokemonUnwrapped) is evolving!")
} else if pokemonUnwrapped == "Squirtle" && evolutionaryStoneUnwrapped == "Water" {
print("Your \(pokemonUnwrapped) is evolving!")
} else {
print("No evolution.")
}
}
```



## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```

Answer:
```swift
var numberOfPeople: Int?

if Bool.random() {
numberOfPeople = 108
if let numberOfPeopleUnwrapped = numberOfPeople {
if numberOfPeopleUnwrapped % 2 == 0 {
print(numberOfPeopleUnwrapped)
}
}
}
```



## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```

Answer:
```swift
var someNumbers: [Int?] = []
var newArray: [Int] = []
var product = 1

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}

for int in someNumbers {
if let intUnwrapped = int {
newArray.append(intUnwrapped)
}
}

for int in newArray {
product *= int
}
print(product)
```



## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```

Answer:
```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]
var cityNamesOnly = [String]()
var cityNamesLowercased = [String]()
var cityNamesCapitalized = [String]()


for city in poorlyFormattedCityNames {
if let cityUnwrapped = city {
cityNamesOnly.append(cityUnwrapped)
}
}

for city in cityNamesOnly {
cityNamesLowercased.append(city.lowercased())
}
//print(cityNamesLowercased)

for city in cityNamesLowercased {
cityNamesCapitalized.append(city.capitalized)
}
print(cityNamesCapitalized)
```



## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```

Answer:
```swift
var aBunchOfNumbers: [Int?] = []
var evenNumbers: [Int] = []

for _ in 0..<20 {
aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}

for number in aBunchOfNumbers {
if let numberUnwrapped = number {
if numberUnwrapped % 2 == 0 {
evenNumbers.append(numberUnwrapped)
}
}
}
print(evenNumbers)
```



## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

Answer:
```swift
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var zipIntArray = [Int]()

for zip in zipCodeStrings {
if let zipIntUnwrapped = Int(zip) {
zipIntArray.append(zipIntUnwrapped)
}
}
print(zipIntArray
```



## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`


Answer:
```swift
//- Print the names of the students that do not have a favorite color.
for tuple in studentInfo {
if tuple.2 == nil {
print(tuple.0)
}
}

//- Print the names of the students that don't have a favorite color or a favorite food.
for tuple in studentInfo {
if tuple.2 == nil || tuple.1 == nil {
print(tuple.0)
}
}

//- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.
var newArray2: [(String, String, String)] = []

for tuple in studentInfo {
if let food = tuple.1,
let color = tuple.2 {
let newTuple = (tuple.0, food, color)
newArray2.append(newTuple)
}
}
print(newArray2)

```


## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


Answer:
```swift
let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]

//- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

var colorsArray: [(UInt8, UInt8, UInt8)] = []

if let possibleColorsUnwrapped = possibleColors {
for rgb in possibleColorsUnwrapped {
if let rgbUnwrapped = rgb {
if let rUnwrapped = rgbUnwrapped.r,
let gUnwrapped = rgbUnwrapped.g,
let bUnwrapped = rgbUnwrapped.b {
let newTuple = (rUnwrapped,gUnwrapped,bUnwrapped)
colorsArray.append(newTuple)
}
}
}
}
print(colorsArray)

//- Write code that counts all the nil values.

var colorsArray: [(UInt8, UInt8, UInt8)] = []
var nilCounter = 0

if let possibleColorsUnwrapped = possibleColors {
for rgb in possibleColorsUnwrapped {
if let rgbUnwrapped = rgb
{
if let rUnwrapped = rgbUnwrapped.r,
let gUnwrapped = rgbUnwrapped.g,
let bUnwrapped = rgbUnwrapped.b
{
let newTuple = (rUnwrapped,gUnwrapped,bUnwrapped)
colorsArray.append(newTuple)
}
if rgbUnwrapped.r == nil {
nilCounter += 1
}
if rgbUnwrapped.g == nil {
nilCounter += 1
}
if rgbUnwrapped.b == nil {
nilCounter += 1
}
} else {
nilCounter += 1
}
} 
}
print(nilCounter)


```


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`


Answer:
```swift
let number: Int??? = 10

if let numberUnwrapped = number {
if let numberUnwrapped2 = numberUnwrapped {
if let numberUnwrapped3 = numberUnwrapped2 {
print(numberUnwrapped3)
}
}
}
```


## Question 22***

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


Answer: (Prints out orangutan twice instead of orangutan and gorrillas.)
```swift
let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]
var vowelCount = 0

for string in monkeyingAround {
if let stringUnwrapped = string {
for character in stringUnwrapped {
if character == "a" || character == "e" || character == "i" || character == "o" || character == "u" {
vowelCount += 1
if vowelCount < 3 {
print(stringUnwrapped)
}
}
}
}
}
```


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`


Answer:
```swift
var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)

//member0
if let member0 = strangeStructure?.0 {
for int in member0 {
print(int)
}
}

//member1
if let member1 = strangeStructure?.1 {
for array in member1 {
for int in array {
if let intUnwrapped = int {
print(intUnwrapped)
}
}
}
}

//member2
if let member2 = strangeStructure?.2 {
for array in member2 {
if let arrayUnwrapped = array {
for int in arrayUnwrapped {
print(int)
}
}
}
}

//member3
if let member3 = strangeStructure?.3 {
print(member3)
}

```

