# CSE 15L Lab 3

## Part 1:

### Code

For part one I chose to use this method:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

### Failure-inducing input:

```
@Test
    public void testReverseInPlaceFailure() {
        int[] input = {1, 2, 3, 4};
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(new int[] {4, 3, 2, 1}, input);
    }
```

### Non-failure-inducing input:

```
@Test
    public void testReverseInPlaceNoFailure() {
        int[] input = {1, 2, 2, 1};
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(new int[] {1, 2, 2, 1}, input);
    }
```
