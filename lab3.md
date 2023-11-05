## Part 1: Bugs  
Failure-inducing input:  
In `ArrayTests.java`, we have the test of a simple array, `{1, 2, 3}`:  
```
@Test
public void testReversed2() {
  int[] input1 = {1,2,3};
  assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
}
```
An input that does not cause a failure is when an array's reverse is the same as the original, for example `{}`:
```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```  
The symptom when running in the terminal:
```
JUnit version 4.13.2
...E
Time: 0.01
There was 1 failure:
1) testReversed2(ArrayTests)
arrays first differed at element [0]; expected:<3> but was:<0>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversed2(ArrayTests.java:22)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 3,  Failures: 1
```
In `ArrayExamples.java`, we keep the original code to replicate the bug:  
```
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
And we fixed the bug and the new, working code is shown below:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
```  
By making the function return `newArray` instead of `arr` (the original array), and switching the order of assignment, we fix the bugs in the function `reversed()`. Previously, the function copied empty array values from `newArray` into the original array instead of copying original values into the new one, resulting in the fuction returning an empty array. After the fixes, the symptoms are addressed as well:
```
JUnit version 4.13.2
...
Time: 0.011

OK (3 tests)
```

## Part 2: Researching Commands  

`grep` has many command-line options, and the four that I chose are `-e PATTERNS`, `-f FILE`, `-i`, and `-v`. I found these while looking at the [Linux Manual Page](https://man7.org/linux/man-pages/man1/grep.1.html)
