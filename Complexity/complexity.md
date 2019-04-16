#Complexity

|NO.|Time Complexity|Big O notation|Graph|
|---|---|---|---|
|1|Consant time|O(1)|![1.png](source/1.png "1.png") |


## Constant time example code
```swift
func checkFirst(names: [String]) {
  if let first = names.first {
    print(first)
  } else {
    print("no names")
  }
}
```

## Linear time example code
```swift
func printNames(names: [String]) {
  for name in names {
    print(name)
  }
}
```