Lab 37 — BFS and DFS Implementation

Objective

Understand graph traversal algorithms and implement Breadth-First Search (BFS) and Depth-First Search (DFS) using Python.

1. Graph

A graph is a data structure consisting of:

- Nodes (Vertices): Individual elements.
- Edges: Connections between nodes.

We represented our graph using a Python dictionary.

2. Breadth-First Search (BFS)

BFS explores neighbouring nodes level by level.

- Uses a Queue.
- Follows FIFO (First In, First Out).
- Uses "deque" from Python's "collections" module.
- Uses "popleft()" to remove the first element.

BFS traversal output:

A
B
C
D

3. Depth-First Search (DFS)

DFS explores one path deeply before backtracking.

- Uses a Stack.
- Follows LIFO (Last In, First Out).
- Uses a Python list as a stack.
- Uses "append()" to add elements.
- Uses "pop()" to remove the last element.

DFS traversal output:

A
C
D
B

4. Important Concepts

Concept| Meaning
Graph| Nodes and connections
BFS| Breadth-First Search
DFS| Depth-First Search
Queue| FIFO
Stack| LIFO
"visited"| Tracks discovered/visited nodes
"deque"| Efficient double-ended queue

5. Challenges and Errors

- Learned that "print()" is needed to display output.
- Corrected Python indentation errors.
- Fixed a variable spelling mismatch ("neighbor" vs "neighbour").
- Learned that code blocks require consistent indentation.
- Successfully executed both algorithms.

6. Key Learning

BFS explores neighbours first, while DFS explores deeper into a path before backtracking.

Both are graph traversal algorithms used to explore connected nodes.

Status: Completed
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5dd86663-7d89-4b9c-a5c0-18532a807775" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ca2c635d-1f19-41ec-8c0b-12cf913950c8" />

