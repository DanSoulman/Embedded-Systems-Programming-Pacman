# Embedded-Systems-Programming-Pacman
A simple Pacman application for the QEMU emulated versatilepb board.

#Object of the game: 
The player controlled character is pacman. He must move around collecting dots in a maze while avoiding ghosts. In this iteration of the game each dot is worth 100 points. If all dots are collected you win and the game ends. If you touch one of the 2 roaming ghosts the game ends early. Afterwards the score you recieved is printed out. 

The game is made up of a series of bmp (bitmap) image files. There are 2 kinds, firstly there is the map which is made of a number of sections. These are walls, dots, and blank spaces. Walls are areas where the pacman bitmap sprite cannot move to. There are also spaces with dots which pacman must collect, and blank spaces that he is free to move to also but do not have points. If a dot is collected 100 points are awarded and the space becomes a blank space.
In the initial zip files there is no collision on the walls and the dots cannot be collected. However these are implemented in the completed version. 

The other kind of bitmaps are the sprites. These are much smaller bitmaps representing the characters. Pacman is controlled by the player character using the WASD keys on the keyboard . Each time he is moved we must update the screen to show his new location and remove him from his previous location. This is done by calling the show_bmp function which takes in a pointer to the sprite, his initial value on the x and y coordinates a buffer of 16x16 pixels to represent the pixels he takes up and his previous x and y coordinates. When Pacman is moved he takes up the space 16 pixels (aprox. 1 square) over in the direction he is moved and putback is called. This replaces pacman with the buffer of space he took up. The previous coordinates are then set to the location he's moved to the new pixels he replaced take up the buffer. The ghosts operate on a similar concept but are not player controlled, and use the function show_bmp1 in the initial version they always moving right and like pacman have no collision detection. In the final version the ghosts are moved in a random direction using a random number from 0-3 and a switch statement. They will travel that direction until they hit a wall. They also cannot travel through walls. 
