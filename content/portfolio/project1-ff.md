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

We answer these questions by defining feedforward for VR and detailing its design space. Throughout the paper, we focus on physics-based interactions using hand-tracking to exemplify the feedforward design space. We develop the design space as an idea-generation tool for designing and describing VR feedforward aimed at researchers and designers. For example, a feedforward may show users a preview of opening a door with a misleading opening mechanism (see video above). We can design this feedforward by showing users a ghosted version of their avatar performing the movements required to open the door. Ultimately, the feedforward design space may aid practitioners in solving challenges related to discoverability and understanding of VR interactions.

While VR can easily mimic 2D feedforward, the design space goes beyond traditional feedforward to include VR-specific dimensions. We explore different ways of triggering feedforward in VR, previewing actions and outcomes using virtual objects and avatars, and returning the world to its initial state. 
We test the feasibility of VR feedforward by implementing a VR feedforward system that enables a subset of the design space. We then create three demos consisting of feedforward variations for three real-world application scenarios using the system. We evaluate the feedforward design space with 14 VR experts focusing on both theoretical and practical aspects of feedforward. Finally, we summarize our observations in 15 general guidelines for applying feedforward in VR.


This figure illustrates the three key stages of feedforward in VR. The user starts in some initial state in the virtual environment (VE). Then, the user executes a (1) trigger, in this case, by turning around and gazing at the virtual door. That leads to (2) previewing the actions involved in opening the door (operating the slider) and their outcomes (opening the door). After the preview is shown once, the feedforward (3) exits from the preview. Finally, the door is returned to its initial state. This hopefully leaves the user better informed about what to do and how to do it.


We introduce feedforward to VR to help designers generate
ideas for showing users how to act. Feedforward shows users a preview of what they can do in a VR environment. 
In such an environment, the user needs to (1) trigger the preview, for instance, by being in a particular place or looking at a particular object. 
When triggered, the feedforward shows the user a (2) preview of the actions and their outcomes available in a particular place for a particular object. For instance, the preview could show how to grab the wheel of a car and steer it. The user may then (3) exit the preview to perform the actions themselves. A preview may be shown only once or in a loop, or the user may interrupt a preview if they wish. One of the main goals of feedforward is to reveal information when the user needs it. Taken together, triggering, previewing, and exiting constitute the three stages of feedforward in VR. 

Figure shows an example of applying the stages of feedforward to a VR interaction. Here, the user triggers a preview by gazing at a door from a distance. In the preview, a ghosted hand shows the user how to operate a nearby slider and open the door. Here, moving the slider represents the action, and opening the door is the outcome. The feedforward continues to the third stage, exiting, after which the door slides back to its initial position, and the ghost hand disappears. The states of the environment before and after feedforward are the same because changes during feedforward do not persist. However, the user now has more knowledge about the interaction with the door.


Feedforward in VR is intended as a bridging concept, which is more general than a particular design but less general than a theory. Bridging concepts describe theory and practical applications that may reveal potential design opportunities and novel theories. For the theoretical part, we develop a design space for feedforward in VR and a working model for feedforward interactions containing the three stages. For the practical side, we implement a feedforward system and evaluate it with experts to uncover new design ideas and reshape the theory.


### The annoying
In theory, the feedforward system is fantastic to reveal all the possible interface combinations for previewing an interaction. In practice, setting up the system correctly requires a lot of Unity knowledge. I made the code available on my GitHub a while back [here](https://github.com/aam505/feedforwardVR), but it requires a proper interface for recording interactions that would work easier than dropping things into the Unity editor, which is :anger: annoying :anger:.

My secret project is exactly about this --- a user-friendly interface for recording interactions. It should be published in 2024 so stay tuned! :smile: