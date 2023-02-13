# Week 4 Lab Report
## Part 1: 
Here is the code for my StringServer (StringServer.java): 
<img width="1512" alt="Screenshot 2023-01-30 at 11 42 14 AM" src="https://user-images.githubusercontent.com/68794846/215579556-cbbbdcdf-4b20-410a-af3f-2c2523d33961.png">
Here are two screenshots using /add-message: 

<img width="582" alt="Screenshot 2023-01-30 at 11 41 06 AM" src="https://user-images.githubusercontent.com/68794846/215579125-173ed33d-a4ba-4aab-b0ba-c089afa59321.png">

For this screenshot, the method in my code that's called is handleRequest. The relevant argument for this method is the url of the server (which is new URI(http://localhost:4000/add-message?s=hello) in this case). A relevant field of the class is the String returnString, which is what was written on the server and, at the time of this screenshot, was "hello". Another relevant field that is used within the function is String[] parameters, as at the time of the screenshot parameters[0] = "s" and parameters[1] = "hello".

<img width="582" alt="Screenshot 2023-01-30 at 11 41 35 AM" src="https://user-images.githubusercontent.com/68794846/215579795-7eb15fc0-e66b-4300-8696-bd080bf392db.png">

For this screenshot, the method in my code that's called is handleRequest. The relevant argument for this method is the url of the server (which is new URI (http://localhost:4000/add-message?s=How%20are%20you) in this case). A relevant field of the class is the String returnString, which is what was written on the server and, at the time of this screenshot, was "hello\nHow are you\n". Another relevant field that is used within the function is String[] parameters, as at the time of the screenshot parameters[0] = "s" and parameters[1] = "How are you".

## Part 2: 
Here is the code of my JUnit tester that tests the buggy code: (both failure inducing inputs and not failure inducing inputs included)
~~~
@Test 
public void testReverseInPlace() {
    // this IS NOT a failure inducing input
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
    
    // this IS a failure inducing input
    int[] input2 = {3,4,5};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{5,4,3}, input2);
    
    // this IS a failure inducing input
    int[] input3 = {0, 0, 1, 2, 3};
    ArrayExamples.reverseInPlace(input3);
    assertArrayEquals(new int[]{3,2,1,0,0}, input3);
}
~~~
Here is an image of the Symptom (with the not failure inducing input and one of the failure inducing inputs):  

<img width="1161" alt="Screenshot 2023-01-30 at 2 08 50 PM" src="https://user-images.githubusercontent.com/68794846/215606819-2a30c343-920e-42bd-a410-859789045547.png">

Here is the code that's causing the bug (Before fix): 
~~~
// Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
 }
 ~~~
 
 Here is the fixed code with no bug (After fix): 
 ~~~
 // Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      temp[arr.length - i - 1] = arr[i];
    }
    for (int i = 0; i < temp.length; i++) {
      arr[i] = temp[i];
    }
}
~~~
My fix addressed the issue because originally there was no temporary array to store the values in reverse order, so the code was overwriting the first half of the elements with the values of the second half elements and then the second half of the elements don't change properly, because the elements that are supposed to go in the second half were the ones from the first half that weren't stored anywhere. To fix this bug in the reverseInPlace function, I made a temporary array to temporarily store the reversed array as it reverses and then I modified the original array by copying the temp array into the original. This way, the first half of the elements are not lost for when they're needed to be put in the second half of the array after reversing.

## Part 3: 
In week 2, I learned about how to make a server and have multiple devices access the server. Earlier, I had never known how to have a server that other people could use, but when making a simple search engine, I realized what could be possible with a server. Especially the fact that what some people do on one device could change the values shown on another device was interesting! I found this out when having multiple browsers running the server and having them all trying to incrememnt the values on their own browser. When one device incremented the value, it incremented for the other devices too and I thought that was cool as I didn't know that would happen.
