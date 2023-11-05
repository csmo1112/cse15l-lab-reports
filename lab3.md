## Part 1: Bugs  
Failure-inducing input:  
In `ArrayTests.java`:  
```
@Test
public void testReversed2() {
  int[] input1 = {1,2,3};
  assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
}
```
In 
