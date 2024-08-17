# Basic Operators

## Operators are unary, binary, or ternary:

- Unary operators operate on a single target (such as -a). Unary prefix operators appear immediately before their target (such as !b), and unary postfix operators appear immediately after their target (such as c!).

- Binary operators operate on two targets (such as 2 + 3) and are infix because they appear in between their two targets.

- Ternary operators operate on three targets. Like C, Swift has only one ternary operator, the ternary conditional operator (a ? b : c).

## Assignment Operator

```swift
let b = 10
var a = 5
a = b
// a is now equal to 10

let (x, y) = (1, 2)
// x is equal to 1, and y is equal to 2
```

## Arithmetic Operators

- Addition (+)

- Subtraction (-)

- Multiplication (\*)

- Division (/)

```swift
1 + 2       // equals 3
5 - 3       // equals 2
2 * 3       // equals 6
10.0 / 2.5  // equals 4.0
```

## Unary Minus Operator

```swift
let three = 3
let minusThree = -three       // minusThree equals -3
let plusThree = -minusThree   // plusThree equals 3, or "minus minus three"

```

## Compound Assignment Operators

```swift
var a = 1
a += 2
// a is now equal to 3
```

## Comparison Operators

- Equal to (a == b)

- Not equal to (a != b)

- Greater than (a > b)

- Less than (a < b)

- Greater than or equal to (a >= b)

- Less than or equal to (a <= b)

Swift also provides two identity operators (=== and !==), which you use to test whether two object references both refer to the same object instance.

## Ternary Conditional Operator

```swift
let contentHeight = 40
let hasHeader = true
let rowHeight = contentHeight + (hasHeader ? 50 : 20)
// rowHeight is equal to 90
```

## Nil-Coalescing Operator

## Range Operators

### Closed Range Operator

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

### Half-Open Range Operato

```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

### One-Sided Ranges

```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names[2...] {
    print(name)
}
// Brian
// Jack


for name in names[...2] {
    print(name)
}
// Anna
// Alex
// Brian

for name in names[..<2] {
    print(name)
}
// Anna
// Alex
```
