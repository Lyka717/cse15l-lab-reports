# Lab Report 3
By Angelica Cabusi (A17948600)\
CSE15L Joseph Politz\
2/23/2024
## `Part 1 - Bugs`
__Testing ArrayExamples.java(buggy program): reverseInPlace() Method:__\

- Failure-inducing input: 
```
@Test
public void testReverseInPlace() {
    int[] input1 = {5,1,2,4,8};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{8,4,2,1,5}, input1);
}
```
- Successful input: 
```
@Test
public void testReverseInPlace() {
    int[] input2 = {3,2,1,2,3;
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3,2,1,2,3}, input2);
}
```
