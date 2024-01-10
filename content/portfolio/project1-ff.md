---
title: "Feedforward: A mo-cap system to preview interactions in VR "
weight: 1
date: 2019-12-23T15:44:46+06:00
type: portfolio
image: "images/projects/ff/car-banner-ff.png"
category: ["Interaction Design and Development"]
project_images: []
enableEmoji: true

---



_________________
This project was published as a *journal* paper in TOCH, entitled *Using Feedforward to Reveal Interaction Possibilities in Virtual Reality*. Find the whole paper [here](https://dl.acm.org/doi/10.1145/3603623 "acm").
_________________




A fundamental aspect of interacting in virtual reality (VR) is knowing how to manipulate objects, what interactions are available, and where to navigate.
Designers often help users understand this by relying on real-world knowledge. Virtual objects can mimic real-world objects in appearance and functionality. For example, if the user sees a virtual door, they may turn its handle to open the door. If the user sees a virtual button, they may press it to perform a certain action. 
 
Despite its convenience, mimicking real-world interaction brings new challenges to VR. 
For instance, users may expect that they can act in the same way in VR as in the real world. 
However, the point of some VR experiences is to provide excitement by going beyond mundane life. Interactions can be purposely different or novel to users. Such VR interactions add value by contributing to immersion, presence, and fulfilling experiences. To do so, they need to differ from their real-world counterparts. Thus, mimicking the real world is not always a viable option. In such cases, designers cannot meet some users' expectations of interactivity.

We propose using feedforward to show users what they can do in VR and how to do it.
Unlike feedback, feedforward shows actions and their results before the user performs them. A canonical example of feedforward in 2D interfaces is the preview of swiping the iPhone lock screen to unlock the phone. Vermeulen et al. discussed feedforward at length for 2D interfaces and as a general concept, and gave examples of real-life use.

### The gist of it

{{< youtube AxIEEGyMNo0 >}} --

Although feedforward has been developed and tested successfully for 2D environments, many questions remain about using feedforward within VR. Why would feedforward be useful for VR? 

On the one hand, feedforward offers similar benefits as feedforward for non-VR user interfaces. This includes bridging Norman's gulf of execution and improving discoverability, helping users plan and execute actions. 
On the other hand, VR differs from traditional user interfaces. In virtual environments, any object can have many manipulations available, and others may be available for the rest of the environment. 
Given that examples of feedforward mainly contain one action (e.g., the iPhone's ``slide to unlock'' function), how can we cater to the higher complexity of VR? Furthermore, actions in VR may vary in granularity, from a single movement to a long sequence of actions. How does feedforward apply to such situations? 

We answer these questions by defining feedforward for VR and detailing its design space. Throughout the paper, we focus on physics-based interactions using hand-tracking to exemplify the feedforward design space. We develop the design space as an idea-generation tool for designing and describing VR feedforward aimed at researchers and designers. For example, a feedforward may show users a preview of opening a door with a misleading opening mechanism (see video above). We can design this feedforward by showing users a ghosted version of their avatar performing the movements required to open the door. Ultimately, the feedforward design space may aid practitioners in solving challenges related to discoverability and understanding of VR interactions. We make the design space available on [Figma](https://www.figma.com/file/yv1141eCG65nBfacXDcrxb/Feedforward-Design-Space-in-VR-Template?node-id=0%3A1&t=vGMWdDt6iaofxKIs-1) as a short cheat-sheet and a design template.


##### Overview of the feedforward design space 
We introduce feedforward to VR to help designers generate
ideas for showing users how to act. Feedforward shows users a preview of what they can do in a VR environment. In such an environment, the user needs to (1) trigger the preview, for instance, by being in a particular place or looking at a particular object. 
When triggered, the feedforward shows the user a (2) preview of the actions and their outcomes available in a particular place for a particular object. For instance, the preview could show how to grab the wheel of a car and steer it. The user may then (3) exit the preview to perform the actions themselves. A preview may be shown only once or in a loop, or the user may interrupt a preview if they wish. One of the main goals of feedforward is to reveal information when the user needs it. Taken together, triggering, previewing, and exiting constitute the three stages of feedforward in VR. 

While the paper describes the feedforward concept at length, the basic idea of the design space is as follows:

1. ***Triggering***
    1. ***Trigger types***: conditions and mechanisms to start triggering previews.
        - *Persistent triggers*. The feedforward already exists in the virtual world, e.g., iPhone “slide to unlock”.
        - *Location*. The preview starts when the user is close to an object, or at a specific place.
        - *Events*. The preview starts after state changes within the environment which are not caused by the user directly, such as weather, timers. 
        - *Gaze*. The preview starts when the user looks at an object or place.
        - *Action*. The preview starts when the user performs an action, i.e., gives direct input like pressing a button, voice command or grabbing an object.
    2. ***Signifiers***: optional cues in the environment that may convey the existence and parameters of feedforward, its state or enable playback controls.
2. ***Previewing***
    1. ***Level of detail***: steps to display during previews. For example, the level of detail may contain:
        - *All actions*. The preview shows all steps involved in the interaction, e.g., from walking to interacting. 
        - *A subset of actions*. The preview shows only some of these steps.
    2. ***Targets***: visual elements of the interaction involved in the preview.
        - *Avatar*. The preview shows the user’s avatar.
        - *Actions*. The preview shows visual elements related to the action.
        - *Outcomes*. The preview contains visual elements related to the outcome.
    3. ***Avatar type***: avatar representation during previews.
        - *Full avatar*. The preview shows the entire avatar.
        - *Partial avatar*. The preview shows a selected part of the avatar.
        - *Real device*. The preview shows a virtual representation of the hand-held device.
        - *Real user*. The preview shows a humanoid representation of the user that performs the movements required for the action.
        - *None*. The avatar does not appear during the preview.
    4. ***Perspective***: how the user’s perspective changes during previews.
        - *Third-person*. Users view the preview from a third-person perspective. 
        - *First-person*.  Users view the preview from a first person perspective. Their location may change during previewing.
    5. ***Modifier***: changes targets during previews. 
        - *Haptic*. Haptic feedback of targets may change.
        - *Audio*. Target audio may change.
        - *Transform*. Size, location or/and rotation of targets may change.
        - *None*. Targets remain unchanged.
    6. ***Rendering***: targets’ appearance change during previews 
        - *Ghosted*. Targets have a ghosted appearance, e.g., blue and transparent.
        - *Original*. Targets remain with their original materials.
    7. ***Representation***: how targets are represented during previews
        - *Direct*. The preview shows targets that simulate the VR experiences.
        - *Indirect*. The preview shows targets as  abstractions, like images, labels or audio.
    8. ***Duplication***: previews may show copies of the targets.
        - *Yes*. Targets are duplicated and the copies appear in the previews. Original targets remain unchanged.
        - *No*. Target are not duplicated. The previews contain original targets.
    9. ***Playback***: previews can be interrupted, repeated, stopped, paused, rewinded, sped up.
3. ***Exiting***
    1. ***Untrigger***: what starts returning the world to a pre-feedforward state. 
        - *Gaze*. The preview stops when the user gazes at something, or looks away.
        - *Action*. The preview stops when the user performs an action.
        - *Playback*. The preview stops when playback conditions are met, like repetitions or interrupts.  
        - *Location*. The preview stops when the user meets a location condition, or walks away.
    2. ***Exit Transition***: how to transition between the preview and the initial state of the environment. 
        - *Return*. Have no transition and simply return objects to their original states.
        - *Rewind*. Rewind the preview like a recording. The rewind may be more sped up than the feedforward.
        - *Visual effects*. Signal exiting through visual cues, e.g., blacking out the user’s field of view. 



##### Putting practice into theory
While VR can easily mimic 2D feedforward, the design space goes beyond traditional feedforward to include VR-specific dimensions. We explore different ways of triggering feedforward in VR, previewing actions and outcomes using virtual objects and avatars, and returning the world to its initial state. 
We test the feasibility of VR feedforward by implementing a VR feedforward system that enables a subset of the design space. We then create three demos consisting of feedforward variations for three real-world application scenarios using the system. We evaluate the feedforward design space with 14 VR experts focusing on both theoretical and practical aspects of feedforward. Finally, we summarize our observations in 15 general guidelines for applying feedforward in VR. These guidelines are based on the implementation and expert evaluation and involve clutter, space and coherence considerations: 

1. When users desire subtlety, use hidden feedforward and only preview actions.
2. To make feedforward explicit, use signifiers with additional information about the triggers, such as distance or gaze timers.
3. To maintain consistency, aim to have similar visual target representations across feedforward interactions (i.e., rendering).
4. Use the playback parameter to communicate whether the target representations are animations or static previews
5. Use perspective to state whether the user’s viewpoint changes, particularly useful for animations.
6. Do not allow changes to targets during previewing to maintain continuity.
7. To prevent misunderstandings make the rewinding salient by changing the speed and rendering of actions and outcomes.
8. To maintain continuity, duplicate the targets if objects need to fulfill certain conditions before previewing.
9. When actions are complex, use direct representations to leave no room for interpretation.
10. When using duplication, refrain from offsetting, especially towards the user.
11. To deal with occlusion, decrease the level of detail to preview interactions step-by-step.
12. Pre-attentively group targets to reduce mental load, for example, by adjusting playback speed, ghosted material, shape, etc.
13. Pre-attentively group targets to reduce mental load, for example, by adjusting playback speed, ghosted material, shape, etc.
14. For complex interactions, allow users some degree of control over the playback using signifiers.
15. Feedforward interactions should not reveal more information than needed to the user, e.g., through transparency.

Feedforward in VR is intended as a bridging concept, which is more general than a particular design but less general than a theory. Bridging concepts describe theory and practical applications that may reveal potential design opportunities and novel theories. For the theoretical part, we develop a design space for feedforward in VR and a working model for feedforward interactions containing the three stages. For the practical side, we implement a feedforward system and evaluate it with experts to uncover new design ideas and reshape the theory.


### Future work

Potential feedforward applications involve tutorials and programming by demonstration. In future work, the feedforward design space can be extended to other mediums, such as augmented reality. We could also experiment with previewing different types of stimuli like haptic sensations. While we make the code required to develop feedforward freely available [here](https://github.com/aam505/feedforwardVR), the interface to record interactions is cumbersome and highly technical. The feedforward system could be upgraded with a non-technical interface for recording and previewing interactions. In theory, the feedforward system is fantastic to reveal all the possible interface combinations for previewing an interaction. In practice, setting up the system correctly requires a lot of Unity knowledge. 

My current project is exactly about this --- a user-friendly interface for recording interactions. It should be published in 2024, so stay tuned! Meanwhile, I described an initial version of the project [here]({{< ref "project3-clones-1.md">}} "Mo-cap Inteface").