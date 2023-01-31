Part 1


Part 2

testReverseinPlace Bug and Fix

Failure Inducing Input

```
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {1,2,3,4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4,3,2,1}, input1);
	}
```

Non-failure Inducing Input

```
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {1,1,1,1,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1,1,1,1,1}, input1);
	}
```

Symptom

![Image](symptom.png)

Bug

Before

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int new [] = arr[i]
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = new;
    }
  }
```

The bug was that the elements in the array were off when printing in reverse.
The fix incorporated a new method where the array length was divided by half as we need the elements after the halfway mark and created a new array that printed backwards.


Part 3
In lab 2&3, I learned how to run a server through a computer. I did know it was a concept that existed but have never tried utilizing the tool myself. Additionally, while running the server, through the lab I learned that if multiple attempts to try to connect to the same port at the same time and computer, there will be an error.
