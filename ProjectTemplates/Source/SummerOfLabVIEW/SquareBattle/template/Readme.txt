*** Do not edit any of the code in the dependencies in the project. If there is an issue in any code in the dependencies contact Derrick Bommarito. The Squares folder exists to ensure the provided examples get copied properly with the project. Feel free to look at these squares for implementation ideas!

1. To get started on the implementation, open the bookmark manager (View menu -> Bookmark Manager) and implement the code according to the notes.

2. The MyTeam instance already includes all the overrides available. More VIs can be added to the MyTeam to perform additional functionality as desired. As examples, the MyTeam class can perform functionality such as maintaining a map of squares, coordinating behaviors across squares, and keeping track of the location and team index of aggressive opponents.

3. The MySquare class is intended to be the first square placed on the battlefield but more classes can be implemented if desired to provide different behaviors. If you want to create another square, add a new class to the SquareTeam library that you renamed in (1) and have it inherit from the Square class (same as MySquare).

4. You can run the Launch SquareBattle VI to be able to run games with your square that is being developed and run it against other provided or downloaded square teams.

*** Intro Videos ***

If you prefer video explanations of the game you can check out a quick intro (< 4 minutes) at https://www.youtube.com/watch?v=c6kcpe6oSuQ

A more in-depth introduction with full coverage of the rules and a walkthrough of implementing some basic strategies is available at https://www.youtube.com/watch?v=1_T_jAQ0_dw

*** Game Rules ***

Each round the game engine iterates over all squares that are able to take an action and calls their Run.vi so that their action can be collected. Squares are able to specify from 4 possible actions each round:
	1. Wait - Does nothing and remains at its current location.
	2. Move - The square will move in the specified direction (8 cardinal and ordinal compass directions).
	3. Attack - If a square is present at the specified adjacent location, specified by direction from the attack square, it will be eliminated.
	4. Replicate - A new square is created in the specified direction from the parent square. Both the new square and the parent square will be inactive for a number of rounds, 50 by default.
	
After all the desired actions are collected the engine goes through a couple of actions:
	1. Process moves and replications.
	2. Handles collisions - in any location where more than a single square is present, all squares at that location are eliminated.
	3. Process attacks.
	
Each of the above processing phases is accomplished effectively in parallel, since all of the actions were collected before performing them. The game does not protect against your own squares moving into the same location or one of your squares attacking another friendly square. It is up to you to implement strategies and logic that prevent/reduce collisions and friendly fire.

In the final tournament run to wrap up the Summer of LabVIEW competition, all standard matches will be run at the default maps settings: 150 board size and 50 replication rounds. Every set of matches will be run with the same time limit, which will be determined based on the submissions and how they run but is expected to also be the default value of 10 minutes. The time limit is only for the time it takes to collect and process actions and does not include time that the engine spends updating the UI.

The game engine also has a video recording mode where you can separately download FFMpeg for Windows and then trying to turn on recording mode it will prompt for the location you placed ffmpeg.exe at. This is accomplished by saving images of the GUI each round and then using FFMpeg to convert the image frames into a 30FPS video. If you plan on running your own tournament, it is highly recommended to use the recording capability and playing back recordings of the matches as the game gets progressively slower the more squares it needs to process.

If you have any questions about SquareBattle or Summer of LabVIEW you can join the Summer of LabVIEW Discord server at https://discord.gg/KxtUER4NGS