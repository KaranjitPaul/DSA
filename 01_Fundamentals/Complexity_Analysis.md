# Complexity Analysis

Complexity analysis describes how an algorithm's resource requirements grow as its input grows.

It helps answer questions such as:

- How will this solution behave with much larger input?
- Which of two correct solutions scales better?
- Is the algorithm likely to meet a system's constraints?

Complexity does not usually predict an exact runtime. It describes growth.

## Input Size

The symbol `n` commonly represents input size.

Depending on the problem, `n` might mean:

- Number of items in an array
- Length of a string
- Number of nodes in a graph
- Number of operations to process

Defining `n` clearly is necessary before analyzing an algorithm.

## Time Complexity

Time complexity describes how the amount of work grows with input size.

Consider finding a value in an unsorted array:

```text
for each value in the array:
    if value is the target:
        return found
```

In the worst case, the algorithm examines every value. If the array contains `n` values, the work grows linearly with `n`.

Its worst-case time complexity is `O(n)`.

## Space Complexity

Space complexity describes how additional memory usage grows with input size.

An algorithm that uses only a few variables regardless of input size uses constant extra space:

```text
O(1)
```

An algorithm that creates a new array containing `n` items uses linear extra space:

```text
O(n)
```

## Big O

Big O describes an upper bound on growth. It is commonly used to discuss worst-case behavior.

When analyzing Big O:

- Ignore constant multipliers.
- Ignore lower-order terms.
- Focus on the dominant growth term.

For example:

```text
3n + 10 becomes O(n)
n^2 + n + 5 becomes O(n^2)
```

This simplification is useful because the dominant term matters most as `n` becomes large.

## Common Growth Rates

From generally better-scaling to worse-scaling:

| Complexity | Name | Typical Example |
| --- | --- | --- |
| `O(1)` | Constant | Access an array element by index |
| `O(log n)` | Logarithmic | Binary search |
| `O(n)` | Linear | Scan an array |
| `O(n log n)` | Linearithmic | Efficient comparison sorting |
| `O(n^2)` | Quadratic | Compare every pair |
| `O(2^n)` | Exponential | Explore every subset in a naive solution |
| `O(n!)` | Factorial | Explore every ordering |

Complexity alone does not decide which algorithm is best. Correctness, input constraints, memory, simplicity, and real-world constants also matter.

## Analyzing Simple Code

### Constant Work

```text
read the first item
```

The amount of work does not grow with `n`.

```text
O(1)
```

### Single Loop

```text
for each item:
    process item
```

The loop performs work once for each of `n` items.

```text
O(n)
```

### Nested Loops

```text
for each item:
    for each item:
        compare the pair
```

The inner operation runs approximately `n * n` times.

```text
O(n^2)
```

### Repeated Halving

```text
while n is greater than 1:
    divide n by 2
```

The number of operations grows by one each time the input size doubles.

```text
O(log n)
```

## Best, Average, And Worst Cases

An algorithm can behave differently for different inputs of the same size.

For linear search:

- Best case: the target is first, `O(1)`
- Worst case: the target is last or absent, `O(n)`
- Average case: depends on assumptions about the input

Always state which case is being analyzed when it matters.

## Big Omega And Big Theta

- Big O describes an asymptotic upper bound.
- Big Omega describes an asymptotic lower bound.
- Big Theta describes a tight asymptotic bound.

In everyday programming discussion, Big O is often used informally to describe tight or worst-case growth. Precise analysis should distinguish these meanings.

## Tradeoffs

A faster algorithm may use more memory.

For example, storing previously seen values in a hash table can reduce repeated searching but requires additional space.

Good engineering considers both time and space, along with:

- Correctness
- Readability
- Maintainability
- Input constraints
- Available resources

## Common Mistakes

- Counting lines of code instead of operations relative to input size
- Forgetting to define the input size
- Assuming every nested loop is automatically `O(n^2)`
- Ignoring space used by recursion
- Treating Big O as an exact runtime measurement
- Optimizing before understanding the actual constraints

## Practice Questions

1. Why does `3n + 10` simplify to `O(n)`?
2. Why is binary search `O(log n)`?
3. Can two nested loops have `O(n)` total complexity?
4. What is the space complexity of copying an array?
5. When might an `O(n)` solution be preferable to an `O(log n)` solution?

## My Explanation

Write your own explanation of complexity analysis after studying this note. If the explanation is unclear, revisit the examples and practice questions.

