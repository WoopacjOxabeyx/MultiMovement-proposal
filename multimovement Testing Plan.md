1. Overview
Describe in several sentences what this document is and what it will cover
Testing cases
2. User Stories and Acceptance Criteria
User Story 1:  As a trickshotter, I want to pull off risky strategies so that I can get rewarded more for my efforts.
- Acceptance Criterion 1 
    - Requirement(s): The game rewards you for harder tricks
    - Purpose: This will incentivize players to go for more risky strategies
    - Test Case:
        a) Feature: 
        b) Test: do a 360 noscope
        c) Expected Result / Behavior: if the shot is successful, it will reward the player bonus points
        d) Automation Candidate: Yes, rule based


- Acceptance Criterion 2 
    - Requirement(s): The game gives you opportunities and the tools you need to attempt trickshots
    - Purpose: This will also incentivize the player to go for different strategies
    - Test Case:
        a) Feature: more weapons
        b) Test: the player has one weapon that launches an enemy and another that does increased damage to airborne targets
        c) Expected Result / Behavior: the user experiments with their arsenal and finds ways that they synergize with each other
        d) Automation Candidate: No




User Story 2:  As a speedrunner, I want to go as fast as possible, so that I can get a quick time.
- Acceptance Criterion 1 
    - Requirement(s): The game’s cutscenes are skippable
    - Purpose: this cuts down speedrun times and attempts, which makes the game more fun to speedrun
    - Test Case: 
        a) Feature: skippable cutscene
        b) Test: player holds down skip button
        c) Expected Result / Behavior: The game immediately skips the cutscene and goes into the game
        d) Automation Candidate: Yes, repetitive


- Acceptance Criterion 2 
    - Requirement(s): The game’s doors open quicker and earlier based on your movement speed
    - Purpose: It won't stop you at fast speeds
    - Setup: if going over a certain threshold of speed, play faster animation
    - Test Case:
        a) Feature: fast doors
        b) Test: player runs into door at fast speeds
        c) Expected Result / Behavior: the doors open faster
        d) Automation Candidate: Yes, rule based




User Story 3:  As a new player, I want to learn the mechanics, so that I can get better at the game
- Acceptance Criterion 1 
    - Requirement(s): There is a tutorial to teach the player the ropes of the game
    - Purpose: this is in case somebody doesn’t know how to play a movement shooter
    - Test Case:
        a) Feature: tutorial
        b) Test: player plays the tutorial
        c) Expected Result / Behavior: the player understands how to play the game
        d) Automation Candidate: No


- Acceptance Criterion 2 
    - Requirement(s): There are easier modes    
    - Purpose: you don't have to be perfect to have fun
    - Setup: make all of the enemies do less damage and have less health
    - Test Case: 
        a) Feature: easy mode
        b) Test: player gets damaged by enemy
        c) Expected Result / Behavior: player takes less damage than on normal
        d) Automation Candidate: Yes, repetitive


3. Boundary and Edge Testing
Boundary / Edge 1:  Player Position
    - Requirement(s): player should stay within the boundaries of the map
    - Purpose: it defeats the whole purpose of a video game if you could just walk to the exit


    - Test Case 1: Inside of ground
        a) Testing data used: <y = -2, y = -5>
        b) Expected Result / Behavior: player should gradually be pushed back upwards
        c) Automation Candidate: Yes, repetitive


    - Test Case 2: Outside of map
        a) Testing data used: <y = -25>
        b) Expected Result / Behavior: player will be killed instantly
        c) Automation Candidate: Yes, repetitive




Boundary / Edge 2:  Weapons
    - Requirement(s): weapon switching should work properly
    - Purpose: if you are in the heat of battle, you do not want your gun to break


    - Test Case 1: Switching to a weapon while still deploying a different one
        a) Testing data used: <weapon#1 + weapon#2>
        b) Expected Result / Behavior:
        c) Automation Candidate: Yes, rule based


    - Test Case 2: Switching the weapon while firing
        q) Testing data used: <mouse 1 + weapon# >
        b) Expected Result / Behavior: the shot fires, and the gun switching animation takes place (in that order)
        c) Automation Candidate: Yes, rule based




Boundary / Edge 3: Enemies
    - Requirement(s): make sure that there is a correct amount of enemies
    - Purpose: that is what half of the game is about


    - Test Case 1: Too much enemies
        a) Upper Boundary: as much as you ram can handle
        b) Testing data used: <9998 enemies, 9999 enemies>
        c) Expected Result / Behavior:Stop spawning enemies, free up space (despawn dead bodies, decals, etc.) and when the space is allocated, spawn more enemies
        d) Automation Candidate: Yes, rule based


    - Test Case 2: Negative enemies
        a) Lower Boundary: 0
        b) Testing data used: <-1 enemies, 0 enemies>
        c) Expected Result / Behavior: enemy count returns to 0
        d) Automation Candidate: Yes, repetitive