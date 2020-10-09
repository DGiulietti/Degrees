# **CS50 STUDENTS, TAKE NOTE**
### This repository contains my homework submission for the Degrees problem set. If you have not already submitted your homework, please keep in mind cs50's academic honesty policy. In other words, spoiler warning!

----

A "Seven Degrees of Kevin Bacon"-like tool, this assignment puts into practice *Breadth First Search* (BFS) instead of *Depth First Search* (DFS) to find the shortest path of connections between one actor to another. The data in **large** and **small** is provided from IMDB and is structured such that there is are three CSVs: one for movies and their IDs, another for people and their IDs, and lastly "stars.csv" which acts as a join table to link both people and movies by IDs.

**util.py** contains many of the critical classes required in a designing an AI for search, including the structure for a node and the methods for a stack frontier (used for BFS) and a queue frontier (used for DFS). **degrees.py** implements the pseudo code:

1. Start with frontier that contains initial state
2. If the frontier is empty, then no solution
3. Remove a node from the frontier
4. If node from step 3 contains goal state, return the solution
5. Add the node from step 3 to explored set
6. Find the neighboring nodes to the node from step 3, and add 
resulting nodes to the frontier if they aren’t already in the 
frontier and they aren’t in the explored set
7. Repeat from step 2.

To run code:
`python degrees.py [database]`

Example:

````
$ python degrees.py large
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix
2: Brendan Gleeson and Michael Fassbender starred in Trespass Against Us
3: Michael Fassbender and Jennifer Lawrence starred in X-Men: First Class
````