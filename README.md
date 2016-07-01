# swift tour

> [02_a_swift_tour](https://numbbbbb.gitbooks.io/-the-swift-programming-language-/content/chapter1/02_a_swift_tour.html)

像JS一样，swift不需要启动函数，直接写即可
```swift
print("Hello, World")  // 分号也可以省略
```

## 简单值

在 `swift` 里面，分别使用 `let` 和 'var' 来声明 `常量` 和 `变量`。
在声明后面加上 `:type` 来声明类型，如果声明没有提供初始值，则必须加上类型声明
```swift
let PI = 3.1415926535897

let ADDRESS:String = "Guangdong Shenzhen"  

var fullName:String
var name = "Ryou"
var familyName = "He"
fullName = name + " " + familyName
```

不同的是，`swift` 不会自动转换类型
```swift
let label = "This building's height is "
let height = 10
let unit = " meters"
let heightLabel = label + String(height) + unit
```

上面的 `heightLabel` 还可以使用类似 `ES2015` 的模板的方式来声明，在 `swift` 里面，模板中
的变量以 `\(` 开头，比如：上面的 `heightLabel` 语句可以改写成
```swift
let heightLabel = "This building's height is \(height) meters"
```

## 数组和字典

在 `swift` 里面，使用 `[]` 来创建数组和字典，并使用下表或者键来访问元素
```swift
var shoppingList = ["catfish", "water", "tulips", "blue paint"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"

// 创建空数组和字典：
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```

## 控制流

在 `swift` 里面，`if`、`for` 等语句后面不需要小括号，直接将条件跟在后面
`if exp { /*...*/ }`

### `if` 语句

```swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore)
```

可以一起使用 `if` 和 `let` 来处理值缺失的情况。
有些变量的值是可选的。
一个可选的值可能是一个具体的值或者是 `nil`，表示值缺失。
在类型后面加一个问号来标记这个变量的值是可选的。

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
print(greeting)

optionalName = nil
if let name = optionalName {
    print("I woun't come out!")
} else {
    print("So this would come!")
}
```

如果变量的可选值是nil，条件会判断为false，大括号中的代码会被跳过。
如果不是nil，会将值赋给let后面的常量，这样代码块中就可以使用这个值了。

### `switch` 语句

`switch` 支持任意类型的数据以及各种比较操作——不仅仅是整数以及测试相等。


```swift
let vegetable = "red pepper"
var vegetableComment:String
switch vegetable {
case "celery":
    vegetableComment = "Add some raisins and make ants on a log."
case "cucumber", "watercress":
    vegetableComment = "That would make a good tea sandwich."
case let x where x.hasSuffix("pepper"):
    vegetableComment = "Is it a spicy \(x)?"
default:
    vegetableComment = "Everything tastes good in soup."
}
print(vegetableComment)  // pepper
```

