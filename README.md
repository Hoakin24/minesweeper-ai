# Degrees of Separation

This repository contains a Python program that calculates the degrees of separation between two actors or actresses based on the movies they have starred in. It uses a simple graph search algorithm to find the shortest path connecting the two individuals through shared movie appearances.

## How to Run

To run the Movie Degrees of Separation program, you will need to have Python installed on your system. Clone this repository and navigate to the project directory. Then, run the following command:

```
python degrees.py [directory]
```

The optional `[directory]` argument specifies the data directory containing the CSV files for people, movies, and stars. If not provided, the program will use the "large" directory by default.

You will be prompted to enter the names of the two actors or actresses for which you want to calculate the degrees of separation. The program will then display the result if a connection is found.

## Files

- `degrees.py`: This is the main Python file that contains the implementation of the degrees of separation algorithm. It loads the data from CSV files, performs the graph search, and displays the result.

- `util.py`: This file defines utility classes used in the graph search algorithm, including the `Node` class for representing nodes in the search and the `StackFrontier` and `QueueFrontier` classes for managing the search frontier.

## Dependencies

There are no external dependencies required to run this program.

## How the AI Works

The Movie Degrees of Separation program uses a graph search algorithm to find the shortest path between two actors or actresses through shared movie appearances. It builds a graph where each node represents a person, and each edge represents a shared movie appearance. The program then performs a breadth-first search or depth-first search on this graph to find the shortest path between the source and target nodes.

1. Loading Data: The program first loads the data from CSV files into memory. It creates dictionaries to map person names to person IDs, person IDs to person information (name, birth, movies), and movie IDs to movie information (title, year, stars).

2. Finding Degrees of Separation: When the user enters the names of the source and target actors or actresses, the program retrieves their corresponding person IDs from the loaded data. If either person is not found, the program exits with an error message.

3. Graph Search: The program uses either a breadth-first search or depth-first search to explore the graph and find the shortest path between the source and target nodes. It creates a node for the source person and adds it to the search frontier. The search frontier is implemented using a stack (for DFS) or a queue (for BFS).

4. Exploring Neighbors: The program explores each person's neighbors (i.e., people who starred in the same movies) and adds them to the search frontier if they have not been explored yet.

5. Backtracking Solution: Once the target person is found during the graph search, the program backtracks the path from the target node to the source node to reconstruct the shortest path. It then prints the number of degrees of separation and the sequence of movie connections between the two individuals.
