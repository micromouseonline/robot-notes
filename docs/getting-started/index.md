---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
# icon: octicons/dot-fill-16
# icon: octicons/dot-16
# icon: octicons/dash-16
# icon: octicons/chevron-right-12
status:
---



# Getting Started With Small Robots

## Core Principles

There are many competitive events for small robots:

- Micromouse Maze Solving
- Line Following
- Drag Racing
- Sumo
- Robot Combat
- Autonomous Rovers
- ... and many more

Some of these are human-guided and some are autonomous. That is, the robots are completely independent. They have a task and they must complete that task entirely without human intervention.

Here, we are concerned only with micromouse and line-following robots although many of the principles will apply to other types of robot and the skills involved are very transferable.

### Weight, size, power, cost

As a hobbyist robot builder, resources are likely to be limited. In most cases, space and money are major constraints. Projects should be small, flexible and inexpensive where possible. While it is true that the contest events for these robots are run on large mazes and tracks, the development of some of the most successful robots takes place in a very limited space with a minimum of facilities. 

Typical robots will weigh a couple of hundred grams at most and may fit in a sandwich box. Indeed, there is a requirement that the robots should fit in a 25cm square box. Most are much smaller.

With only a small robot to drive, power requirements are modest and a simple 9V PP3-size battery is going to be sufficient to get started with. REchargeable batteries are widely available and will very quickly pay for themselves.

There is no getting around the need to spend some money but there is no need to go overboard. You can go a long way with costs no greater than a games console. 


### Design Philosophy

Everything about building robots involves a trade-off. What makes it all interesting is that there are many ways to combine all the components to make your robot different to everyone else's while still having the same goal. 

In these guides, the aim is to examine many of these choices and help you to make an informed decision about what to use, why you might make that selection and how to get the most out of it.

Above all though, there is a desire to get the best out of simple components and methods. 

Start simple and add complexity only when you need to.

--- 

## About the contests

### Micromouse

The micromouse contest is the oldest, continually running autonomous robot contest in the world. Robots are tasked with exploring a maze to find the optimum route to a target area somewhere in the maze. The robots know where the target is but know nothing about where the walls are. The maze is a grid of up to 32x32 cells, all the same size. Each cell may have walls on any of its edges. Mazes are designed to ensure that it is not possible to reach the target area by just following one wall.

Typically, there are several alternate routes that the robot might discover while searching the maze and the robot will need to find the route that it can run fastest. That may not be the shortest route, or even the straightest route and may change depending on the ability of the robot to accelerate and turn at various speeds.

Having determined the optimal route, the robot will return to the start and make a number of attempts to run to the target in the shortest time.

Even after more than 45 years of micromouse contests, this is not a 'solved' problem and the performance of micromouse robots is still improving.

While robots of 40 years ago might trundle around without spilling a cp of tea. modern robot have performance levels that are higher than Formula 1 race cars and the real challenge is keeping them on track.

For a pretty definitive look at the event, you cannot do better than the Veritasium video on YouTube. [The Fastest Maze-Solving Competition On Earth](https://www.youtube.com/watch?v=ZMQbHMgK2rw)

### Line Followers

On the face of it, getting a robot to follow a line drawn on the ground is a pretty simple task. On one level, that is correct. Basic line following with a minimum of hardware resources is a very popular beginner's project. It can be achieved with a very satisfying level of success using really basic, inexpensive components and only moderate skills.

Line following contests though present a whole extra set of challenges. Many robots compete to run the same track as fast as possible. All the robots must run autonomously and the builder of the robot has little idea what that track will look like until the contest actually starts. There may be crossovers that must be navigated and, while there may be long straights, some of the bends can be very tight. Running at a single fixed speed is not going to get the shortest time on the track. Robots will need to learn the layout on an exploratory run and then use the information learned to adjust their speed as they go.

Only a limited number of attempts are permitted and the total time is also limited.

Like the micromouse robots the range of performance is remarkable. Modern entries will analyse the track and generate a path that cuts corners while still obeying the rule that requires the robot body to be over the line at all times.

In this video from a regional contest in Japan, you can see line follower first map out the track and then run it at speed:
[https://www.youtube.com/watch?v=IW6_JFPHD2Q&t=570s](https://www.youtube.com/watch?v=IW6_JFPHD2Q&t=570s)

--- 


## Essential Tools & Skills

You do not need to be a graduate in multiple engineering disciplines to either enjoy, or be successful in either of these contests. It would probably help, but it is not essential. At least some basic skills will be needed though and many of these can be learned along the way.

The entire business should, at least, be treated as a learning process. Even robot builders with experience in one or more of the related subjects will find there is something new to learn. For many builders the process is as important as the result. The most important thing is that you enjoy it at your level.

### Electronics

Some electronics knowledge is pretty essential. An understanding on voltages, currents, and basic components is going to save a lot of time and money. It is possible to find kits that can be put together and run with the absolute minimum of skills but, at the very least, you should be able to solder reliably and be able to identify the components. If you have a background in electronics, then there some aspects of the robot that will be familiar but don't be surprised if you find your understanding challenged and your skills broadened.

### Mechanical 

For many, the mechanical aspects of the robot can be quite challenging. The robot looks simple but getting everything made accurately and fitted together securely depends on the availability of tools, materials and parts. It does not take a lot but these are not normally household items. Fortunately, there are now a good range of kits and modules that can often be put together into a working robot  without having to do everything from scratch.

#### Design and Manufacture

For many, the design and manufacture of custom components is both a challenge and an achievement. For the very highest performance, you are definitely going to have to possess, or learn, design skills and bea able to turn those designs into actual, working objects. That need is some way down the road though. Start simple and work up to complex. Hopefully, avoiding complicated on the way.

In recent years, the manufacture side of hins has become much easier. There are inexpensive 3D printers and laser cutters readily available and several companies provide services to make custom parts from your designs. PCB manufacture is also very cheap and the boards are of excellent quality. In pretty well all cases, there is no reason to make your boards at home. Do the design, send off the files and work on something else until they arrive.

### Software Development

The robots need code. There is no way around that. Even if you could get a ready-built robot, perfect for your application (there are a few), it can do nothing without the software. There are many choices and you may be swayed by you own experience but there are robots running in contests that have been programmed in various languages, including:
 - Assembly
 - Basic
 - C
 - C++
 - Forth
 - Python

Not all choices are suited to all microcontrollers so there is that to consider as well. Pick the one you are most familiar with to get started. Do not be swayed by people telling you this or that is 'best' or 'correct'. When you reach the limits of what you can achieve with your chosen language and controller, then you will be able to make a more informed choice about how to progress.

In the first instance, it is much more important that you get something working than it is to chase the ultimate in performance. Do not set yourself up to fail with unreachable goals.





