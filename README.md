# Minesweeper AI

This repository contains an implementation of an AI player for the game of Minesweeper. The AI uses logical reasoning and inference to make educated guesses about the locations of mines in the game board.

## How to Run

To run the Minesweeper AI, you will need to have Python installed on your system. Clone this repository and navigate to the project directory. Then, run the following command:

```
python runner.py
```

This will start the Minesweeper game with the AI player. You can interact with the game by clicking on cells to reveal them or right-clicking to flag them as mines. The AI player can be activated by clicking the "AI Move" button.

## Files

- `runner.py`: This is the main file that runs the Minesweeper game with the AI player. It contains the game loop and the GUI code using the Pygame library.

- `minesweeper.py`: This file defines the `Minesweeper` class, which represents the game board and provides functions to interact with the board, such as revealing cells and counting nearby mines. It also defines the `Sentence` class, which represents a logical statement about the game and is used by the AI player to reason about the board.

## Dependencies

The Minesweeper AI requires the Pygame library to be installed. You can install it using pip:

```
pip install pygame
```

## How the AI Works

The Minesweeper AI uses logical reasoning to make educated guesses about the locations of mines in the game board. It maintains a knowledge base, which consists of logical statements (sentences) about the game. Each sentence represents a set of cells and the count of nearby mines. The AI uses these sentences to infer new information about the board.

When the AI makes a move, it first checks if there are any cells that are known to be safe or mines based on the current knowledge base. If so, it selects one of those cells as the move. Otherwise, it applies logical inference to make a move. It iterates over each sentence in the knowledge base and checks for two types of inferences:

1. Known Mines: If the count of nearby mines in a sentence is equal to the number of cells in the sentence, all cells in the sentence are known to be mines.

2. Known Safes: If the count of nearby mines in a sentence is zero, all cells in the sentence are known to be safe.

The AI continues making moves and updating its knowledge base until it either wins the game (flags all mines) or determines that it cannot make any more safe moves.
