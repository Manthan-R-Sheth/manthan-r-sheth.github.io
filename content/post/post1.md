Project N.A.I.N.A.
===================


It stands for :- New Artificial Intelligence with Natural Augmentation.

The aim of the project was to make a cardboard app in which 3-D drawing could be done. This idea can then be extended to allow 3-D modelling of robots and other structures.

Tracking the users's hand motion.
-------------
> **Technology used :**

> - <kbd>IMU 6050</kbd> along with Arduino UNO.
	Difficulty in transferring the data obtained to the cardboard android app made me drop the idea of using the sensor. 
	
> - <kbd>Android Acelerometer</kbd> and Gyroscope data.
	The data provided by android's built in sensors is highly sensitive and callibrating it becomes very difficult. Double integrating it to obtain the distance co-ordinates is not possible as it leads to highly errornous data. This made me drop ths idea too.

> **Solution :** 

> -  Finally I made use of the concept of<kbd>Stereographic Vision</kbd>to overcome the problem. 
> Two webcams separated by a known distance can be appropiately used to get the exact 3 dimensional co-ordinates a point in space.

#### **More to the idea of Stereographic Vision.**

The concept is exactly what our eyes use to see things around us. Each webcam corresponding to each eye. Each webcam produces its own image of the same point in space. Trigonometric relations can then be used to get the exact space co-ordinates of the point.

#### **Determing a point corresponding to user's hand.**

Having figured out how to get the co-ordinates of the point in space, getting a point corresponding to the user's hand was the next task.

> - I used Image Processing for overcoming the task. 
> - Tracking a particular colour was the intial approach but background noises of the same colour were the major source of challenge.
> - Then the simple concept of luminous body was applied. A luminous body appears white to the webcam irrespective of anything else. So I pasted red coloured cellophane paper to the webcam to filter the actual white colour.
> - The only white colour seen by the webcams would be due to the luminous object and nothing else. (white colour would appear red to the webcams because of the cellophane filter).
> - OpenCV for JAVA was used to get the white object whose mean was then calculated to obtain a point.

Yipeeee!!!!! Hurdle 1 solved!!! :D 


Transmission Medium
-------------
Though not an issue but worth mentioning as it was a part of the project.

> Two ways that could be used for the purpose were :- 

> - Involving a third party server like a Python or NodeJS server.
> - Using Sockets - Server and Client Sockets.

Rendering the lines from the co-ordinates obtained.
-------------------

Once the co-ordinates are obtained from one of the above methods, the next and final task was to plot it in the cardboard android app.

> **Unity - A lucrative Choice!!**

> - Unity engine seemed a lucrative choice and it definitely made plotting easiar. But in the course if using it, two probably unsolvable issues arose.
> - Unity doesn't have the support for sockets. Third party libs like Unity Photon Network Lib need to be used. In my case the use of third party server was the solution. But.....
> - The Line Renderer in Unity which is used to draw lines between points works incorrectly when you want to draw discrete figures. Line Renderer draws lines continuously making the 3D drawing erronous in my case.

After a great deal of research on this...... finally figured a way out!!!

>  **OpenGL to the rescue!!**

>  I decided to shift from unity to OpenGL for android.
>  This solved both my problems. I could use sockets as well as could draw discrete figures using OpenGL.
>  The concept I used was to draw cubes with the co-ordinates obtained as the center of the cube. Keeping the size of the cubes quite small, series of cubes appeared like a continuous line.

Ahh!!! Work done!!!! 



Conclusion
-------------------
To sum it up, Project NAINA involved a wide dimension of technologies that was used to make it a successful product. At the end of the project, the user  (with a torch in his hand and in the field of view of the webcams) could move the torch and draw any pattern. This pattern could be seen in the in app running in the Virtual Reality Kit which made the user feel that he was drawing in a wide 3D space.
The idea could be extended to work wonders!!!





