# Week 2 Lab Report
## Part 1: 
Here is the code for my StringServer (StringServer.java): 
<img width="1512" alt="Screenshot 2023-01-30 at 11 42 14 AM" src="https://user-images.githubusercontent.com/68794846/215579556-cbbbdcdf-4b20-410a-af3f-2c2523d33961.png">
Here are two screenshots using /add-message: 

<img width="582" alt="Screenshot 2023-01-30 at 11 41 06 AM" src="https://user-images.githubusercontent.com/68794846/215579125-173ed33d-a4ba-4aab-b0ba-c089afa59321.png">

For this screenshot, the method in my code that's called is handleRequest. The relevant argument for this method is the url of the server (which is new URI(http://localhost:4000/add-message?s=hello) in this case). A relevant field of the class is the String returnString, which is what was written on the server and, at the time of this screenshot, was "hello". Another relevant field that is used within the function is String[] parameters, as at the time of the screenshot parameters[0] = "s" and parameters[1] = "hello".

<img width="582" alt="Screenshot 2023-01-30 at 11 41 35 AM" src="https://user-images.githubusercontent.com/68794846/215579795-7eb15fc0-e66b-4300-8696-bd080bf392db.png">

For this screenshot, the method in my code that's called is handleRequest. The relevant argument for this method is the url of the server (which is new URI (http://localhost:4000/add-message?s=How%20are%20you) in this case). A relevant field of the class is the String returnString, which is what was written on the server and, at the time of this screenshot, was "hello\nHow are you\n". Another relevant field that is used within the function is String[] parameters, as at the time of the screenshot parameters[0] = "s" and parameters[1] = "How are you".

## Part 2: 
here is the code of my tester 
~~~
@Test 
public void testReverseInPlace() {
    // this is not a failure inducing input
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
    
    // this is a failure inducing input
    int[] input2 = {3,4,5};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{5,4,3}, input2);
    
    // this is a failure inducing input
    int[] input3 = {0, 0, 1, 2, 3};
    ArrayExamples.reverseInPlace(input3);
    assertArrayEquals(new int[]{3,2,1,0,0}, input3);
}
~~~
