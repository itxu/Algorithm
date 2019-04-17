# Stack

Stacks are useful, and also exceedingly simple. The main goal of building a stack is to enforce how you access your data. If you had a tough time with the linked list concepts, you’ll be glad to know that stacks are comparatively trivial.

There are only two essential operations for a stack: 

* push: Adding an element to the top of the stack. 
* pop: Removing the top element of the stack.

This means that you can only add or remove elements from one side of the data structure. In computer science, a stack is known as the `LIFO` (last-in first-out) data structure. Elements that are pushed in last are the first ones to be popped out.
Stacks are used prominently in all disciplines of programming. To list a few:

* iOS uses the navigation stack to push and pop view controllers into and out of view.
* Memory allocation uses stacks at the architectural level. Memory for local variables is also managed using a stack.
* Search and conquer algorithms, such as finding a path out of a maze, use stacks to facilitate backtracking.


`push and pop both have a O(1) time complexity.`

```swift
public struct Stack<Element> {
  private var storage: [Element] = []
  public init() { }
}
extension Stack: CustomStringConvertible {
  public var description: String {
    let topDivider = "----top----\n"
    let bottomDivider = "\n-----------"
    let stackElements = storage
      .map { "\($0)" }
      .reversed()
      .joined(separator: "\n")
    return topDivider + stackElements + bottomDivider
  }
}
```

```swift
public mutating func push(_ element: Element) {
  storage.append(element)
}
@discardableResult
public mutating func pop() -> Element? {
  return storage.popLast()
}
```

### push

```swift
example(of: "using a stack") {
  var stack = Stack<Int>()
  stack.push(1)
  stack.push(2)
  stack.push(3)
  stack.push(4)
  print(stack)
  if let poppedElement = stack.pop() {
    assert(4 == poppedElement)
    print("Popped: \(poppedElement)")
    /*
    ----top----
	4
	3
	2
	1
	-----------
	Popped: 4
	*/
  }
}
```

### Non-essential operations
```swift
public func peek() -> Element? {
 return storage.last
}
public var isEmpty: Bool {
  return peek() == nil
}
public init(_ elements: [Element]) {
  storage = elements
}
```

### pop

```swift
example(of: "initializing a stack from an array") {
  let array = ["A", "B", "C", "D"]
  var stack = Stack(array)
  print(stack)
  stack.pop()
}
```

```swift
extension Stack: ExpressibleByArrayLiteral {
  public init(arrayLiteral elements: Element...) {
    storage = elements
  }
}
```

```swift
example(of: "initializing a stack from an array literal") {
  var stack: Stack = [1.0, 2.0, 3.0, 4.0]
  print(stack)
  stack.pop()
}
```

