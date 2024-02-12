# Lab Report 3
By Angelica Cabusi (A17948600)\
CSE15L Joseph Politz\
2/23/2024
## `Part 1 - Bugs`
__Testing ArrayExamples.java(buggy program): reverseInPlace() Method:__\

* Failure-inducing input: 
```
@Test
public void testReverseInPlace() {
    int[] input1 = {5,1,2,4,8};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{8,4,2,1,5}, input1);
}
```
* Successful input: 
```
@Test
public void testReverseInPlace() {
    int[] input2 = {3,2,1,2,3};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3,2,1,2,3}, input2);
}


```
* Buggy Code:
    1. Before:
    ```
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
    }
    ```
    2. After:

    ```
    static void reverseInPlace(int[] arr) {
      int[] changedArray  = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
          changedArray[i] = arr[arr.length - i - 1];
        }
        arr = changedArray; 
    }
    ```
*Explanation:*\
The buggy code under "Before;" above reverses the array values perfectly for the first [few] values until a certain point (usually the middle value of the array). The issue is that once `i` reaches an index where the latter `(arr[arr.length - i - 1])` refers to an index whose value has already been changed, the call will refer to a reversed value rather than the intended value from the inputted array. Meaning that the first part of the array will be reversed while the later values of the array will have the same values as the now reversed value of the array, because the original inputted array value are not preserved.\
By making a new array, in this case it is a `changedArray`, we can save and refer to the original values of the inputted array. Now, `changedArray` will be the same size as the original array but empty and then filled (one-by-one) with the reversed value of the original array. We do this by referring to the last value of the original `arr` array and assigning it to the beginning of the `changedArray` and then iterating through each index where `changedArray`'s index is moving forward and the index value of `arr` is moving backward. Finally, `changedArray` will replace the inputted `arr` array as intended.
