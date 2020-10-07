Introduction: 

SE tools is a set of tools for Nintendo Switch game memory hacking. 

With SE tools you can search for memory location that will affect the behaviour of the game when modified and create cheat codes that modify these memory location. 

SE tools consist of two major components and some optional components.

EdiZon-SE is the memory searching tool. 

Pointersearcher-SE is the pointer searching tool. Many memory locations are dynamic and changes when the game relaunch and some even changes as the game progress. A pointer chain is required to locate these memory locaton. 

Here all the tools I made is package into one release for the latest version of atmosphere. 

Quick Start: 
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




This source can be found by following the individual link: 

https://github.com/tomvita/EdiZon-SE

https://github.com/tomvita/PointerSearcher-SE

https://github.com/tomvita/Atmosphere

https://github.com/tomvita/Noexes

