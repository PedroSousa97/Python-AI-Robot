# Python-AI-Robot

The objective of this project was to develop a robot and the environment where it will act. For this, a robot was created and programmed, and heuristics and strategies developed that incorporate knowledge about this type of problems and allow them to be solved in a more effective way.
The robot was created using Lego EV3 and coded with Python.

### The Game

There are four pieces of different colors and each piece has a symbol (o, +, -, x).
The board for this game measures 5x5. The objective of the game is to arrange all the pieces of a random sequence of pieces on a board with the dimension n x n, in order to obtain as many points as possible.
The pieces are placed initially in such a way that they can be read and known by the robot at the beginning of the game. The starting tray is empty. Points are obtained when complete figures are formed. The pieces that form these figures are eliminated from the board (by the group members, not by the robot).

The final score of the game (that is, of a solution) is obtained by adding the scores obtained during the game with the elimination of the pieces. For each figure complete with n pieces that is eliminated, 2^n points are added to the score.
In the case that there is no solution, and regardless of whether some pieces were eliminated during the game, the final score is 0 points.

### Heuristics

#### First Heuristic

Simpler heuristic and the first to be implemented. Selected by pressing the EV3 button (->).
* In this heuristic, only small figures are created;
* The heuristic is based on dividing the game board into 4 parts and each part corresponds to a figure;
* There is always room for any of the 4 figures, at any time during the game;
* Thus, the focus is on creating as many figures as possible, without ever conflicting or lacking space to create them (safe method);
* As for the order in which the pieces are placed, each piece is placed from the LEFT -> RIGHT and from UP to DOWN;

##### Parts

[-] = TOP LEFT CORNER
[X] = TOP RIGHT CORNER
[O] = LEFT LOWER CORNER
[+] = LOWER CORNER RIGHT

##### Benefits

* Safer method of playing;
* It always works, regardless of the number of pieces or their order;
* Simple and easy to implement heuristic;

##### Disadvantages

* In some situations / games, fewer points are made than the maximum possible because, even if there is a possibility, large figures will never be created (which give more points but also offer a greater risk of conflict).

#### Second Heuristic

Second heuristic to be implemented and the most complex. Selected by pressing the EV3 (<-) button.
* For this heuristic, priority is given to creating figures with the largest possible dimension (which give a higher score but offer a greater risk).
* Each figure has an ideal position that allows, almost always and in the vast majority of cases, to leave free space for the creation of the others.
* For each position (square) there is a rank or priority.
* The robot uses this priority (in ascending order) to place the pieces so that they are always in the most appropriate position for the creation of the figure in question as well as the possibility of creating other figures.
* There are also escape scpaces (Garbage) that allow "storing" pieces that will no longer be able to form figures, thus leaving the remaining squares free for the formation of new / other figures.

##### Benefits:

* Extremely effective method, obtaining the vast majority of times the same result as the group itself, but more quickly.
* It aims at the greatest number of points, focusing on creating large figures first and only then, if it is not possible, small figures.
* Heuristic that covers most of the possible problematic cases (whether using the Garbage List, priorities, etc.)

## Authors

* **Pedro Sousa**
* **João Freitas**
* **Luís Miguel**
* **Gonçalo Castro**
* **Nelson Graça**
