# Complexity
## Table of Contents
* [Time Complexity](#Time-complexity)
    * [Constant time](#Constant-time)
    * Linear time
    * Quadratic 
    * Logarithmic time
    * Quasilinear time
    * other
* [Space complexity](#Space-complexity)

***

## Time complexity  
For small amounts of data, even the most expensive algorithm can seem fast due to the speed of modern hardware. However, as data increases, cost of an expensive algorithm becomes increasingly apparent. Time complexity is a measure of the time required to run an algorithm as the input size increases. In this section, you'll go through the most common time complexities and learn how to identify them.

***

### Constant time
A constant time algorithm is one that has the same running time regardless of the size of the input. Consider the following:

```swift
func checkFirst(names: [String]) {
  if let first = names.first {
    print(first)
  } else {
    print("no names")
  }
}
```

The size of the names array has no effect on the running time of this function. Whether the input has 10 items or 10 million items, this function only checks the first element of the array. Here's a visualization of this time complexity in a plot between time versus data size:

![illustration](/source/img.png "img") 

As input data increases, the amount of time the algorithm takes does not change.
For brevity, programmers use a notation known as Big O notation to represent various magnitudes of time complexity. The Big O notation for constant time is O(1).

***

## Linear Time
Consider the following snippet of code: 

