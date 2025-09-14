# Henry-Taylor-2206046-Technical-Art-Development-Commentary

# Technical Art Development Commentary

**Unit Name:** Technical Art 24-25 FGCT5016

**Student Name:** Henry Taylor

**Student ID:** 2206046

**Total Word Count:** \[XXXX]

**Documentation Link:** https://github.com/Ramphoryncus/TechnicalArt_24_25_Copy/blob/GitMain/README.md

**Repository Link:** https://github.com/Ramphoryncus/TechnicalArt_24_25_Copy

**Build Link:** https://ramphoryncus.itch.io/indigo-charger

**Video Demonstration Link:** https://drive.google.com/file/d/1L5X_Y1mxgZnPHIaEqiTAQqOWj3VAOeTj/view?usp=drive_link

---

## Abstract


The task was to create a game and subsequently a final playable build in Unreal Engine 5 based on the theme Alive. We were free to interpret what this might mean to produce a real-time interactive experience. We would have to implement at least two of the following: Procedural Content Generation; Complex Materials and Shaders; Visual Effects (Niagara or Cascade); Performance Optimisation. My goal was to produce a playable level with obstacles and interactive elements and to create a new kind of super anti-hero, based on electricity and speed (running really fast), as the playable character. I approached it in two ways, from a player’s perspective concerning controls, animations and interactive elements, and from an artist’s, making original 3D models with “hand-painted” textures that would populate my three-dimensional environment. The final outcome did not end up having everything that I would like to have included but it is playable and functional. I had intended to use the Niagara system to create lightning bolts and orbs that the character would “throw”, and to implement a custom gravity so the player could run at high speeds on the walls of the final area. I created the lightning orbs using a complex material, the custom gravity was not included in the final build but I did achieve most of what I set out to do.

---

## Research *(Approx. 20-30% of word count)*


I explored three video games, *Titanfall 2* (Respawn Entertainment, 2016), *DeathSprint 66* (Sumo Digital (Newcastle), 2023), *Tron RUN/r* (Sanzaru Games, 2016), I also considered *The Flash* (Warner Bros. Television, 2014-2023) and *Event Horizon* (Paramount Pictures, 1997).

*Titanfall 2* (Respawn Entertainment, 2016) is widely regarded as one of the finest examples of a single and multiplayer video game experience. Respawn Entertainment crafted something special, lightning in a bottle.

- Wall running mechanic, with believable limitations, some of the best in the business
- Fluid character movement, also some of the best in the business

I could only hope to achieve something as good as this, not wanting to set my sights too high, this is purely for a reference of what is possible.

*DeathSprint 66*(Sumo Digital (Newcastle), 2023) is a fast-paced PvP racing game in the “runner” genre. The players race around tracks on foot which have difficult reversals and deadly traps littering them. The player gains power ups and can use them to benefit themselves or to attack the other runners depending on the type of power up. This is a slick third person game, vary enjoyable.

- Wall running mechanic which appears to be active until the wall runs out
- You gain speed the longer you stay out of trouble but there is a limit to the speed
- Deadly traps

This game comes close to what I had in my mind in terms of movement and wall running. It has nice animations and good controls and a good gameplay loop. This was rattling around in my subconscious, I suspect, when I was constructing my animation blend space.

Tron RUN/r (Sanzaru Games, 2016) is a medium paced “on rails” running game. The player runs at a set speed and they have to run, slide, jump and dodge to the exit. Jumping and gliding over large gaps, dodging obstacles and enemies, or destroy the enemies and obstacles with your disc, collecting “bits” along the way. The controls are not too complicated, but it is not easy.

- Challenging obstacle placement
- Nice visuals (because it’s Tron if you like that sort of thing)

This was relevant for obstacle placement in my level, not as easy as it may look. It was all a matter of flow, where the platforms and hazards should be placed,  to make the player think rather than just run and jump and slide. From the looks of my character there was definitely some influence from the Tron universe.

*The Flash*(Warner Bros. Television, 2014 to 2023) was the underlying template for my character. He gets his powers after a freak accident. He can run really fast, the friction from his super speeds generates electricity which he can throw like lightning. He also has accelerated healing, he can see the world in super slow motion.

- He runs really fast
- Can throw lightning
- Has cool suits

The Flash is totally relevant with the superspeed and lightning throwing. For my character I did not want time to slow down or for there to be accelerated healing, I wanted there to be consequences for irresponsible speeding. My first 3D mesh that I made for charger had lightning bolts on his boots, ears and one on his chest, I was advised against copyright infringement and I like purple more than red, so he got a makeover.

*Event Horizon* (Paramount Pictures, 1997), this is one of the best space horror movies with excellent set design, which is what inspired me create my gyroscopic sphere and the rotating tunnel that looks like an inverted buzzsaw. I watched the Blu-ray extra on set design and construction which helped me fine tune my 3D meshes.





### What sources or references have you identified as relevant to this task?

Reflect on the **type** and **relevance** of sources explored. Justify your research direction in relation to the task brief and target outcomes.

* What types of sources did you explore and why?
* Which types of sources did you avoid and why?
* How does the research relate to the user experience, technical approach, or creative aim?

#### Sources

For each source, provide:

1. An **opening paragraph** describing the source's creator/publisher, reputation, and relevance.
2. A **bullet list** of what you analysed or learned from it.
3. A **closing paragraph** evaluating its usefulness or limitations.

You may include both **academic resources** and **industry examples** (e.g. documentation, games, developer talks). You are encouraged to include plenty of images, videos and diagrams.

---

## Implementation *(Approx. 30–40% of word count)*

### What was your development process and how did decisions evolve?

Describe your technical and creative approach, including:

* Planning, ideation, and iteration
* Feedback received and how it was integrated
* New tools, workflows, or systems explored

#### Example Code Snippet

```csharp
using UnityEngine;

public class HelloWorld : MonoBehaviour 
{
    public void Start() 
    {
        Debug.Log("Hello World!");
    }
}
```

*Figure 2: Example code snippet using Unity's `Start()` method.*

#### Example Image

![Example](https://beforesandafters.com/wp-content/uploads/2021/05/Welcome-to-Unreal-Engine-5-Early-Access-11-16-screenshot.png)
*Figure 3: Unreal packaging menu interface.*

### What creative or technical methods did you try?

Were any methods unfamiliar or experimental? Did they succeed? Did they change your approach?

### Did you experience any technical challenges?

How did you address problems, bugs, or limitations?

---

## Testing *(Approx. 10–15% of word count)*

### What testing methods did you use?

* Did you conduct internal testing, peer testing, or user testing?
* What were your key goals in testing?
* What did you observe or learn from testing?
* How did testing influence the final result?

You may include screenshots, graphs, tables, or embedded videos to demonstrate tests and results.

| Tester | Platform | Device Specs           | Test Type      | Bugs Found | Avg. FPS | Severity (1–5) | Repro Steps Provided | Feedback Summary                                                       |
| ------ | -------- | ---------------------- | -------------- | ---------- | -------- | -------------- | -------------------- | ---------------------------------------------------------------------- |
| User A | Chrome   | i7, GTX 1060, 16GB RAM | Internal (Dev) | 3          | 60       | 2, 3, 4        | Yes                  | “Controls are responsive. Minor stutter near large particle emitters.” |
| User B | Firefox  | Ryzen 5, 8GB RAM       | Peer Playtest  | 2          | 58       | 1, 2           | No                   | “Menu system works well, but level loading feels slow.”                |
| User C | Edge     | i5, Intel UHD 620      | External User  | 5          | 45       | 2, 3, 4, 3, 2  | Yes                  | “Performance drops during explosions; some UI overlaps text.”          |
| User D | Chrome   | M1 MacBook Air         | Guided Test    | 1          | 62       | 2              | Yes                  | “Tutorial is clear. Suggested adding a visual checkpoint marker.”      |
| User E | Safari   | iPhone 12 Safari       | Blind Test     | 4          | 50       | 2, 3, 3, 4     | Partial              | “Enjoyed art style. Unclear level goals; needed more on-screen hints.” |

*Figure 4: User Testing Data.*

---

## Critical Reflection *(Approx. 10–15% of word count)*

### What went well?

* What strengths or successes stood out in the final piece?
* Did anything exceed expectations?

### What could be improved or done differently next time?

* Were there things that didn’t work? Why?
* What would you try differently with more time or resources?

---

## Bibliography

Please use [UCA's Harvard Referencing Format](https://mylibrary.uca.ac.uk/referencing) for all citations.

Example:

> Rollings, A. and Adams, E. (2003) *Andrew Rollings and Ernest Adams on Game Design*. New Riders Publishing.

---

## Declared Assets

You must declare any content that was **not entirely created by you**, or was **modified with the aid of AI tools**. This includes:

* Third-party 3D models, audio, textures, or code
* Code snippets from tutorials or forums
* AI-generated or AI-assisted assets (e.g. ChatGPT, GitHub Copilot, DALL·E)

List these clearly, with context where needed.

Example:

> The following assets were created or modified with the use of GPT-4o:
>
> * `Test.cs` – generated structure with manual revision
> * `UIAudioManager.cs` – refactored with Copilot suggestions
> * `DevelopmentJournal.html` – generated layout and headings

---

## Tips for Success

* Use plenty of **images, code snippets, drawn diagrams, tables and embedded media** to support your writing.
* Use **inline citations** for everything that influenced your work, including software and games. Include as many **hyperlinks** as possible for easier navigation to external sources.
* Reference **documentation, tutorials**, and **games** just like academic sources.
* Word count is a guideline – ±10% is allowed.
* You are allowed to use AI tools, but you **must declare** them under *Declared Assets*.
