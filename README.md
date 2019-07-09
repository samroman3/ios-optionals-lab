# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1 - done

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap
```
var userName: String?
if userName != nil {
print(userName)
} else {
print("No name")
}
```


- Method two: Optional binding
```
var userName: String?
if let realName = userName {
print(realName) {
else {
print("No name")
}
}
}
```
- Method three: Nil coalescing
```
var userName: String?
var unwrappedName = userName ?? "samroman3"

print(unwrappedName)
```


## Question 2 - done

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

***
```
var backgroundColor: String?`

if let unwrappedColor = backgroundColor ?? "grey"

print(unwrappedColor)
```

## Question 3- done

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double? = 3.2
var height: Double? = 4.0

var area = width! * height!

```


## Question 4 - done

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String? = "sam"
var age: Int? = 24
var height: Double? = 5.11
if let unwrappedName = name,
let unwrappedAge = age,
let unwrappedHeight = height {
print("\(unwrappedName) + \(unwrappedAge) + \(unwrappedHeight)")
} else {
print("error")
}
```


## Question 5 - done

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String? = "Alex"
var lastName: String = "Stone"

if firstName != nil, middleName != nil, lastName != nil{
var fullName = "\(firstName) \(middleName!) \(lastName)"
print(fullName) } 

```



## Question 6 - done

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.
***
```
let myIntString = "35"

if let integerString = Int(myIntString) {
print(integerString + 15)
}
```
## Question 7 - done

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?
var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)


func unwrapTuple (tuple: (Int?, Int?, Int?)?) {

if let safeTuple = tuple {

let testCase1 = safeTuple.0 ?? 0
let testCase2 = safeTuple.1 ?? 0
let testCase3 = safeTuple.2 ?? 0

let tupleSum = testCase1 + testCase2 + testCase3

print(tupleSum)
}
}

unwrapTuple(tuple: testCaseTwo)
unwrapTuple(tuple: testCaseThree)
unwrapTuple(tuple: testCaseOne)
unwrapTuple(tuple: scores)
```


## Question 8 - done

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
tuple = (5, 3)
}

if let tuple = tuple {
print(tuple)
}

```


## Question 9 - done

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}

if let myInt = myInt {
print(myInt * 2)
} else {
print("error")
}

```


## Question 10 - done

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double? 
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}

if let myDouble = myDouble {
print(myDouble * doubleTwo)
} else {
print("error")
}

```


## Question 11 - done

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}

if isTheGreatest == nil {
isTheGreatest = false
} else {
isTheGreatest = true
}
```


## Question 12 done

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
 var myTuple: (Int?, Int?, Int?, Int?)
 
if Bool.random() {
myTuple.0 = 5
myTuple.2 = 14
let sum = Int(myTuple.0 ?? 0) + Int(myTuple.2 ?? 0 )
print("bool is true, sum is \(sum)")
} else {
myTuple.1 = 9
myTuple.3 = 10
let sum = Int(myTuple.1 ?? 0) + Int(myTuple.3 ?? 0)
print("bool is false, sum is \(sum)")
}
```


## Question 13 todo

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


## Question 14 - done

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}

if let numberOfPeople = numberOfPeople {
if numberOfPeople % 2 == 0 {
print(numberOfPeople)
}
}
```


## Question 15 done

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []
var safeNumbers = [Int]()

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}
for i in someNumbers {
guard let safeNumber = i else {continue}
safeNumbers.append(safeNumber)
}
print(safeNumbers)
print(safeNumbers.reduce(1,*))
```


## Question 16 -done

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]
//Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
var cityNames = [String]()

for city in poorlyFormattedCityNames {
guard let safeCity = city else {continue}
cityNames.append(safeCity.capitalized)
}
print(cityNames)
```


## Question 17-done

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
var newArray = []
for i in aBunchOfNumbers {
if i != nil && i % 2 ==0 {
newArray.append(i)

}
}
```


## Question 18 done

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

```
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]

let zipCodeInt = zipCodeStrings.map { Int($0) ?? 0 }
print(zipCodeInt)

```

## Question 19 todo

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`


## Question 20 - todo 

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


## Question 21 done
Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.
```
let number: Int??? = 10

if let number = number{
if let number1 = number{
if let number2 = number1{
print(number2)
}
}
}
//
```

## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`

for i in monkeyingAround {
if let i = 
}
## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`


