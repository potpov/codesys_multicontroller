i didn't find a lot of examples about connecting more than 2 controllers in codesys, so i thought someone might be finding this useful.

as codesys has its own standards i cant show the source code directly. you can download the project and import it (i'll upload some snapshots here btw).

this project has been tested on codesys V3.5 SP12 patch 4.
there shouldn't be any conflicts when importing the project but you might be having some issues whenever trying to lunch the simulation over a different codesys version. in this case i suggest you to create a new project in another codesys window, create all the files and copy the code directly from your previous codesys window: that should fix the problem.

in this simulation the main controller is handling all the little entities like buttons, scanners, etc but it's also communicating with the second controller. second controller's task is to move correctly the position of the arm and open/close the robotic hand.

the project has a 3-layers depth so that main controller has to be able to read data coming up from the robotic arm throught the second controller.

above you can find some snaps, the demo video and the Whole State-Chart for this project.

just a little note about errors:
there's a graphic interface where you can handle the inputs for 
1. the "weight system" (which should check if there's a new item on the supply chain)
2. the start button
3. the item ID (A, B, C are allowed types)
4. the scan ID (the arm checks if the item is the same of (3)
5. reset button, in case of error

error are raised whenever:
1. start button is pressed and no items are detected
2. scan code differs from item ID

Whole State-Chart

![alt text](https://ibin.co/4jnbh1GERq1e.jpg)

plc prg file

![alt text](https://ibin.co/4jnailGA7IVK.png)

main controller

![alt text](https://ibin.co/4jnb4cHnGywQ.png)

second controller

![alt text](https://ibin.co/4jnbKEA6NyoA.png)

arm controller

![alt text](https://ibin.co/4jnbuRdNRhag.png)

graphic demo

[![](http://img.youtube.com/vi/Pl7ywRZvZgU/0.jpg)](https://www.youtube.com/watch?v=Pl7ywRZvZgU "demo")

