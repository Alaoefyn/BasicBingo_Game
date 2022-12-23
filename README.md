# BasicBingo_Game

Simple bingo game written in C++.

Tombala is turkish version of the game bingo.It was a school project so there is several things forbidden :)


The details of this game played in real life are listed below:
1) Tombala is a game of chance played over 3 sets with at least 2 and at most 5 players.
2) In the Tombala game, each player is given a unique (different) Tombala card with 15 integers on it at
the start of the game. These numbers are random numbers in the range of 1 (inclusive) to 90 (inclusive).
3) Each set of the game uses a bag of numbers in the range of 1 (included) and 90 (included). A number
is randomly drawn from this bag each time, and each player checks if the number exists on their
Tombala card. This process continues similarly until the game set is completed.
4) The first player with 5 numbers on his card is deemed to have made the first “Çinko”, the first player
having the card with 10 numbers drawn from the bagmakes the second “Çinko”, and the player with
all the numbers on his card drawn from the bag is deemed to have made “Tombala”.
5) The player who makes the first “Çinko” gets 5 points, the player who makes the second “Çinko” gets
10 points, and the player who makes the Tombala gets 15 points.
6) When any player makes Tombala, the game set ends.
7) The player with the highest score after 3 sets of games wins the game.
To simulate the game detailed above in a computer environment as a C++ console application, follow the
steps below:

i. Declare a two-dimensional array of 10 rows and 15 columns that can store integers in the int data type.
Each row of this two-dimensional array represents a Tombala card. Therefore, this array has the
capacity to store 10 different Tombala cards.

ii. Assign 15 unique random integers in the range of 1 (inclusive) to 90 (inclusive) to each row of this
array. For this, use the Function Prototype:
void KartlariOlustur(int[][15], int);
The first parameter of this function is the two-dimensional array that stores Tombala cards, and the
second parameter is the total number of cards. Then print the contents of the array on the screen similar
to the following output.
Eng: Loading Tombala Cards... / Tr: Tombala Kartları Hazırlanıyor...
Eng: Card number / Tr: Kart No

iii. Get the number of players (minimum 2 and maximum 5) from the user through the keyboard and
randomly assign one of the cards stored in the two-dimensional array to each player. Then, print the
players’ cards on the screen similar to the following output.

iv. Declare a 90-element one-dimensional array that stores integers in the int data type to represent the
Tombala bag in a computer environment. Assign unique random integers in the range of 1 (inclusive)
to 90 (inclusive) to each element of this array. Then print the contents of this array on the screen similar
to the following output.

v. The first element of the one-dimensional array represents the first number drawn randomly from the
bag during normal game, and likewise, the second element represents the second number to be drawn
from the bag. Therefore, continue the game by taking into account all the elements of this array one
by one and checking them over the Tombala cards of all players. For example, the output above tells
us that the first number to search for Tombala cards is 74 and the second number is 17.

vi. The first player with 5 numbers on his card drawn from the Tombala bag makes the first “Çinko” and
gets 5 points. When the first “Çinko” is completed, print on the screen similar to the output following
which player made the first “Çinko” and the final status of the players’ cards. Use the number “-1” on
the cards instead of the numbers drawn from the bag.

vii. The first player with 10 numbers on his card drawn from the Tombala bag makes the second “Çinko”
and gets 10 points. When the second “Çinko” is completed, print on the screen similar to the output
following which player made the second “Çinko” and the final status of the players’ cards. Use the
number “-1” on the cards in place the numbers drawn from the bag.

viii. The first player with 15 (All) numbers on his card drawn from the Tombala bag makes the Tombala
and gets 15 points. When the Tombala is made, print on the screen similar to the output following
which player made the Tombala and the final status of the players’ cards. Use the number “-1” on the
cards in place the numbers drawn from the bag.

x.2 more sets (3 sets in total) must be played. In each new set, players must be
assigned different random Tombala cards and the Tombala bag must be filled with different random
numbers.

x. At the end of the game, print the total points of the players and the winning player (the player with the
highest score) on the screen.


ATTENTION!

-Your application must contain at least 4 sub-functions. At least 2 of these functions should take two-
dimensional or one-dimensional arrays as parameters.

-It is not allowed to use global variables. (Variables defined before main are called global variables. In
other words, variables whose scope are both main functions and other functions are called global
variables.)

-C style library declaration is not allowed. All library declarations must be in C++ style. For example,
<ctime> should be used instead of <time.h>.
  
-Relevant libraries must be included in your application. For example, in order to use the rand and
srand functions, the <cstdlib> library must be included to your program.
  
-Camel notation should be used in variable naming and pascal notation should be used in function
naming.
  
-Any use of recursive functions is not allowed.
  
-Changing the program flow using the goto statement is not allowed.
  
-Comment lines must be added to the program where necessary.
