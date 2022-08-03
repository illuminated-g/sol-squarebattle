*** Do not edit any of the code in the Deps folder in the project. If there is an issue in any code in the dependencies contact Derrick Bommarito.

1. After copying this template folder, open the project and rename the SquareTeam.lvlib to a different name. The new name isn't super important but should not have the same name as anybody else's team library so a safe bet is to include your name. If creating multiple teams, make sure each library rename includes your name and the unique team name.

2. To get started on the implementation, open the bookmark manager (View menu -> Bookmark Manager) and implement the code according to the notes.

3. The MyTeam instance already includes all the overrides available. More VIs can be added to the MyTeam to perform additional functionality as desired. As examples, the MyTeam class can perform functionality such as maintaining a map of squares, coordinating behaviors across squares, and keeping track of the location and team index of aggressive opponents.

4. The MySquare class is intended to be the first square placed on the battlefield but more classes can be implemented if desired to provide different behaviors. If you want to create another square, add a new class to the SquareTeam library that you renamed in (1) and have it inherit from the Square class (same as MySquare).

5. <Testing and UI still being developed>