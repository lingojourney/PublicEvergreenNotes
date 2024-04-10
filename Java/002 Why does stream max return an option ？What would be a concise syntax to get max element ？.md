If the list is guaranteed to be non-empty, you can use the `stream.max()` method without the need to check for the presence of the value within an `Optional`. Here’s a more concise way to get the maximum element:

```java
List<Integer> nums = Arrays.asList(-1, 2, 1, 7, 3);
Integer maxElement = nums.stream().max(Comparator.naturalOrder()).orElseThrow(NoSuchElementException::new);
// Use maxElement as needed
```

In this case, since you’re certain the list isn’t empty, you can directly retrieve the value with `orElseThrow()`, which will throw an exception if no value is present. This is a safe operation because you’ve ensured that the list has at least one element.