# Unix-Project-BattleShip-Game
###22101191우수흐바야르
###22101219테리겔

## Introduction

Boat Battle Game is a two-player turn-based strategy game where players draw boats on a grid and take turns shooting at each other's boards. The game continues until one player destroys all the opponent's boats or after a set number of rounds.

## Code Structure


### 2. player1.c and player2.c

#### Game Initialization:

- `initializeBoard`: Initializes the game boards.
- `printBoard`: Prints the current state of the board.

#### Drawing Boats:

- `drawBoat`: Allows players to draw boats on their boards.
- `displayBoards`: Displays the player's and enemy's boards.

#### Game Logic:

- `updateBoard` and `processShot`: Update the board based on a shot result.
- `getShotLocation`: Prompts the user to input a shot location.

#### Turn Implementation:

- `player1Turn` and `player2Turn`: Implement turns for Player 1 and Player 2.
- `countRemainingBoats`: Counts the number of remaining boats for a player.

#### Main Game Loop:

- `playGame`: Main game loop where players take turns until a win condition is met.

## Gameplay Flow

1. **Condision of starting game:**
   - Two player must connect to smae port.
   - Connect from different terminal.
3. **Drawing Boats:**
   - Players take turns drawing boats on their boards.
   - Input the boat location in the format: `boatNumber:startCell:endCell`.

4. **Taking Turns:**
   - Players alternate turns shooting at each other's boards.
   - Input the target location in the format: `columnNumber:rowNumber` (e.g., A1).

5. **Game End:**
   - The game ends when all boats of one player are destroyed or after a set number of rounds.
   - The player with the most hits at the end wins.

## Running the Game
```bash
gcc -o player2 player2.c -lsocket -std=c99
gcc -o player1 player1.c -lsocket -std=c99
```
```bash
./player1
./player2
```
these code must open on different terminal.


## Follow On-Screen Instructions:

- Input boat locations when prompted.
- Take turns shooting at each other's boards.

## Game Outcome:
- Our game is a standard turn-based Battleship game where players take shots at each other's boards, and the state of the boards is updated after each turn. The game continues until one player sinks all the ships of the other player.
- The game ends based on boat destruction or the number of rounds.
- The winner is determined, and the result is displayed.


## 1. Player's Board (Your Board):

Represented as an 8x8 grid.
Each cell on the player's board can be in one of two states:
‘point’: Represents water. This is the default state for unoccupied cells.
'X': Represents a hit. This symbol is used to mark cells where the opponent has successfully targeted and hit one of the player's ships.
![Player1](https://github.com/Usuhuuu/Unix-Project-BattleShip-Game-/assets/101633545/5fd75e6b-1eaf-4834-9227-585f7b28d898)
<img width="1512" alt="Player2" src="https://github.com/Usuhuuu/Unix-Project-BattleShip-Game-/assets/101633545/f611eec8-bb12-4a2f-8415-934a22dd7ec4">



 ## 2. Opponent's Board (Enemy Board):

Also represented as an 8x8 grid.
Each cell on the opponent's board can be in one of two states:
‘point’: Represents water. This is the default state for unoccupied cells and cells where the opponent has not yet targeted.
'X': Represents a hit. This symbol is used to mark cells where the player has successfully targeted and hit one of the opponent's ships.
