# ***Polymating User Guide for 1.0***
### _A page for user instructions and manuals_

Hello, MozzarellaARC here, we have finally come to the release of version 1.0.
For this version of Polymating, Johhny Boy will help us guide in version 1.0 [Alaskan Malamute - Johnny Boy](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204) please say hello to Johhny!

![1 0_Guide_Johnny_256](https://github.com/user-attachments/assets/c3fb3c70-3c2e-4c3a-b97a-d9af572b3bb0)

Before we start, I want to give explanation of what is Polymating, it is a Blender retopology addon, that uses a system of that similar to Blender Shrinkwrap modifier, but instead of a non-destructive way of retopology, Polymating updates all vertices transformation in realtime, Why? it is originaly made to tackle a single problem which is user event mismatch, and as it grows Polymating try to tackle another problem which is integrations. As you can see Blender currently have 3 main modelling mode; object-mode, edit-mode and sculpt-mode and there is an abundance of tools that artists can use not to mention the amount of other modelling addon that the artists have. Polymating can integrates to most of those tools because at the core of Retopology pipeline is the projection of vertices and edge flow, Polymating focus on that.

Let's get started!!!


In Polymating 1.0 you have 4 main projection type to help your Retopology tasks, we call them ***Solver***

![solver_list](https://github.com/user-attachments/assets/6e39038a-38af-4365-aa2f-5a15389e53d4)

Now let's take a closer look;
1. ***Force Project***, this is an original projection type that have been used for polymating 1.0 and below and this is the first of its kind, it forces all vertices to project to the reference surface on the go.
2. ***On-hit Limit*** similar to Force Project, except that it doesn't force all vertices on start, instead it limit constraints only happens when the vertex hits the reference surface
3. ***On-hit*** this is the bread and butter of Polymating 1.0 there is no actual projection but instead its only behavior is preventing the vertices to penetrates through the reference surface
4. ***Multi-hit*** similar to On-hit, but it uses all the object in a collection as reference, there is no handler to limit the amount of object in the collection so please be careful when using this, as it iterates through all your object in a collection, until multi-threading is implemented there is nothing I can do to fix this performance problem

Goodbye ["Johnny"](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204)

- - -
Version 1.0 was extensively used for my other project, 
["Arctic Trailblazer"](https://www.artstation.com/artwork/0lod8y)
["Alaskan Malamute - Johnny Boy"](https://www.fab.com/listings/bb6b5598-f803-4b19-931a-b31051dba204)
