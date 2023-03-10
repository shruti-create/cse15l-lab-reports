# Week 6 Lab Report
## Researching the grep Command-line Options

## Option 1: grep -v <Name of Directory/File>

Source: https://en.wikibooks.org/wiki/Grep

Function: This option causes the Grep command to list out all the files/directories in the directory you use it in, except for the file/directly you write next to the -v portion of this command. This is useful if you are looking for many files, but not looking for a file, or a couple files, and do not want to see them when you display all the files, so that you find the files you're specifically looking for. 

Example Use 1: 
 ~~~
 $ cd skill-demo1-data
 $ cd written_2
 $ ls
 non-fiction     travel_guides
 $ ls|grep -v travel_guides
 non-fiction
 ~~~
As you can see in the example, it removes the travel_guides directory when listing directories, as we decided we didn't want to look in there, so it made it easy to find the non-fiction directory. 

Example Use 2: 
 ~~~
 $ cd non-fiction
 $ cd OUP
 $ ls
 Abernathy       Berk            Castro          Fletcher        Kauffman        Rybczynski
 $ ls|grep -v Fletcher
 Abernathy
 Berk
 Castro
 Kauffman
 Rybczynski
 $ cd Abernathy
 $ ls
 ch1.txt         ch14.txt        ch15.txt        ch2.txt         ch3.txt         ch6.txt         ch7.txt         ch8.txt         ch9.txt
 $ ls|grep -v ch15.txt
 ch1.txt
 ch14.txt
 ch2.txt
 ch3.txt
 ch6.txt
 ch7.txt
 ch8.txt
 ch9.txt
 ~~~
As you can see in this example, we used the command to remove the directory Fletcher from the display, which would help us as we wouldn't accidentlly see it in our search for the file that we wanted and then we removed the text file ch15.txt, as we didn't want to see that file in our display, so we filtered it out. 

## Option 2: grep -e <"Pattern">

Source: https://linuxcommand.org/lc3_man_pages/grep1.html 

Function: This option causes the Grep command to list out all the files/directories that have the same properties as the pattern written after the -e in the command. This is useful if you're looking through many files, but really are searching for files that aare all with the same type of starting pattern. 

Example Use 1: 
 ~~~
  $ cd skill-demo1-data
  $ cd written_2
  $ cd travel_guides
  $ cd berlitz1
  $ ls
  HandRHawaii.txt         HistoryFWI.txt          HistoryMalaysia.txt     IntroLakeDistrict.txt   WhatToIndia.txt           WhereToGreek.txt
HandRHongKong.txt       HistoryFrance.txt       HistoryMallorca.txt     IntroLasVegas.txt       WhatToIsrael.txt        WhereToHawaii.txt
HandRIbiza.txt          HistoryGreek.txt        IntroDublin.txt         IntroLosAngeles.txt     WhatToIstanbul.txt      WhereToHongKong.txt
HandRIsrael.txt         HistoryHawaii.txt       IntroEdinburgh.txt      IntroMadeira.txt        WhatToItaly.txt         WhereToIbiza.txt
HandRIstanbul.txt       HistoryHongKong.txt     IntroEgypt.txt          IntroMadrid.txt         WhatToJamaica.txt       WhereToIndia.txt
HandRJamaica.txt        HistoryIbiza.txt        IntroFWI.txt            IntroMalaysia.txt       WhatToJapan.txt         WhereToIsrael.txt
HandRJerusalem.txt      HistoryIndia.txt        IntroFrance.txt         IntroMallorca.txt       WhatToLakeDistrict.txt  WhereToIstanbul.txt
HandRLakeDistrict.txt   HistoryIsrael.txt       IntroGreek.txt          JungleMalaysia.txt      WhatToLasVegas.txt      WhereToItaly.txt
HandRLasVegas.txt       HistoryIstanbul.txt     IntroHongKong.txt       WhatToDublin.txt        WhatToLosAngeles.txt    WhereToJapan.txt
HandRLisbon.txt         HistoryItaly.txt        IntroIbiza.txt          WhatToEdinburgh.txt     WhatToMadeira.txt       WhereToJerusalem.txt
HandRLosAngeles.txt     HistoryJamaica.txt      IntroIndia.txt          WhatToEgypt.txt         WhatToMalaysia.txt      WhereToLakeDistrict.txt
HandRMadeira.txt        HistoryJapan.txt        IntroIsrael.txt         WhatToFWI.txt           WhatToMallorca.txt      WhereToLosAngeles.txt
HandRMadrid.txt         HistoryJerusalem.txt    IntroIstanbul.txt       WhatToFrance.txt        WhereToDublin.txt       WhereToMadeira.txt
HandRMallorca.txt       HistoryLakeDistrict.txt IntroItaly.txt          WhatToGreek.txt         WhereToEdinburgh.txt    WhereToMadrid.txt
HistoryDublin.txt       HistoryLasVegas.txt     IntroJamaica.txt        WhatToHawaii.txt        WhereToEgypt.txt        WhereToMalaysia.txt
HistoryEdinburgh.txt    HistoryMadeira.txt      IntroJapan.txt          WhatToHongKong.txt      WhereToFWI.txt          WhereToMallorca.txt
HistoryEgypt.txt        HistoryMadrid.txt       IntroJerusalem.txt      WhatToIbiza.txt         WhereToFrance.txt
  $ ls|grep -e "History"
  HistoryDublin.txt
  HistoryEdinburgh.txt
  HistoryEgypt.txt
  HistoryFWI.txt
  HistoryFrance.txt
  HistoryGreek.txt
  HistoryHawaii.txt
  HistoryHongKong.txt
  HistoryIbiza.txt
  HistoryIndia.txt
  HistoryIsrael.txt
  HistoryIstanbul.txt
  HistoryItaly.txt
  HistoryJamaica.txt
  HistoryJapan.txt
  HistoryJerusalem.txt
  HistoryLakeDistrict.txt
  HistoryLasVegas.txt
  HistoryMadeira.txt
  HistoryMadrid.txt
  HistoryMalaysia.txt
  HistoryMallorca.txt
  ~~~
As you can see above, there were many files, but after using the command, we were able to narrow the search down to a couple files. In this case, we were looking for the history files and with the -e, we were able to find them.

Example Use 2: 
 ~~~
  $ cd skill-demo1-data
  $ cd written_2
  $ cd travel_guides
  $ cd berlitz1
  $ ls|grep -e "HistoryM"
  HistoryMadeira.txt
  HistoryMadrid.txt
  HistoryMalaysia.txt
  HistoryMallorca.txt
 ~~~
As you can see above, we were able to narrow down our search even more when we looked with the pattern "HistoryM" as it then only gave us the history files for the places with names starting with M. 

## Option 3: grep -w <"word"> 

Source: https://www.ibm.com/docs/en/aix/7.2?topic=g-grep-command#grep__row-d3e144005

Function: This option causes the Grep command to find any file/directory with the word in it and return those file names. It is case sensitive to the word. This is useful when you're looking for a specific type of file/directory and can find it with a specific word. 

Example Use 1:
~~~
  $ cd berlitz2
  $ ls|grep -w "History"
  Algarve-History.txt
  Amsterdam-History.txt
  Athens-History.txt
  Bahamas-History.txt
  Bali-History.txt
  Barcelona-History.txt
  Beijing-History.txt
  Berlin-History.txt
  Budapest-History.txt
  California-History.txt
  Canada-History.txt
  CanaryIslands-History.txt
  Cancun-History.txt
  China-History.txt
  Costa-History.txt
  CostaBlanca-History.txt
  Crete-History.txt
  Cuba-History.txt
  Nepal-History.txt
  NewOrleans-History.txt
  Poland-History.txt
  Portugal-History.txt
  PuertoRico-History.txt
  Vallarta-History.txt
~~~ 
In this example, we can see that all the files with "History" are shown, which would be useful if we're looking for only history files. 

Example Use 2:
~~~
  $ cd berlitz2
  $ ls|grep -w "California"
  California-History.txt
  California-WhatToDo.txt
  California-WhereToGo.txt
~~~
In this example, we can see that all the files with "California are shown, which would be useful if we're only looking for information on California. 
  
## Option 4: grep -i <"word">
Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html

Function: This option causes the Grep command to find any file with the word in it and return those file/directory names. The reason this is different from the last one is that it is not case sensitive in finding. This is useful when you're looking for a specific type of file/directory and can find it with a specific word. 

Example Use 1:
~~~
 $ cd travel_guides
 $ ls|grep -i "Berlitz"
 berlitz1
 berlitz2
~~~
In this example, it found both the directories, even though we searched for the word "Berlitz", which is the capitalized version of the directory. This would very useful if we forget the exact cases of the directories/files we look for. 

Example Use 2:
~~~
 $ cd travel_guides
 $ cd berlitz1
 $ ls|grep -i "history"
 HistoryDublin.txt
 HistoryEdinburgh.txt
 HistoryEgypt.txt
 HistoryFWI.txt
 HistoryFrance.txt
 HistoryGreek.txt
 HistoryHawaii.txt
 HistoryHongKong.txt
 HistoryIbiza.txt
 HistoryIndia.txt
 HistoryIsrael.txt
 HistoryIstanbul.txt
 HistoryItaly.txt
 HistoryJamaica.txt
 HistoryJapan.txt
 HistoryJerusalem.txt
 HistoryLakeDistrict.txt
 HistoryLasVegas.txt
 HistoryMadeira.txt
 HistoryMadrid.txt
 HistoryMalaysia.txt
 HistoryMallorca.txt
~~~
With this example, we can see that it found all the files with the word "history" in it, even though the files actually have the word "History" in them, as it is not case sensitive.  

---
As you can see, those are 4 options with the grep command. They're all very useful in finding files and words, but these are not the only options. Hopefully this was enough information for you to find some files/directories!
