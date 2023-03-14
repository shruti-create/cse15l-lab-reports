# Week 10 Lab Report
## Doing Lab 3 in a Different Way: Researching the find Command-line Options instead of grep

## Option 1: find . -type d 
Source: https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/

Function: This option causes the find command to find all the directories under the current working directory. This is useful if you are looking for the different directories under the current directory. For example, if you are trying to find a certain type of file, you could use this to see the directories and figure out where the file could be organized with that information. This could also be used with a different letter than "d", as if the letter was "f" instead, then find would look for files. 

Example Use 1:
```
$ cd docsearch
$ cd written_2
$ find . -type d
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Berk
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Rybczynski
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Castro
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```
As you can see in the example, it found all the directories inside the working directory, which include non-fiction and travel_guides and all the directories under them. This command is useful as it shows all the directories under the specific directory, which differentiates it from the command "ls", as "ls" only shows the directories directly under the working directory and not the ones under those. 

Example Use 2:
```
$ cd non-fiction
$ cd OUP
$ find . -type d
.
./Berk
./Abernathy
./Rybczynski
./Kauffman
./Fletcher
./Castro
$ ls
Abernathy       Berk            Castro          Fletcher        Kauffman        Rybczynski
```
As you can see in this example, we used the command to get the directories under the directory OUP and when looking at the directories under the directory OUP with the command ls, we see that they're the same. 

## Option 2: find . -name < Name of file to search for >
Source: https://www.tecmint.com/35-practical-examples-of-linux-find-command/ 

Function: This option allows the find command to find all the files with the given in the current working directory. This is useful when you're looking for a single file and you know what it's called, so you can use this command to easily search for it. 

Example Use 1:
```
 $ cd docsearch
 $ cd written_2
 $ cd non-fiction
 $ cd OUP
 $ cd Berk
 $ ls
 CH4.txt ch1.txt ch2.txt ch7.txt
 $ find . -name ch2.txt
 ./ch2.txt
```
As you can see above, there were many files, but after we used the find command, we were able to find the exact file we needed: the ch2.txt. This was very beneficial as we knew the file we needed and so we could easily get it. 

Example Use 2:
```
 $ cd Berk
 $ find . -name ch4.txt
 $ find . -name CH4.txt
 ./CH4.txt
```
As you can see above, we could find the CH4.txt from berk when we searched exactly CH4.txt, however not when we searched ch4.txt. So, this shows how this is only useful when you know exactly the name of the file you are looking for. 

## Option 3: find . -iname < Name of file to search for >
Source: https://www.tecmint.com/35-practical-examples-of-linux-find-command/

Function: This option allows the find command to find any file with the name of the file to search for, however, it is different from the other command, as it doesn't need it to be the exact capitalization to search for it. Therefore, you can search for any file without exactly knowing what needs to be and doesn't need to be capitalized in the file title.

Example Use 1:
```
  $ cd Berk
  $ find . -iname ch4.txt
  ./CH4.txt
```
In this example, we can see that even though I didn't search for the exact name of the file (the capitalization was off), it still found the file for me. This command would be beneficial when you want to search for a file that you don't exactly know the capitalization for. 

Example Use 2:
```
  $ cd written_2
  $ ls
  non-fiction     travel_guides
  $ find . -iname Travel_Guides 
  ./travel_guides
```
As you can see in this example, it found the directory for me, so this command isn't limited to only files. Also, the capitalization was off in two parts of the search, but the command still found the directory, showing how this command could be beneficial when searching files and directories. 

## Option 4: find . -name < file name > -exec rm -i {} \;
Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

Function: This option allows the find command to find a file and then delete it from the directory. This is useful as it allows people to search and delete for specific files with the option on just one command. 

Example Use 1:
```
 $ cd travel_guides
 $ cd berlitz2
 $ ls
Algarve-History.txt             Bali-History.txt                Budapest-History.txt            China-WhereToGo.txt             NewOrleans-History.txt
Algarve-Intro.txt               Bali-WhatToDo.txt               Budapest-WhatToDo.txt           Costa-History.txt               Paris-WhatToDo.txt
Algarve-WhatToDo.txt            Bali-WhereToGo.txt              Budapest-WhereoGo.txt           Costa-WhatToDo.txt              Paris-WhereToGo.txt
Algarve-WhereToGo.txt           Barcelona-History.txt           California-History.txt          Costa-WhereToGo.txt             Poland-History.txt
Amsterdam-History.txt           Barcelona-WhatToDo.txt          California-WhatToDo.txt         CostaBlanca-History.txt         Poland-WhatToDo.txt
Amsterdam-Intro.txt             Barcelona-WhereToGo.txt         California-WhereToGo.txt        CostaBlanca-WhatToDo.txt        Portugal-History.txt
Amsterdam-WhatToDo.txt          Beijing-History.txt             Canada-History.txt              Crete-History.txt               Portugal-WhatToDo.txt
Amsterdam-WhereToGo.txt         Beijing-WhatToDo.txt            Canada-WhereToGo.txt            Crete-WhatToDo.txt              Portugal-WhereToGo.txt
Athens-History.txt              Beijing-WhereToGo.txt           CanaryIslands-History.txt       Crete-WhereToGo.txt             PuertoRico-History.txt
Athens-Intro.txt                Berlin-History.txt              CanaryIslands-WhatToDo.txt      CstaBlanca-WhereToGo.txt        PuertoRico-WhatToDo.txt
Athens-WhatToDo.txt             Berlin-WhatToDo.txt             CanaryIslands-WhereToGo.txt     Cuba-History.txt                PuertoRico-WhereToGo.txt
Athens-WhereToGo.txt            Berlin-WhereToGo.txt            Cancun-History.txt              Cuba-WhatToDo.txt               Vallarta-History.txt
Bahamas-History.txt             Bermuda-WhatToDo.txt            Cancun-WhatToDo.txt             Cuba-WhereToGo.txt              Vallarta-WhatToDo.txt
Bahamas-Intro.txt               Bermuda-WhereToGo.txt           Cancun-WhereToGo.txt            Nepal-History.txt               Vallarta-WhereToGo.txt
Bahamas-WhatToDo.txt            Bermuda-history.txt             China-History.txt               Nepal-WhatToDo.txt
Bahamas-WhereToGo.txt           Boston-WhereToGo.txt            China-WhatToDo.txt              Nepal-WhereToGo.txt
 $ find . -name Algarve-History.txt -exec rm -i {} \; 
 remove ./Algarve-History.txt? Y
 $ ls
Algarve-Intro.txt               Bali-WhatToDo.txt               Budapest-WhatToDo.txt           Costa-History.txt               Paris-WhatToDo.txt
Algarve-WhatToDo.txt            Bali-WhereToGo.txt              Budapest-WhereoGo.txt           Costa-WhatToDo.txt              Paris-WhereToGo.txt
Algarve-WhereToGo.txt           Barcelona-History.txt           California-History.txt          Costa-WhereToGo.txt             Poland-History.txt
Amsterdam-History.txt           Barcelona-WhatToDo.txt          California-WhatToDo.txt         CostaBlanca-History.txt         Poland-WhatToDo.txt
Amsterdam-Intro.txt             Barcelona-WhereToGo.txt         California-WhereToGo.txt        CostaBlanca-WhatToDo.txt        Portugal-History.txt
Amsterdam-WhatToDo.txt          Beijing-History.txt             Canada-History.txt              Crete-History.txt               Portugal-WhatToDo.txt
Amsterdam-WhereToGo.txt         Beijing-WhatToDo.txt            Canada-WhereToGo.txt            Crete-WhatToDo.txt              Portugal-WhereToGo.txt
Athens-History.txt              Beijing-WhereToGo.txt           CanaryIslands-History.txt       Crete-WhereToGo.txt             PuertoRico-History.txt
Athens-Intro.txt                Berlin-History.txt              CanaryIslands-WhatToDo.txt      CstaBlanca-WhereToGo.txt        PuertoRico-WhatToDo.txt
Athens-WhatToDo.txt             Berlin-WhatToDo.txt             CanaryIslands-WhereToGo.txt     Cuba-History.txt                PuertoRico-WhereToGo.txt
Athens-WhereToGo.txt            Berlin-WhereToGo.txt            Cancun-History.txt              Cuba-WhatToDo.txt               Vallarta-History.txt
Bahamas-History.txt             Bermuda-WhatToDo.txt            Cancun-WhatToDo.txt             Cuba-WhereToGo.txt              Vallarta-WhatToDo.txt
Bahamas-Intro.txt               Bermuda-WhereToGo.txt           Cancun-WhereToGo.txt            Nepal-History.txt               Vallarta-WhereToGo.txt
Bahamas-WhatToDo.txt            Bermuda-history.txt             China-History.txt               Nepal-WhatToDo.txt
Bahamas-WhereToGo.txt           Boston-WhereToGo.txt            China-WhatToDo.txt              Nepal-WhereToGo.txt
Bali-History.txt                Budapest-History.txt            China-WhereToGo.txt             NewOrleans-History.txt
```
As you can see in this example, the Algarve-History.txt file was deleted from the directory through the single command. This is useful when you want to delete a specific file and know what it's called.

Example Use 2:
```
 $ cd written_2
 $ cd non-fiction
 $ cd OUP
 $ cd Abernathy
 $ ls
 ch1.txt         ch14.txt        ch15.txt        ch2.txt         ch3.txt         ch6.txt         ch7.txt         ch8.txt         ch9.txt
 $ find . -iname Ch15.txt -exec rm -i {} \; 
 remove ./ch15.txt? y
 $ ls
 ch1.txt         ch14.txt        ch2.txt         ch3.txt         ch6.txt         ch7.txt         ch8.txt         ch9.txt
```
In this example, we can see that when we combine the previous option with this one and use "-iname" instead of "-name", the command is not case sensitive and will delete the file that you write, even if you don't know what it's exactly called. This is useful as we can easily delete files and it's faster than finding the file before hand. 


As you can see, those are 4 options with the find command. They're all very useful in finding files and words, but these are not the only options. Hopefully this was enough information for you to find some files/directories!
