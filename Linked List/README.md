# Linked List
A linked list is a collection of values arranged in a linear unidirectional sequence. A linked list has several theoretical advantages over contiguous storage options such as the Swift Array

####Key points
* Linked lists are linear and unidirectional. As soon as you move a reference from one node to another, you can't go back.
* Linked lists have a O(1) time complexity for head first insertions. Arrays have O(n) time complexity for head-first insertions.
* Conforming to Swift collection protocols such as Sequence and Collection offers a host of helpful methods for a fairly small amount of requirements.
* Copy-on-write behavior lets you achieve value semantics.

---

## Basic Linked List

![1.png](source/1.png "1.png")

Sample Code:

```swift
public class Node<Value> {

  public var value: Value
  public var next: Node?
  
  public init(value: Value, next: Node? = nil) {
    self.value = value
    self.next = next
  }
}

extension Node: CustomStringConvertible {

  public var description: String {
    guard let next = next else {
      return "\(value)"
    }
    return "\(value) -> " + String(describing: next) + " "
  }
}
```

```swift
example(of: "creating and linking nodes") {
  let node1 = Node(value: 1)
  let node2 = Node(value: 2)
  let node3 = Node(value: 3)
  
  node1.next = node2
  node2.next = node3
  
  print(node1)  // 1 -> 2 -> 3
}
```

Linked list has the concept of a head and tail, which refers to the first and last nodes of the list respectively
![2.png](source/2.png "2.png")

```swift
public struct LinkedList<Value> {

  public var head: Node<Value>?
  public var tail: Node<Value>?
  
  public init() {}

  public var isEmpty: Bool {
    return head == nil
  }
}

extension LinkedList: CustomStringConvertible {

  public var description: String {
    guard let head = head else {
      return "Empty list"
    }
    return String(describing: head)
  }
}
```

---

### Adding values to the list
#### push: Adds a value at the front of the list.

```swift
public mutating func push(_ value: Value) {
  head = Node(value: value, next: head)
  if tail == nil {
    tail = head
  }
}
```
```swift
example(of: "push") {
  var list = LinkedList<Int>()
  list.push(3)
  list.push(2)
  list.push(1)
  
  print(list)   // 1 -> 2 -> 3
}
```

#### append: Adds a value at the end of the list

```swift
public mutating func append(_ value: Value) {

  // 1
  guard !isEmpty else {
    push(value)
    return
  }
  
  // 2
  tail!.next = Node(value: value)
  
  // 3
  tail = tail!.next
}
```
```swift
example(of: "append") {
  var list = LinkedList<Int>()
  list.append(1)
  list.append(2)
  list.append(3)
  
  print(list) // 1 -> 2 -> 3
}
```

#### insert(after:): Adds a value after a particular node of the list.

```swift
public func node(at index: Int) -> Node<Value>? {
  // 1
  var currentNode = head
  var currentIndex = 0
  
  // 2
  while currentNode != nil && currentIndex < index {
    currentNode = currentNode!.next
    currentIndex += 1
  }
  
  return currentNode
}
```

```swift
// 1
@discardableResult
public mutating func insert(_ value: Value,
                            after node: Node<Value>)
                            -> Node<Value> {
  // 2
  guard tail !== node else {
    append(value)
    return tail!
  }
  // 3
  node.next = Node(value: value, next: node.next)
  return node.next!
}
```

```swift
example(of: "inserting at a particular index") {
  var list = LinkedList<Int>()
  list.push(3)
  list.push(2)
  list.push(1)
  
  print("Before inserting: \(list)") // Before inserting: 1 -> 2 -> 3
  var middleNode = list.node(at: 1)!
  for _ in 1...4 {
    middleNode = list.insert(-1, after: middleNode)
  }
  print("After inserting: \(list)") // After inserting: 1 -> 2 -> -1 -> -1 -> -1 -> -1 -> 3
}
```

---

### Removing values from the list

#### pop operations

```swift
@discardableResult
public mutating func pop() -> Value? {
  defer {
    head = head?.next
    if isEmpty {
      tail = nil
    }
  }
  return head?.value
}
```

```swift
example(of: "pop") {
  var list = LinkedList<Int>()
  list.push(3)
  list.push(2)
  list.push(1)
  
  print("Before popping list: \(list)") //Before popping list: 1 -> 2 -> 3
  let poppedValue = list.pop() 
  print("After popping list: \(list)")  //After popping list: 2 -> 3
  print("Popped value: " + String(describing: poppedValue)) // Popped value: Optional(1)
}
```
removeLast operations

```swift 
@discardableResult
public mutating func removeLast() -> Value? {
  // 1
  guard let head = head else {
    return nil
  }
  // 2
  guard head.next != nil else {
    return pop()
  }
  // 3
  var prev = head
  var current = head
  
  while let next = current.next {
    prev = current
    current = next
  }
  // 4
  prev.next = nil
  tail = prev
  return current.value
}
```

```swift
example(of: "removing the last node") {
  var list = LinkedList<Int>()
  list.push(3)
  list.push(2)
  list.push(1)

  print("Before removing last node: \(list)") // Before removing last node: 1 -> 2 -> 3
  let removedValue = list.removeLast()

  print("After removing last node: \(list)") // After removing last node: 1 -> 2
  print("Removed value: " + String(describing: removedValue)) // Removed value: Optional(3)
}
```

#### remove(after:) operations

```swift
“@discardableResult
public mutating func remove(after node: Node<Value>) -> Value? {
  defer {
    if node.next === tail {
      tail = node
    }
    node.next = node.next?.next
  }
  return node.next?.value
}
```



```swift
example(of: "removing a node after a particular node") {
  var list = LinkedList<Int>()
  list.push(3)
  list.push(2)
  list.push(1)
  
  print("Before removing at particular index: \(list)") // Before removing at particular index: 1 -> 2 -> 3
  let index = 1
  let node = list.node(at: index - 1)!
  let removedValue = list.remove(after: node)
  
  print("After removing at index \(index): \(list)") // After removing at index 1: 1 -> 3
  print("Removed value: " + String(describing: removedValue)) // Removed value: Optional(2)
}
```

#### Custom collection indexes

```swift
“extension LinkedList: Collection {

  public struct Index: Comparable {

    public var node: Node<Value>?
    
    static public func ==(lhs: Index, rhs: Index) -> Bool {
      switch (lhs.node, rhs.node) {
      case let (left?, right?):
        return left.next === right.next
      case (nil, nil):
        return true
      default:
        return false
      }
    }
    
    static public func <(lhs: Index, rhs: Index) -> Bool {
      guard lhs != rhs else {
        return false
      }
      let nodes = sequence(first: lhs.node) { $0?.next }
      return nodes.contains { $0 === rhs.node }
    }
  }
}
```

```swift
// 1
public var startIndex: Index {
  return Index(node: head)
}
// 2
public var endIndex: Index {
  return Index(node: tail?.next)
}
// 3
public func index(after i: Index) -> Index {
  return Index(node: i.node?.next)
}
// 4
public subscript(position: Index) -> Value {
  return position.node!.value
}
```

```swift
example(of: "using collection") {
  var list = LinkedList<Int>()
  for i in 0...9 {
    list.append(i)
  }
  print("List: \(list)")  //List: 0 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8 -> 9
  print("First element: \(list[list.startIndex])")  //First element: 0
  print("Array containing first 3 elements: \(Array(list.prefix(3)))") //Array containing first 3 elements: [0, 1, 2]
  print("Array containing last 3 elements: \(Array(list.suffix(3)))")  //Array containing last 3 elements: [7, 8, 9]
  let sum = list.reduce(0, +)
  print("Sum of all values: \(sum)") //Sum of all values: 45
}
```
