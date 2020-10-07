Introduction: 

SE tools is a set of tools for Nintendo Switch game memory hacking. 

With SE tools you can search for memory location that will affect the behaviour of the game when modified and create cheat codes that modify these memory location. 

SE tools consist of two major components and some optional components.

EdiZon-SE is the memory searching tool. 

Pointersearcher-SE is the pointer searching tool. Many memory locations are dynamic and changes when the game relaunch and some even changes as the game progress. A pointer chain is required to locate these memory locaton. 

Here all the tools I made is package into one release for the latest version of atmosphere. 

Quick Start: Search Memory
1. Assuming you already have atmosphere install. Copy the content of the zip files for the switch into the root of your SD card. 
2. Launch the game. Press "HOME" when there is something interesting you want to search. Press "up" then "A". 
3. Take the example of the game "Kingdom Rush Frontiers" and we will search for the amount of gold you have. You will see the following screen. 
![2020100712584600-6F1404E6C8413C7EFF592CBB30E5AB96](https://user-images.githubusercontent.com/68505331/95290669-5e9bf200-08a0-11eb-8815-962d98e98fb3.jpg)
![2020100712574900-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95290660-5b086b00-08a0-11eb-9578-754f4bdb8b8a.jpg)
4. Press "Y" and "L" and "R" to navigate the setup for search. 
![2020100713292000-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291040-3c56a400-08a1-11eb-95c1-22e05b93a0ad.jpg)
![2020100713292200-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291048-3fea2b00-08a1-11eb-90ab-fd611eaedd4f.jpg)
![2020100713292400-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291052-42e51b80-08a1-11eb-8b1b-180cbf997d7b.jpg)
![2020100713292900-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291054-45477580-08a1-11eb-90d1-51139f5cb906.jpg)
5. Data Type is how the data is represented in memory. You have to make a guess what type it is. A good starting point is u16. (If that does not work try "flt" and "dbl" next). 
6. Mode is how the content of memory is to be compared with the value you enter. In this case the value can been seen on game screen to be 840 so we choose "==".
7. Region is where the app will search. Choose "HEAP+MAIN" unless you already know where it is located. 
8. In the VALUE tap press "A" to enter the value 840. Highlite the "Search Now!" box and press "A". after a few second you will see that some candidates has been found. 
9. Go back to the game (press "HOME" and "HOME"). Spend some gold. 
10. Press "HOME" then "UP" then "A". Press "Y". Enter the new value. Search again and this time you will find that there is only a few candidates left. Go back and repeat from Step 8 if there is too many candidate.
11. Now select one of the candidate and press "A" to modify the value. Go back to the game and see if you have found the right memory location. 
12. Now that the memory location is found the next step is to add it to bookmark by press "+" and enter a label. Press "L" to toggle bookmark view. 
![2020100713350000-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291368-f2ba8900-08a1-11eb-9986-85317065a69d.jpg)
13. Since we use data type u16 to perform the search you can see on the status line above that the address relative to Heap and that the type is u16. Press "RStick" and take a look at the memory editor. 
![2020100713421400-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95291857-f3075400-08a2-11eb-9d0e-b3b4c1743565.jpg)
14. Since the value of the upper order bytes are zero maybe the datatype is u32. Go back to bookmark view. Press "ZL"+"R" to change the datatype to u32. Now enter a large value and see what happens. We have confirm that the data type is u32. 
![2020100713502000-6F1404E6C8413C7EFF592CBB30E5AB96](https://user-images.githubusercontent.com/68505331/95292469-18489200-08a4-11eb-9d85-bf48c81904d4.jpg)
15. Next we test if this memory location is dynamic. Let try "RESTART". The memory looks to be the same. How about "QUIT" and come back. Now we see the memory location is no longer valid. We will need pointer in order to not need to keep repeating the search in this case. 
![2020100714035600-6F1404E6C8413C7EFF592CBB30E5AB96](https://user-images.githubusercontent.com/68505331/95293438-fd771d00-08a5-11eb-84b4-b51f814248be.jpg)  
16. We proceed to find the new memory location. 
![2020100714071100-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95293656-71b1c080-08a6-11eb-8e15-c87bea8476fc.jpg)

Quick Start: Search Pointer Chain
1. Next we will use the pointer searching tool on PC. Launch either pointersearcher.exe or pointersearcher64.exe (will need this for cases where more that 4Gbyte of memory is needed). Click on "Attach dmnt". 
2. Fetch bookmark from EdiZon SE.
3. Copy and paste into the TargetAddress1. Click on "Dump Ptr".
4. When the dump is complete click on "Reset and Search". Adjust MaxDepth, OffsetNum and OffsetRange until candidates are found. In this example many targets are found.
5. To perform a second dump go back to the game make the memory location of gold change. Now we have "gold2". Select "File2" and click on "Dump ptr" to make the second dump. Click on "Narrow Down Result" to reduce the number of targets.
6. Click on "Export To EdiZon SE" to export the result ready for EdiZon SE to import into bookmark.
7. Clock on "Push Export to EdiZon SE" which will push the file over to the switch.
![pointer search example](https://user-images.githubusercontent.com/68505331/95306963-a3cd1d80-08ba-11eb-877c-ad2a09db6428.png)
![2020100714071100-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95307071-c4957300-08ba-11eb-9f99-dfe38ee72172.jpg)
![2020100716351100-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95307360-1ccc7500-08bb-11eb-920c-ae166a052187.jpg)
8. On the switch press "ZL"+"+" to import bookmark. The imported bookmark has the label "import"










This source can be found by following the individual link: 

https://github.com/tomvita/EdiZon-SE

https://github.com/tomvita/PointerSearcher-SE

https://github.com/tomvita/Atmosphere

https://github.com/tomvita/Noexes

