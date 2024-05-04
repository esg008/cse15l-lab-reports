# Part 1: Bugs


* Failure-inducing input
  ```java
    @Test
  public void testReverseInPlace(){
    int [] input = {1,2,3,4};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int []{4,3,2,1}, input);
  }
  ```
* Input that doesn't induce failure
  ```java
  @Test
  public void testSecondReverseInPlace2(){
    int [] input = {10};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int []{10}, input);
  }
  ```

<img src="ArrayListTest-SS.png" alt="Test Results" width="550"/>

  **Chosen Bug:** 
```java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
  
  




