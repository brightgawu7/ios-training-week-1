# The Basics

Swift is a type-safe language which means the language helps you to be clear about the types for values your code is working with.

## Constants and Variables

The value of a constant cannot be changed ones it is set, but the value of a variable can be set to a different values in the future.

# The Basics

Swift is a type-safe language which means the language helps you to be clear about the types for values your code is working with.

## Constants and Variables

The value of a constant cannot be changed ones it is set, but the value of a variable can be set to a different values in the future.

# The Basics

Swift is a type-safe language which means the language helps you to be clear about the types for values your code is working with.

## Constants and Variables

The value of a constant cannot be changed ones it is set, but the value of a variable can be set to a different values in the future.

```swift
let maximumNumberOfLoginAttempts = 10 // constant
var currentLoginAttempt = 0 // variable
var z=2, b=3, c=9.2;

```

## Type Annotations

You can provide a type annotation when you declare a constant or variable, to be clear about the kind of values the constant or variable can store.

```swift
let name:String
var age:Int

var a,b,c:Double;
```

## Printing Constants and Variables

```swift
let name = "Bright Edem";
var age = 21;

print(name)
print(age)
print(name,age)
print(name,age,separator:"=>", terminator:"/")
print("\n")
print("My name is \(name) and I am \(age) years old")
```

## Comments

```swift
// This is a comment.

/* This is also a comment
but is written over multiple lines. */
```

## Numeric Literals

```swift
let decimalInteger = 17
let binaryInteger = 0b01011
let octalInteger = 0o21
let hexadecimalInteget = 0x121;

```

## Numeric Type Conversion

### Integer Conversion

```swift
let cannotBeNegative: UInt8 = -1
// UInt8 can't store negative numbers, and so this will report an error
let tooBig: Int8 = Int8.max + 1
// Int8 can't store a number larger than its maximum value,
// and so this will also report an error
```

```swift
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```

### Integer and Floating-Point Conversion

```swift
let three = 3
let pointOneFourOneFiveNine = 0.14159

let pi = Double(three) + pointOneFourOneFiveNine


let integerPi = Int(pi)
// integerPi equals 3, and is inferred to be of type Int
```

## Type Aliases

```swift

typealis AgeType = Int32
let age: AgeType = 22

```

## Booleans

```swift
let orangesAreOrange = true
let turnipsAreDelicious = false
```

## Tuples

```swift

let http404Error = (404,"Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")

let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// Prints "The status code is 404"
print("The status message is \(statusMessage)")
// Prints "The status message is Not Found"


let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// Prints "The status code is 404"

print("The status code is \(http404Error.0)")
// Prints "The status code is 404"
print("The status message is \(http404Error.1)")
// Prints "The status message is Not Found"



let http200Status = (statusCode: 200, description: "OK")

print(http200Status.statusCode)
print(http200Status.description)
```

### Optionals

```swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)


```

### nil

```swift
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value

```

## Optional Binding

```swift

let possibleNumber:String = "121"

if let actualNumber = Int(possibleNumber){
        print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")

}else{
        print("The string \"\(possibleNumber)\" couldn't be converted to an integer")
}


let myNumber = Int(possibleNumber)
// Here, myNumber is an optional integer
if let myNumber = myNumber {
    // Here, myNumber is a non-optional integer
    print("My number is \(myNumber)")
}
// Prints "My number is 123"


if let myNumber {
    print("My number is \(myNumber)")
}
// Prints "My number is 123"
```

## Providing a Fallback Value

```swift

let name: String? = nil

let greeting = "Hello \(name ?? "Bright" )"

print(greeting)

```

## Force Unwrapping

```swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)


let number = convertedNumber!
```

## Error Handling

```swift
func canThrowAnError() throws {
    // this function may or may not throw an error
}


do {
    try canThrowAnError()
    // no error was thrown
} catch {
    // an error was thrown
}


func makeASandwich() throws {
    // ...
}


do {
    try makeASandwich()
    eatASandwich()
} catch SandwichError.outOfCleanDishes {
    washDishes()
} catch SandwichError.missingIngredients(let ingredients) {
    buyGroceries(ingredients)
}

```

## Assertions and Preconditions

Assertions and preconditions are checks that happen at runtime.

Assertions help you find mistakes and incorrect assumptions during development, and preconditions help you detect issues in production.

The difference between assertions and preconditions is in when they’re checked: Assertions are checked only in debug builds, but preconditions are checked in both debug and production builds.

### Debugging with Assertions

```swift
let age = -3
assert(age >= 0, "A person's age can't be less than zero.")
// This assertion fails because -3 isn't >= 0.

assert(age >= 0)
```

If the code already checks the condition, you use the assertionFailure(\_:file:line:) function to indicate that an assertion has failed. For example:

```swift
if age > 10 {
    print("You can ride the roller-coaster or the ferris wheel.")
} else if age >= 0 {
    print("You can ride the ferris wheel.")
} else {
    assertionFailure("A person's age can't be less than zero.")
}
```

### Enforcing Preconditions

```swift
// In the implementation of a subscript...
precondition(index > 0, "Index must be greater than zero.")
```

You can also call the preconditionFailure(\_:file:line:) function to indicate that a failure has occurred — for example, if the default case of a switch was taken, but all valid input data should have been handled by one of the switch’s other cases.
