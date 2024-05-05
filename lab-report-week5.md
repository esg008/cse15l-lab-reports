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
* Before
```java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
* After
```java
static void reverseInPlace(int[] arr) {
    int[] copy = new int[arr.length];
    for(int i = 0; i <copy.length; i +=1){
      copy[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i +=1){
      arr[i] = copy[arr.length - i - 1];
    }
  }
```

- The first implementation would modify the array in the loop which ended up just replacing the first values with the ending values. The fix creates a new copy of the original array that stores original values before reversing. Then iterates through the second copy to effectively reverse the order.

# Part 2: Researching Commands

**`grep`**

`$ grep -c "biomed" find-results.txt
838`

`$ grep -c "biomed" technical/plos
grep: technical/plos: Is a directory
0`




  
  




