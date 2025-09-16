# Henry-Taylor-2206046-Technical-Art-Development-Commentary

# Technical Art Development Commentary

**Unit Name:** Technical Art 24-25 FGCT5016

**Student Name:** Henry Taylor

**Student ID:** 2206046

**Total Word Count:** \[2029]

**Documentation Link:** https://github.com/Ramphoryncus/TechnicalArt_24_25_Copy/blob/GitMain/README.md

**Repository Link:** https://github.com/Ramphoryncus/TechnicalArt_24_25_Copy

**Build Link:** https://ramphoryncus.itch.io/indigo-charger

**Video Demonstration Link:** https://drive.google.com/file/d/1L5X_Y1mxgZnPHIaEqiTAQqOWj3VAOeTj/view?usp=drive_link

---

## Abstract


The task was to create a game and subsequently a final playable build in Unreal Engine 5 based on the theme Alive. We were free to interpret what this might mean to produce a real-time interactive experience. We would have to implement at least two of the following: Procedural Content Generation; Complex Materials and Shaders; Visual Effects (Niagara or Cascade); Performance Optimisation. My goal was to produce a playable level with obstacles and interactive elements and to create a new kind of super anti-hero, based on electricity and speed (running really fast), as the playable character. I approached it in two ways, from a player’s perspective concerning controls, animations and interactive elements, and from an artist’s, making original 3D models with “hand-painted” textures that would populate my three-dimensional environment. The final outcome did not end up having everything that I would like to have included but it is playable and functional. I had intended to use the Niagara system to create lightning bolts and orbs that the character would “throw”, and to implement a custom gravity so the player could run at high speeds on the walls of the final area. I created the lightning orbs using a complex material, the custom gravity was not included in the final build but I did achieve most of what I set out to do.

---

## Research


I explored three video games, *Titanfall 2* (Respawn Entertainment, 2016), *DeathSprint 66* (Sumo Digital (Newcastle), 2023), *Tron RUN/r* (Sanzaru Games, 2016), I also considered *The Flash* (Warner Bros. Television, 2014-2023) and *Event Horizon* (Paramount Pictures, 1997).

---
*Titanfall 2* (Respawn Entertainment, 2016) is widely regarded as one of the finest examples of a single and multiplayer video game experience. Respawn Entertainment crafted something special, lightning in a bottle.

- Wall running mechanic, with believable limitations, some of the best in the business
- Fluid character movement, also some of the best in the business

I could only hope to achieve something as good as this, not wanting to set my sights too high, this is purely for a reference of what is possible.

---
*DeathSprint 66*(Sumo Digital (Newcastle), 2023) is a fast-paced PvP racing game in the “runner” genre. The players race around tracks on foot which have difficult traversals and deadly traps littering them. The player gains power ups and can use them to benefit themselves or to attack the other runners depending on the type of power up. This is a slick third person game, very enjoyable.

- Wall running mechanic which appears to be active until the wall runs out
- You gain speed the longer you stay out of trouble but there is a limit to the speed
- Deadly traps

This game comes close to what I had in my mind in terms of movement and wall running. It has nice animations and good controls and a good gameplay loop. This was rattling around in my subconscious, I suspect, when I was constructing my animation blend space.

---
Tron RUN/r (Sanzaru Games, 2016) is a medium paced “on rails” running game. The player runs at a set speed and they have to run, slide, jump and dodge to the exit. Jumping and gliding over large gaps, dodging obstacles and enemies, or destroy the enemies and obstacles with your disc, collecting “bits” along the way. The controls are not too complicated, but it is not easy.

- Challenging obstacle placement
- Nice visuals (because it’s Tron if you like that sort of thing)

This was relevant for obstacle placement in my level, not as easy as it may look. It was all a matter of flow, where the platforms and hazards should be placed,  to make the player think rather than just run and jump and slide. From the looks of my character there was definitely some influence from the Tron universe.

---
*The Flash*(Warner Bros. Television, 2014 to 2023) was the underlying template for my character. He gets his powers after a freak accident. He can run really fast, the friction from his super speeds generates electricity which he can throw like lightning. He also has accelerated healing, he can see the world in super slow motion.

- He runs really fast
- Can throw lightning
- Has cool suits

The Flash is totally relevant with the superspeed and lightning throwing. For my character I did not want time to slow down or for there to be accelerated healing, I wanted there to be consequences for irresponsible speeding. My first 3D mesh that I made for charger had lightning bolts on his boots, ears and one on his chest, I was advised against copyright infringement and I like purple more than red, so he got a makeover.

---
*Event Horizon* (Paramount Pictures, 1997), this is one of the best space horror movies with excellent set design, which is what inspired me create my gyroscopic sphere and the rotating tunnel that looks like an inverted buzzsaw. I watched the Blu-ray extra on set design and construction which helped me fine tune my 3D meshes. I replicated their visual appearance and motion too.

---
## Implementation

I started with the gyroscopic portal (figure 1) using Add Local Rotation and a parent-child hierarchy with the base as the parent and the sphere as the final child. I also used individual floats to adjust each ring’s and the sphere’s rotation speed. I came back to this at the end and added a stop rotation and a return to starting rotation when all four pillars are activated with a visibility change to the sphere and spawn a particle portal (figure 5) created in Niagara thanks to RedefineFX YouTube channel (figure 5.1).

<img width="882" height="946" alt="Portal" src="https://github.com/user-attachments/assets/2f6939c7-54c1-49ae-91d7-e26c31286c72" />

Figure 1: Gyroscopic Portal https://blueprintue.com/blueprint/z6r3w0bn/

I then moved on to the rotating tunnel (figure 2) and used Add Local Rotation On Event Tick with an adjustable rotation speed variable. I added the invisible plane at the end, I was always going do this, in an attempt to disorient the player.
<img width="892" height="1158" alt="RotatingTunnelAndInvisiblePlane" src="https://github.com/user-attachments/assets/587b18ed-fee3-44ce-bb90-c3c9d9833b71" />

Figure 2: Rotating Tunnel (with invisible plane) https://blueprintue.com/blueprint/tkuszww7/


For the Buzz stack (figure 3), single buzzsaw and tenderiser (figure 4)  Add Local Rotation on Event Tick but I added an On Component Hit > Cast To Character> Destroy Actor. For the swinging hammers (figure 4) I initially used a Timeline to swing the hammers back and forth but when it came to adding force with Launch Character the player would shoot off in unexpected directions no matter which side of the hammer they got hit by, so I went back to the trusted Add Local Rotation so they would do 360° of rotation and every other hammer I rotated 180° so the player can only get hit in one direction by a specific hammer.

<img width="852" height="612" alt="BuzzsawStack" src="https://github.com/user-attachments/assets/73774fe1-8dc1-4078-a5c4-d58022d6d49e" />

Figure 3: Buzzsaw Stack https://blueprintue.com/blueprint/7m_f-8ko/

<img width="899" height="918" alt="HammersAndBuzzsaws" src="https://github.com/user-attachments/assets/f52bdbd1-4e65-4014-bc85-bdbfa3a2484b" />

Figure 4:

Swinging Hammers https://blueprintue.com/blueprint/dusedirm/

Single Buzzsaw https://blueprintue.com/blueprint/10bica6x/

Tenderizer https://blueprintue.com/blueprint/wfunnnc1/

Then I got to blueprinting the character movement and constructing the animation blueprint (figure 6). At first every time I jumped with no animation present the character would fall flat on his face, this was because I had imported the mesh without a skeleton which did exist because I put it there in Mixamo. I then had to refresh my memory on movement input, camera control and animation blueprints by re-watching some YouTube tutorials from the creator Matt Aspland (cited in the bibliography).

I put a lot of time into these blueprints making adjustments, constantly testing, making sure that everything worked as I wanted it to. I did have a few issues with passing variables between the character blueprint at the animation blueprint but they all got ironed out in the end. I did attempt to use animation notify states to control the spawn and throw lightning ball, but ended up using custom events to control the spawning and launching. Animation notify states worked with the throw animation using enable and disable input notifiers so that the player wouldn’t be skating around whilst they’re going through throw animation. When it came to sliding, I had to add an UnCrouch node and then adjust the collision capsule half height and also the location of the character mesh, because if I used a crouch node it would drop the player speed and they wouldn’t slide on their back for as long as I wanted. I could probably have used a set player speed as well but I felt this was the most robust solution.

<img width="2055" height="1219" alt="ChargerScreenShot" src="https://github.com/user-attachments/assets/c80a9c95-3314-4b38-b2fb-6a22797f7f7b" />

Figure 5: The Indigo Charger, Niagara Portal and Activated Pillars

BP_Charger complete character Blueprint https://blueprintue.com/blueprint/6idxw_ek/

Niagara portal https://blueprintue.com/blueprint/0bdc1b48/  (blueprintUE does not parse these properly)


<img width="1209" height="790" alt="NiagaraPortalNodes" src="https://github.com/user-attachments/assets/8a5212c5-de08-465d-8592-ed01ecf6f32e" />

Figure 5.1 Niagara Portal nodes 




<img width="1075" height="667" alt="ABP_Charger" src="https://github.com/user-attachments/assets/101cf649-912e-4f8e-baf0-7d88dbbd3ef0" />

Figure 6: Animation Blueprint (blueprintUE does not parse these)

Animation Blueprint Event Graph https://blueprintue.com/blueprint/15wpgxa2/

For the ball lightning projectile (figure 7) I had to use an Actor Has Tag node which was assigned to the pillars and then a Cast To BP_Pillar with an event dispatcher for Activate Pillars which was then also passed to the gyroscopic portal, so when all of the pillars are activated, the portal stops rotating the centre sphere disappears and a Niagara portal appears. I also got quite an impressive complex material from the CGHOW YouTube channel (cited in the bibliography) using a noise map twice layering one on top of the other moving it with an absolute world location multiplied by time plus many other add and multiply nodes with a Fresnel fade for the glowing effect, all very nice.

<img width="427" height="424" alt="BallLightning" src="https://github.com/user-attachments/assets/f955d9ad-b7db-456a-bfa8-ac23aa1ee071" />

Figure 7: Lightning Orb

Projectile blueprint https://blueprintue.com/blueprint/r5el-5vl/

Complex material blueprint https://blueprintue.com/blueprint/g619my29/

For the pillars (figures 5 and 8) I created a dynamic material instance for colour change (user feedback). I had to use a branch check to stop the pillars from being activated more than once, this was happening so you could open the portal by hitting one pillar four times I did not want that. The pillars were tied to an event dispatcher (connected to the gyroscopic portal) and when they are activated they Lerp colour using a scalar parameter value with the dynamic material as the target they change from black to emissive purple.

<img width="442" height="782" alt="Pillars" src="https://github.com/user-attachments/assets/6608e236-431c-4bc8-bb52-4de72b24ac81" />

Figure 8: Activatible Pillars https://blueprintue.com/blueprint/_rz1y35g/

Pillar material https://blueprintue.com/blueprint/q_o33nff/

I already had my kill boxes set up around the level to ensure no infinite falls to not dying, so I had to have a checkpoint system, thanks again to Matt Aspland’s YouTube channel.

<img width="1038" height="1015" alt="KillBox" src="https://github.com/user-attachments/assets/7dc5bdf3-61e4-461e-bd4c-d6e98d62f64e" />

Figure 9: KillBoxes (OnComponentOverlap > CastToBP_Charger > DestroyActor)


<img width="1124" height="225" alt="Checkpoints" src="https://github.com/user-attachments/assets/4f8468ab-b76c-49e0-9599-99f01e4dfff3" />

Figure 10: Checkpoints

BP_Checkpoint https://blueprintue.com/blueprint/mrdih0ny/

ChargerGameMode Checkpoint blueprint https://blueprintue.com/blueprint/w5rcgg4x/

With my game being completely functional as best as I could get it, I needed a menu system. I had no idea about how to do this but thanks to the Unreal University (cited in bibliography) YouTube channel whose creator is a certified Unreal Engine Instructor he really knows his stuff. Without his knowledge I would not have a Main Menu (figure 11), Options Menu (figure 12), Pause Menu (figure 13) with adjustable input settings and a system that saves user settings. The options menu allows you to change the window mode, resolution, graphics quality and VSync. I certainly learned how to use widgets in separate levels to load up another level which is what I ended up doing for my image on a widget at the end of the game (figure 16).

<img width="1279" height="717" alt="MainMenu" src="https://github.com/user-attachments/assets/45ed5348-3afe-4c4d-b197-330af2a78698" />

Figure 11: Main Menu https://blueprintue.com/blueprint/md8tiiku/

<img width="1278" height="739" alt="Options" src="https://github.com/user-attachments/assets/6be28c76-abe4-4116-9632-8049c1ce3163" />

Figure 12: Options Menu https://blueprintue.com/blueprint/q3vvcjvn/


<img width="1280" height="738" alt="PauseMenu" src="https://github.com/user-attachments/assets/65299d96-2763-4bbd-b668-2d1e54be428e" />

Figure 13: Pause Menu (in game) https://blueprintue.com/blueprint/85n_acg7/


<img width="1279" height="719" alt="Intro1" src="https://github.com/user-attachments/assets/06cf3b60-95e5-46f5-89c3-6d03621e96f0" />

Figure 14: Intro widget image

<img width="1278" height="718" alt="Intro2" src="https://github.com/user-attachments/assets/b2138959-a77d-4993-b4fa-ff4325a7cb23" />

Figure 15: Second intro widget image

<img width="957" height="534" alt="Outro" src="https://github.com/user-attachments/assets/a94d0b16-dc03-448d-b86b-b78eb4a67954" />

Figure 16: Outro widget image


## Testing

I was constantly testing throughout the process, mostly on character movements/animations, troubleshooting any problems that I came across to proceed to the next task. This was a linear journey, for the most part, except when it came to making the Niagara portal with fluid motion (figure 5). With the full set up that I got from RedefineFX YouTube channel (cited in bibliography) it impacted performance (i.e. frame rate) greatly, even with GPU simulation. It should have been a smoke portal, perhaps if I cut the particle count down dramatically it would have not been so bad on performance but I removed the smoke element entirely and there was no noticeable drop after that. That being said I did not conduct any performance tests on my final build, it runs nicely.

## Critical Reflection 

Character movement and animations lived up to my expectations. The increasing sprint speed in parallel with the sprint animation, was the highlight of this project for me. I got most of what I wanted done in this project. I think that the custom gravity was most likely the wrong system to use for wall running as there are a few videos on replicating the Titanfall 2 (Respawn Entertainment, 2016) wall running available and I should have looked those instead. I would have liked to have added projectile lightning but my inexperience with the Niagara system ultimately excluded it from the game. Given more time, I would have liked to have implemented the Apex Destruction system to dice the player into many pieces when they collided with one of the buzzsaws. I would also have liked to have used a static single layer water material on the gyroscopic sphere and lerp it with a panning layer water material. I feel I achieved roughly 75% of what I set out to do.


---

## Bibliography


Arnbjornsson, Ari. ‘Custom Gravity in UE 5.4 | Tutorial’. Epic Games Developer, 21 March 2024. https://dev.epicgames.com/community/learning/tutorials/w6l7/unreal-engine-custom-gravity-in-ue-5-4.

CGHOW, Ashif Ali, dir. *Create Stunning Lightning Orbs in Unreal Engine Niagara: Step-by-Step Tutorial.* 2025. 15:19. https://www.youtube.com/watch?v=bYG6qWZfCsg.
ChatGPT. ‘ChatGPT’. Accessed 14 September 2025. https://chatgpt.com/?locale=en-US.

*DeathSprint 66* (2023) [PC] Newcastle: Sumo Digital (Newcastle). Secret Mode.

*Event Horizon* (1997) [Film.Blu-ray] Directed by Paul W.S. Anderson. United Kingdom/United States: Paramount Pictures.

Matt Aspland, dir. *Creating Character Movement With The New Enhanced Axis Mappings In Unreal Engine 5 (Tutorial).* 2022. https://www.youtube.com/watch?v=Z9zEEY7dGaM.

Matt Aspland, dir. *How To Make An Animation Blueprint In Unreal Engine 5.1 | How To Animate A Character - UE5 Tutorial.* 2023. 19:15. https://www.youtube.com/watch?v=qbgDaRo312k.

Matt Aspland, dir. *How To Setup Multiple Checkpoints And Respawn At Them - Unreal Engine 5 Tutorial.* 2025. 14:10. https://www.youtube.com/watch?v=T3ZugysfPL4.

Matt Aspland, dir. *Unreal Engine 5 Beginner Tutorial - Character Movement And Animation.* 2023. 01:11:29. https://www.youtube.com/watch?v=bqPvUPPgJZs.

RedefineFX, Jesse Pitela, dir. *Niagara Fluids Smoke Portal VFX Tutorial in Unreal Engine 5 | Real-Time Simulation | RedefineFX.* 2024. 12:33. https://www.youtube.com/watch?v=nOirmGz8YG4.

*The Flash: The Complete Series* (2014–2023) Warner Bros. [Television programme] Microsoft Films & TV.

*Titanfall 2* (2016) [PlayStation 4, Xbox One, PC] Los Angeles: Respawn Entertainment. Electronic Arts.

*Tron RUN/r* (2016) [PlayStation 4, Xbox One, PC] Foster City: Sanzaru Games. Disney Interactive Studios.

Unreal University, dir. *How To Create A Main Menu - Unreal Engine 5 Tutorial.* 2022. 09:20. https://www.youtube.com/watch?v=kumZj_mov58.

Unreal University, dir. *How To Make A Pause Menu In Unreal Engine 5.* 2023. 07:36. https://www.youtube.com/watch?v=ga9-Zps0l48.

Unreal University, dir. *How To Make An Options Menu - Unreal Engine 5 Tutorial.* 2023. 27:12. https://www.youtube.com/watch?v=Ff67XtqgSxc.

Unreal University, dir. *Mouse Sensitivity And Invert Settings ( With Save & Load ) - Unreal Engine 5 Tutorial.* 2025. 27:12. https://www.youtube.com/watch?v=q4d_D9HTkyU.


---

## Declared Assets


List of declared assets
>  The following assets were created by Matt Aspland YouTube channel
> * `BP_Charger`
> * `ABP_Charger`
> * `ChargerGameModeBlueprint`
> * `BP_Checkpoint`

> The following assets were created by Unreal University YouTube channel
> * `UI_MainMenu`
> * `UI_Options`
> * `UI_Controls`
> * `UI_PauseInputSettings`

>  The following assets were created by CGHOW YouTube channel
> * `M_Lightning`

> The following assets were created by RedefineFX YouTube channel
> * `NS_Portal`

> The following assets were created by Ari Arnbjornsson Epic Games Developer
> * `CustomGravity.cpp`
> * `CustomGravity.h`

> The following assets were created or modified with the use of ChatGPT 4o
> * `M_PillarActivated`
> * `BP_BallLightning`
> * `BP_SwingingHammer`
> * `BP_Pillar`
> * ` BP_Charger`
> * `ABP_Charger`
> * `BP_GyroscopicPortal`

