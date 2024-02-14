# Part 1

## Failure Inducing Input

```java
@Test
public void testReversedEven() {
  int[] input1 = {1, 2};
  assertArrayEquals(new int[]{2, 1}, ArrayExamples.reversed(input1));
}
```

## Non-failure Inducing Input

```java
@Test
public void testReversedEmpty() {
  int[] input1 = { };
  assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```

## Output of JUnit

![image](Screenshot2024-02-12152535.png)

## Before Code

```java
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

## After Code

```java
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
 return newArray;
}
```

This code fixes the error as the previous code switched adding to the `newArray` variable instead of `arr` variable. It also incorrectly returned the old `arr`, instead of the `newArray` variable.

# Part 2

We'll be looking at the `find` command here:

## `find -type <type>` 

Inputing `f` for `<type>` returns only files, not directories.

```

```