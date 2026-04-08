# MULTIMEDIA

# 193. 148 – ASSIGNMENT 1

## BASICS OF A 3 RD PERSON GAME IN UNREAL

**Deadline: 12 April 2026, 23:**

**Submission Platform:** TUWEL

## ASSIGNMENT GOALS

You will start from a **Third Person Game template** in Unreal Engine 5.6.1 and extend it with custom
characters, logic, and gameplay systems to get hands-on experience with Blueprints, physics, player
controllers, and game modes.


## ASSIGNMENT REQUIREMENTS

## 1. PROJECT SETUP

- Start from the **Third Person Game** sample provided by Unreal Engine.
- Use **Blueprints only** for this assignment (no C++ required).

## 2. CHARACTER SETUP AND SWITCHING CONTROLS

- Place **three characters** in your level **manually** , wherever you like in the scene.
- Create a new **GameModeBase Blueprint** and a new **PlayerController Blueprint**.

## CUSTOM PLAYER CONTROLLER

In your custom **PlayerController** , you should:

- Keep the **default controls** (WASD for movement and mouse for looking around).
- Add a **new feature** :
    o When the player **presses G** on the keyboard or **right-clicks the mouse** , the controller
       should **switch to the next character**.
    o This should work in a **loop** (after the third character, switch back to the first one).

## INPUT SETUP (ENHANCED INPUT SYSTEM)

- Use the **Enhanced Input System** with **Input Actions** for all input controls.
- For movement, you can **reuse** the Input Actions already provided by the Unreal Starter Content.
- Add a new **Input Mapping Context** that includes all four necessary Input Actions:
    o IA_Jump
    o IA_Move
    o IA_Look
    o IA_Switch (for switching between characters)
- In your **PlayerController Blueprint** , use the **Enhanced Input Events** to handle actions:
    o Use the IA_Switch Input Action to trigger character switching.

## IMPORTANT:

- Do **not spawn** any characters when the game begins and only make sure **one of the three**
    **characters already placed in the scene** gets control **automatically**.
- When switching between characters:
    o The **previous character** should **stop moving** and return to its **idle state**.
    o It should **not continue walking, running, or jumping** after you switch away from it.

## 3. FIRE SPHERES

- Create or import a **Fire Sphere** as shown in the tutorial.
- On game start, **spawn 100 fire spheres randomly** around the environment. Make sure all 100
    spheres are spawned even if there is a physics contradiction (i.e. adjust the spawn position of the
    sphere even if it is being spawned inside another object or overlapping with it)


- Enable **physics and gravity** for each sphere. You can decide about the mass and drag of the
    spheres.
- Make sure the fire spheres **do not collide** with the characters. In the other words, the characters
    can walk through the spheres and no physics interactions happen when these two collide. The
    spheres are physics sensitive toward the other objects, meaning that they will collide and react
    when touching other objects like the cubes or environment.
- When a character walks through a fire sphere:
    o After **1 second** , the sphere should **pop** using an **explosion particle effect**.
    o Use Starter Content or any particle effect you prefer.
- Each character should **track how many fire spheres they popped**.
- The game should also track the **total number of popped spheres** across all characters.

## 4. ELEVATOR AND FINISH ZONE

- Place an **elevator panel** in the level that moves **5 meters up and down** frequently.
- At the top of the elevator, place a **finish point** that cannot be reached without using the elevator.
- When **any character** reaches the finish point:
    o The level should only finish if:
       ▪ The **total popped spheres count is at least 40**
       ▪ Each character has popped **at least 10 spheres**
    o If these conditions are met, **reset the level**.
- To implement it, we recommend using Timeline node but you can implement it differently too.

## 5. FEEDBACK AND UI

- Use **Print String** nodes to:
    o Display messages when spheres are popped
    o Show how many spheres each character has popped

## 6. GAME LOGIC

- You can track the **total popped sphere count across all characters** using the **Level Blueprint** or
    another method of your choice.
- Ensure sphere counts per character are tracked and updated correctly when popping spheres

## Submission Checklist

Upload your project to TUWEL in one Zip file.

If it's larger than **250MB,** upload your project to **cloud storage** (e.g., Google Drive, OneDrive,
Dropbox).

## In your Zip file :

1. Add your **source project**. Be careful to exclude the folders that should be ignored by Git!
    o Exclude /Binaries, /DerivedDataCache, /Intermediate, /Saved
2. Build your project and add your **Built (Packaged)** files for Windows containing the .exe file
    o See here how to build and pack: https://youtu.be/BLXhZTK4HkY


```
o Use Shipping build configuration to build and pack to reduce its final size
```
3. Add a **screenshot** of your **Blueprints logic** used to:
    o Detect and pop fire spheres
    o Increase the popped sphere count for each character
    o Move the elevator
4. Include a **text file with an explanation** (at least 3 paragraphs):
    o What steps did you take to complete the assignment?
    o What part was the most challenging?
    o What did you learn while working on it?

## Grading Focus (Totally 20 points)

- Correct **input handling (4 points)**
- Correct implementation of **character switching (4 points)**
- Accurate **sphere collecting** and **score tracking (5 points)**
- Functional and smooth **elevator logic (3 points)**
- **Clear Print String feedback** for debugging and visibility **(2 points)**
- Logical, organized, and clean Blueprint design **(2 points)**

If you have any questions, ask on the course forum.

Good luck, and have fun building your first Unreal project!


