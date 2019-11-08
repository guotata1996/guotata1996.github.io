## Some reflections on the old version

A few decisions made at the early stage of the last branch undermines the feasibility of further development:
### The Road-Crossroad representation turned to have lots of tricky issues.

![image](https://user-images.githubusercontent.com/12555907/68507797-bcf8c480-023a-11ea-8f37-4a152c9af471.png)

Takes the crossroad on the left as an example. The Road-Crossroad representation only uses 4 roads and 1 node to express
the complex logic of a crossroads, thus the code for the node was super complex. To make things worse, it's even harder to design a viable UI for editing the node. With so many variables to control, it would be a big pop-up window that drives
the user mad in a minute.

On the RHS is the new _Link-Node_ representation. A link can be one or more one-way lanes that lead traffic to
one node to another. A turn-left lane, for example, goes towards a different link from a turn-right lane. This idea is borrowed
from the [CityBound](https://github.com/citybound/citybound) project, plus a slight change that allows a link to have multiple lanes. Vehicles can switch between lanes as long as they belong to the same link. This way, we have 7 nodes to deal with, 
making each of them understandable and editable.

### The Play-mode workstyle missed so much convenience provided by Unity Editor
I got fascinated by the power of a well-customized Unity Editor once I watched the [MegaCity](https://unity.com/megacity)
presentation. Although I'm still a newbie in this area, it has already brought so much convenience to my development. The changes we made are saved in the RAM, which is really FAST. Even better, we no longer have to care about (de)serialization.

![image](https://user-images.githubusercontent.com/12555907/68509245-8755da80-023e-11ea-9ee6-2bfccef512f8.png)

The second advantage of Unity Editor is that it is born with a well-organized UI, which means we can focus on the main logic
instead of UI design. The transform editing tools, multi-window layout, and many more things are what a developer really needs,
although it doesn't look as pretty as the playmode UI. For instance, if I want to add an "Add Lane" button, that's only several
extra lines of code in the UnityEditor component, while it means carefully placing some buttons/windows + events or even managing a state machine in Play mode.

### The sweet but deadly variability of building block classes
![image](https://user-images.githubusercontent.com/12555907/68511505-1e716100-0244-11ea-8975-052236f47729.png)
The curve class of the old version is variable: if you change any of its control points, it will do a resample and tell its
owner recursively about what happened. My initial consideration was to save the objects from being destroyed and created again,
as in the static case. However, this turns out to be a headache for the owners to handle the changes, especially when a change
is fundamental. The new version abandons this feature and keeps everything static -- as simple as possible.

## What the new version is gonna focus on
### A customized editor that supports network editing on a large scale.
With the current editor extension, I was able to fully configure the following map with multiple roads with a simple crossroads in serval minutes, which is
already 3x faster than the old version, but there's still room for improvement. 
![image](https://user-images.githubusercontent.com/12555907/68513443-051ee380-0249-11ea-9fba-b8718da5c854.png)

### A faster surrounding-query API for vehicle AI
I keep track of six neighbors constantly, like what a typical driver does. In most of the cases such as taking over neighbors or joining new roads, an update only takes constant time, while lane switching can be a bit harder, but hopefully, we can achieve good frame-average time cost since one doesn't switch lanes all the time!
![image](https://user-images.githubusercontent.com/12555907/68512905-a5740880-0247-11ea-8aaf-4d7e432ced0b.png)

### Better vehicle AI
This is the ultimate goal of the work done before.
Smart AI could display aggressive driving behavior, instead of simply following their path. Otherwise, the game is certainlly
boring to play.
![image](https://user-images.githubusercontent.com/12555907/68513793-eec55780-0249-11ea-91fb-eb1e07104cf3.png)
