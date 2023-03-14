# Week 8 Lab Report

## Completing the Competition Tasks

This is a report on how I completed the competition tasks outlined below: 

## Task 4: Log into ieng6

For this task, I ran the command: 
```
ssh cs15lwi23ate@ieng6-202.ucsd.edu 
```

The account logged in immediately. This is because I had generated an SSH key for ieng6 and now I do not need to put in a password to log in everytime. 

<img width="968" alt="Screenshot 2023-02-27 at 11 46 54 AM" src="https://user-images.githubusercontent.com/68794846/221667282-8783e1bf-c23d-42cd-8c36-60f3d1e99b98.png">

## Task 5: Clone your fork of the repository from your Github account

Fork the code into your own repository first. 

For this task I used the command:
```
git clone
```

I cloned the link under the SSH tab. This is because I had generated an SSH key for github earlier to access and write data into repositories from my computer. Now I can access github from my course specific account on ieng6.

I had already used git clone earlier, 8 lines above this code, so I pressed the up arrow 8 times to get it to appear on my line. 
keys pressed for git clone: 
```
< up > < up > < up > < up > < up > < up > < up > < up > < enter >
```
<img width="930" alt="Screenshot 2023-02-27 at 11 49 55 AM" src="https://user-images.githubusercontent.com/68794846/221667902-53ffbfbd-705a-41de-bca8-1e774c40c94c.png">

## Task 6: Run the tests, demonstrating that they fail

For this task, since I had already run these tests the last time I was doing the tasks, I had the following commands: 
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests 
```
much higher up in my search history already (8 commands up). I accessed them with these keys pressed: 
```
< up > < up > < up > < up > < up > < up > < up > < up > < enter > 
< up > < up > < up > < up > < up > < up > < up > < up > < enter > 
```
respectively.

running the commands: 

<img width="1112" alt="Screenshot 2023-02-27 at 12 13 58 PM" src="https://user-images.githubusercontent.com/68794846/221673425-9ff86581-7d8d-4191-ab95-7c1df637a4b7.png">

the failures: 

<img width="1507" alt="Screenshot 2023-02-27 at 12 13 12 PM" src="https://user-images.githubusercontent.com/68794846/221673335-ad66c642-f496-4e6b-97d0-030c81ed448a.png">

## Task 7: Edit the code file to fix the failing test

For this task, I opened up the ListExamples.java file through vim (as I was shown by the tutor) using this command: 
```
vim ListExamples.java
```

Then, I corrected the code by doing the following commands: 
```
i
< escape >
:w 
:q
```
"i" to insert and pressing < escape > and then ":w" to write into the code and then ":q" to quit vim. 
<img width="369" alt="Screenshot 2023-02-27 at 12 17 12 PM" src="https://user-images.githubusercontent.com/68794846/221674520-d0c8aad1-1fd9-48b1-ba01-3173dd421561.png">

In the vim after I pressed "i" and edited the code. To do this, after I pressed "i" I moved my cursor onto the line that had the bug and clicked and was able to access and fix the line. There are no other commands and there was no way to search for the line. I had to just click on where the issue was and fix it accordingly. Here is the fixed image: 

<img width="990" alt="Screenshot 2023-02-27 at 11 32 44 AM" src="https://user-images.githubusercontent.com/68794846/221664391-17619e23-4ca8-4c03-96be-94a50bba202b.png">

## Task 8: Run the tests, demonstrating that they now succeed

Now in order to access the 
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```
command, I had to go up 3 lines, so I pressed these keys and accessed it: 
```
< up > < up > < up > < enter>
```

Then, to access the 

```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
command, I had to also go up 3 lines, so I pressed these keys to access it: 
```
< up > < up > < up > < enter>
```

<img width="963" alt="Screenshot 2023-02-27 at 12 19 12 PM" src="https://user-images.githubusercontent.com/68794846/221675516-cf323535-8d6f-4f11-9cf3-87f3a399bd52.png">

## Task 9: Commit and push the resulting change to your Github account

Finally to commit and push into my Github account, I needed to use the following commands: 
```
git add ListExamples.java
git commit -m "updated file"
git push 
```
that I had used already, however, as they were many commands before and these commands were short anyway, instead of going up in my search history, I just manually inputted these commands. 

<img width="427" alt="Screenshot 2023-02-27 at 12 20 42 PM" src="https://user-images.githubusercontent.com/68794846/221676298-fce9a1e4-f244-4730-bd76-114fea963c62.png">

After I put those commands in, it successfully pushed into my fork of the repository and therefore I was able to complete all the tasks. Now, after practicing, these tasks take me around 2 minutes to complete. 
