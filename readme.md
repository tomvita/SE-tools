Introduction: 

SE tools is a set of tools for Nintendo Switch game memory hacking. 

With SE tools you can search for memory location that will affect the behaviour of the game when modified and create cheat codes that modify these memory location. 

SE tools consist of two major components and some optional components.

EdiZon-SE is the memory searching tool. 

Pointersearcher-SE is the pointer searching tool. Many memory locations are dynamic and changes when the game relaunch and some even changes as the game progress. A pointer chain is required to locate these memory locaton. 

Here all the tools I made is package into one release for the latest version of atmosphere. 

Quick Start: Search Memory
1. Assuming you already have atmosphere install. Copy the content of the zip files for the switch into the root of your SD card. Restart your switch.  
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
9. To test whether this is the real deal. Change the game state and see if "import" points to the gold.
10. Turns out that this pointer chain is only valid when some gold has been spend. The screen shot shows the pointer chain is able to resolve into the correct address of "gold3". 

Quick Start: Create cheat code
1. Edit the bookmark label to what you want to show as the cheat code label. 
2. Edit the value of memory to what you want the code to set.
3. To create cheat code choose the bookmark and press "Y". This will create a cheat code with the bookmark's label and set it to the current value at the memory location. 
4. Press "ZL"+B to quite and reload to see the cheat code appear on the cheats section
![2020100716491900-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/95308950-1b03b100-08bd-11eb-830f-98c1101ce1fc.jpg)

Quick start Unknown value search:

Here we use the game "Zombie Blast Crew"
![2020111618545200-8A979FD4D8350EA4A40B19001182DC1A](https://user-images.githubusercontent.com/68505331/99244931-c0eff700-283d-11eb-8950-58692275c64a.jpg)
The life bar has the value of 1400. But after some direct value search we can't find a memory location that can be used to change this value.
We now try unknown value search as the representation isn't direct. 
![2020111622344400-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/99265093-42ef1880-285c-11eb-968f-d7e9f7151a74.jpg)
![2020111618393100-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/99261344-8abf7100-2857-11eb-932a-c4d4440ec17e.jpg)
After the current value has been dumped go back to the game and let the life bar reduce a bit.
![2020111618395100-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/99261499-c5c1a480-2857-11eb-903d-907afa158fab.jpg)
Continue with [--] search. 
You will need to do [--] or [++] search until the candidate list is reduced to a manageable amount. 
Recover HP with potion if needed. In general you should not allow the character to die because the address may change. In this case 
it does not change if you die but at this stage you won't know yet.
![2020111618452800-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/99262910-7b412780-2859-11eb-9b66-4b0f198eddfa.jpg)
![2020111618452600-CCFA659F4857F96DDA29AFEDB2E166E6](https://user-images.githubusercontent.com/68505331/99263102-b6dbf180-2859-11eb-88a8-1880eddf1e62.jpg)
Now that there is not that many candidate left it's time to take a look at them. 
Those that looks promising you have to hack them to see if it works. 
Sometimes hacking value may cause the switch to crash. It is just too bad that the progress would be lost. This is a hazard that 
cannot be avoided. 
After some trial and error you will find that hacking the two value that is close to the display value divided by 10 makes a difference.
One will keep you alive and the other will affect the life bar but you will still die. 
Freeze both value will give you infinite HP. You will find that the life bar don't directly correspond to the value that affects the life
bar. This is rather common. In this case probably the code only update the life bar when there is change and it put up the value you 
hack - HP that was just lost. 
Now with these two memory found you are ready to proceed to find pointers for these two value.

Quick start moon jump search:
1. For some games you can find moon jump this way. Please note that this isn't applicable to all games. 
2. For many game a floating point number is added to make the character rise or fall.
3. Press the jump button. Make sure the character is on the rise then pause the game. Do a range search. 
4. Next pause the game when the character is falling. Do a range search of the opposite polarity. (i.e. if you search for a positive range now search for a negative range and vice versa). 
5. Repeat step 3 and 4 until you narrow down to a small candidate list. 
6. Pause the game while the character is on the rise. Go to the candidate list and freeze a few of them. Go back to the game and see if the character keep rising continously. If it does one of the candidates you frozen is the moon jump memory location. Now unfreeze them one by one until the character stop rising. If nothing happens continue until the candidate list has been exhaused. 
7. If you found the address proceed with step 8, if not repeat from step 3 with a different range, polarity or datatype, bear in mind that this method is not applicable to all games.
8. Added the found address to bookmark and label it moon jump. 
9. Go to the bookmark you just added. Edit the value to a value you want this moon jump to be (how fast the character will rise). Press ZL+A to add this to code. Press ZL+B to reload dmnt and see that a new code has been added to the cheat code list.
10. Choose this code you just created. Press Rstick to assign a moon jump button. Enable this code and test your newly created moon jump.
11. Repeat from step 9 and 10 if the value you set don't work well. When you are satisfied with you moon jump proceed to next step. 
12. The memory location you found is not static in most cases. You may have to replace the static memory with a pointer. Once you found the pointer you can either replace the static code or repeat step 7 to 10. 








This source can be found by following the individual link: 

https://github.com/tomvita/EdiZon-SE

https://github.com/tomvita/PointerSearcher-SE

https://github.com/tomvita/Atmosphere

https://github.com/tomvita/Noexes

