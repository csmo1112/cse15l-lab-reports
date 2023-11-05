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
In 
