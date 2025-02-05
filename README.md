# ***Polymating User Guide for 1.0***
### _A page for user instructions and manuals_

Hello, MozzarellaARC here, we have finally come to the release of version 1.0.
For this version of Polymating, Johhny Boy will help us guide in version 1.0 [Alaskan Malamute - Johnny Boy](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204) please say hello to Johhny!

![1 0_Guide_Johnny_256](https://github.com/user-attachments/assets/c3fb3c70-3c2e-4c3a-b97a-d9af572b3bb0)

Before we start, I want to explain what Polymating is. It is a Blender retopology addon that uses a system similar to Blender's Shrinkwrap modifier. However, instead of a non-destructive retopology approach, Polymating updates all vertex transformations in real-time. Why? It was originally created to tackle a single problem: user event mismatch. As it evolved, Polymating began addressing another issue: integration.

As you know, Blender currently has three main modeling modes: Object Mode, Edit Mode, and Sculpt Mode. There is also an abundance of tools artists can use, not to mention the number of other modeling addons available. Polymating integrates with most of these tools because, at the core of the retopology pipeline, lies the projection of vertices and edge flow. This is where Polymating focuses its development.

Let's get started!!!

## What's new?

In Polymating 1.0 you have 4 main projection type to help your Retopology tasks, we call them ***Solver***

<p align="left">
  <img src="https://github.com/user-attachments/assets/552af735-b75c-4c70-8d23-7c0566f9db39" width="24%" />
  <img src="https://github.com/user-attachments/assets/5653fec1-aade-461f-989d-fe923dc6d483" width="24%" />
  <img src="https://github.com/user-attachments/assets/fca3b674-dca7-46b1-b297-a361a28ba85c" width="24%" />
  <img src="https://github.com/user-attachments/assets/f132a877-993f-4e09-9235-004038d65dfd" width="24%" />
</p>

Now let's take a closer look;
1. ***Force Project***, this is an original projection type that have been used for polymating 1.0 and below and this is the first of its kind, it forces all vertices to project to the reference surface on the go.
2. ***On-hit Limit*** similar to Force Project, except that it doesn't force all vertices on start, instead it limit constraints only happens when the vertex hits the reference surface
3. ***On-hit*** this is the bread and butter of Polymating 1.0 there is no actual projection but instead its only behavior is preventing the vertices to penetrates through the reference surface
4. ***Multi-hit*** similar to On-hit, but it uses all the object in a collection as reference, there is no handler to limit the amount of object in the collection so please be careful when using this, as it iterates through all your object in a collection, until multi-threading is implemented there is nothing I can do to fix this performance problem


## UI Introduction
Now that you have Polymating installed, let's take a look at how Polymating ui looks:

![ui_guide1x](https://github.com/user-attachments/assets/e89bb3a9-5dc4-4107-aac5-24d0db6d2d47)

UI map:
1. Apply overlay on start - When you press "Start Polymating" (11) it will automatically apply a material that is optimized for retopology and then turn on backface culling
2. Clamp brush strength - When you press "Start Polymating" (11) it will automatically limit some of your brush strength to 0.5 in order to tone down the sensivity that would result a very jumpy wrapping at higher strength
3. Color preferences - This is would be the default material color when you applying material either through "Apply overlay on start" mechanism (1) or "Apply Overlay" (13)
4. Reset Color - This will reset the "Color preferences" (3) at its default value of RGBA 0.800, 0.708, 0.323, 0.777
5. Experimenta Features - This is a collapsible menu to show or hide Experimental features
6. Use Raycast - This is solver specific preferences toggle for On-Hit and Multi-hit solver (10) that switch between the default find_nearest into ray_cast blender module, it is targeted to solve performance problem where user need more realtime interaction within edit-mode
7. Developer Extras - This is for me don't touch >.<
8. Reference - Use this object picker to select which reference you are going to project your vertices
9. Reference Visibility - After reference (8) is set you can use this to toggle hide or show your reference (8)
10. Solver - this is a drop down menu on which you can select your projection solver, currently contains Force Project, On-hit limit, On-hit and Multi-hit
11. Start Polymating - this is a toggle button, the main button to operate Polymating. It will show Start Polymating or Stop Polymating to tell you the state of the button
12. Info message - this is a message to show the state of Polymating, it roughly tells you what you need to do to operate Polymating
13. Apply Overlay - this button lets you apply an optimized material for retopology to your selected object
14. Remove Overlay- this button will remove all applied material created from Apply Overlay (13) or Apply overlay on start (1)
15. Overlay visibility - After overlay material is applied you can use this to toggle hide or show your object with overlay material
16. Selected vertex groups - this is where you select which vertex groups for vertex locking (18)
17. Axis - Multiple toggle button to select which axis you want to lock, if three button is toggled on it will lock the vertex in place
18. Lock Vertex - the operator button for vertex locking feature, this is a toggle button it will show the state on which the vertex is locked or unlocked

After everything is set, this is the default Polymating ui looks on your 3D viewport:

![ui_guide2](https://github.com/user-attachments/assets/449779d1-d295-4c0d-a7fb-54ada619af06)

Now that you've learn the naming of things and where things are placed, let's get to the first step to the Polymating retopology pipeline:

## Step 1 - Bounding boxes
This is the most crucial moment for the pipeline because when you retopologizing with Polymating you preplaned the the edge flow instead of thinkering it on the run. The benefit of this is that you have more control for the edge flow over the whole mesh because you start with relatively simple shape and put the details later on just like with what you do when doing modeling or sculpting in general, so here is the example of doing the bounding boxing to our friend Johhny Boy:

https://github.com/user-attachments/assets/a2ebbcab-b617-4d32-8697-9589fdcb011a

For reference on this part it will roughly take around 2 minutes to create the bounding box, and this video is 5x for github compression. So take it into consideration when you doing this for getting paid, because time is at the essence.

## Step 2 - The "Wrapping"
This is the heart and soul of polymating. On this part you will wrap the previous bounding box that you have made into our friend Johnny. Basically this is what polymating is made for and this would be the most fun part of Polymating pipeline, so take your time on this part: note here that, the less polygon you have the harder it is to wrapp into your mesh, so you have to take it into consideration and use about 1 level or 2 level of subdivision:

https://github.com/user-attachments/assets/c12a535b-4018-44f5-8f11-8faf74bc7a6f

So basically after you press "Start Polymating" you can go to sculpt mode and do smooth brush over the wack surface area with bad topology and arange it out to a beauty:
For reference on this part it will roughly take around 1 minute to do the wrapping and the draft wrapping. The video is speed up 2.5x

## Step 3 - The "Prepping"
On this part, you need to make preparation for the detailing because in bigger project or specifically project with symmetrical or asymmetrical shape it is generally best to do it by 1 side and the other side can copy, on this part you will also need to rearange some polygons for the missing shape that not get wrapped properly on previous part like the mouth, here we go:

https://github.com/user-attachments/assets/a6716eca-47f6-4b0c-a349-0d73cc40575c

https://github.com/user-attachments/assets/b26b18d1-a90a-4e68-a7ad-ccffb234eefe

so on this part it takes roughly 2 to 3 minutes of eyeballing game. Overall there is no certain limit to what extend of beauty that you aim to achieve.





Goodbye ["Johnny"](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204)
- - -

was extensively used for my other project, 
["Arctic Trailblazer"](https://www.artstation.com/artwork/0lod8y)
["Alaskan Malamute - Johnny Boy"](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204)
