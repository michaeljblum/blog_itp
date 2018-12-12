+++
title = "Data Art Final"
date = 2018-12-12T14:51:01-05:00
tags = ["Data Art"]
categories = [""]
draft = false
+++

{{< youtube fCOz7escA_Q >}}
<br>

For my data art final, I wanted to build something that doesn't just live on a flat screen, but rather something that has depth and affords a greater range of experience than mouse/trackpad interaction, scrolling, scanning, etc. 

My attention, therefore, was turned toward VR (still technically based on a flat screen——or screens, namely two very little ones stationed an inch or so away your eyeballs, but offering a very different experience than that offered on personal computer nevertheless). 

I wanted build an experience that would allow the user to get some sense of the data that is maybe inaccessible when simply looking at and processing a visualization (bar chart, line graph, tree graph, etc.) on their laptop screen. A data visualization built for VR could allow for the user to feel the scale of the data more intimately or viscerally than might be possible in their more conventional, quotidian experiences with these aforementioned visualizations on screens. 

So I built a navigable, responsive data visualization in Unreal Engine 4, featuring meshes procedurally generated from climate change data and a motion controller pawn with a bespoke climbing locomotion system, effectively allowing——and inviting——the user to climb the data.

I wanted the user to develop a sense for the steep incline of the climate warming data by being tasked with exerting the energy to physically, manually scale it, thereby developing a more intimate, bodily understanding of the severity and rapidness of the change over time. 

Executing this idea involved a number of steps. 

1. Scale the climate change JSON data in D3.
2. Create a data struct in Unreal Engine 4 with variables that correspond to the keys in the JSON data.
3. Export the scaled JSON data from my D3/Jacvascript script, and import it into UE4 as a data table.
4. Create an actor blueprint and in its construction script procedurally create a series of meshes using the climate data as instructions——this process involves nested forEachLoops as well as a relatively complex negotiation of various UE4 blueprint nodes, from the handling of math and vector, location, and scale, to the iterating of specific rows and redirecting their outputs into the mesh generating nodes.
5. Create a climbing locomotion system that works across the BP_MotionControllerPawn and BP_MotionController blueprints, using casting as well as blueprint interfaces to communicate between each other as well as with the climable objects (BP_Climable). This system chiefly relies on the getting and setting of "climable" variables, as well as the storing of playing locotion and grip in order to calculate world position and move the pawn based on where the motion controllers pull it to (climbing, essentially).
6. Modify collision channels as well as tweak the MotionControllerPawn blueprint to allow to navigation on the procedural mesh data visualization (it is rare in VR to navigate between different planes of varying height——which is of course necessitate in the navigation between areas in the bar chart)
7. The cosmetic stuff: create labels for each year and the lowess mean temperature that corresponds to it for each "bar" in the visualization, as well as box collisions atop each bar so that when the user is atop that bar, the label illuminates somewhat.
8. Create a 2d real time screen capture——effectivelly a mirror——in which the user can gauge their path over and across the data. 

