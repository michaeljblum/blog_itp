+++
title = "Immersive Sound Design for 3D Environments"
date = 2018-10-12T17:52:52-04:00
tags = ["Immersive Sound"]
categories = [""]
draft = false
+++

![heropic](/images/uploads/immersivepink.png)

 This class—<i>Immersive Listening: Designing Sound for VR</i>—primarily emphasizes working with sound—composing, generating, refining, augmenting, and spatializing sound, as well as positioning it in 3D space.

That being the case, the two assignments I completed over the course of the past two weeks revolved more around generating and processing sound than they did around creating compelling environments and interesting interactions in Unreal Engine 4, the game engine in which we're tasked with designing our experiences.

The two experiences below, moreover, were designed using the first-person template in UE4, as it is not until the following week's assignment that we will be designing sound for experiences intended for VR. 

{{< youtube 6bAy8VmUeXQ >}}
<br>

My primary goal with this first piece was familiarizing myself with Audacity and creating "moving" sounds using the blueprint visual scripting language in UE4. 

All the sounds used in this piece are derived from various sound libraries. Most of the sounds have been heavily processed in Audacity (one of the booming, static-y sounds, for example, was originally a field recording of flowing water), while others were only minimally touched up (the guitar sound that plays at the location of the player start was only given a mild reverb and echo-y sort of dampening effect). 

The hovering, mobile orbs in the scene were animated using a timeline and a customized spline system, while the sounds that these orbs emit were programmed to follow their parent orb's location as they progress through the spline's path.

In terms of visuals, I tweaked the exponential height fog in a number of ways, and generally messed with the lighting, in order to give the scene an eerie, sort of washed out vibe.

{{< youtube 7f7f-4vQ-aY >}}
<br>

All the sounds in this second piece were composed by myself using the modular, open-source synthesized VCV Rack. I spent many hours experimenting with this highly flexible and addicting software, creating all kinds of sounds (from 8-bit video game-style music to horror ambiance, dreamy poppy sounds, ~1970s synthy music, as well as a lot of pure noise garbage) and downloading a handful of third-party plugins, extending the software's core functionality.

My initial idea for this piece was to create a sort of symmetry between the sine waves in my sound recordings and the sine waves I sometimes use in my materials in UE4 (sine waves can be used to make materials pulsate, which can be soothing, aggressive, or anywhere in between). After playing with this effect some, I ultimately decided to soften it greatly because it was *just* a little too aggressive, particularly on the sound side of things.

So I went with a more melodic sounding piece for the primary "music" of the scene, and only made a couple of the materials pulsate and glow using sine waves and emmisive color.

As for the sounds—a somewhat moody sound piece plays at the player's start location. There are four rotating platforms that the player is expected to jump up to (I tweaked the jumping mechanics and gravity in order to mimic the locomotion of a platformer-style game). On each of these four platforms, a progressively more dramatic variation of the same musical piece plays. On the topmost platform, a final piece plays, which is more gamey and fun in spirit than the previous several, indicating a sort of "win" state. (You can find a screenshot of my workspace in VCV Rack during the composition of these sounds below.)

The piece also has a sort of "8-bit" graphical style, the product of a post-processing shader material I created and set to unbounded, affecting the entirety of the environment.

![vcvpic](/images/uploads/vcv1.png)