# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propagation is a technique used to optimise performance of the function or algorithm by reducing the number of elements we have
to look through to find the values we are looking for or to find an optimal solution to the problem (in Sudoku it is usually expressed as some 
constraints applied on which values should be taken into consideration to do a search on and solve the puzzle). The aim of naked twins function
is to check if there are any twin boxes in a unit (two boxes which consist of two exactly the same digits) and remove those digits from shared 
peers of those twin boxes. The reason for this is that if two boxes in a unit have two exactly the same possible digits, we can state that those 
two digits can't be assigned to any other peer box, but those two boxes which have these digits as their only two options. By removing those twin 
digits from other peer boxes, we reduce the number of iterations needed to solve the puzzle. We apply constraint propagation while looking for 
naked twin boxes as well. Naked twins can only be boxes with two digits inside and their peers which might potentially be affected by naked twins
technique also have at least two digits. With that in mind for every two digit box, we scan their two digit peer boxes to find whether or not it 
has any twin values. In the end, we scan through non-one digit shared peer boxes of identified twin boxes to check if they have digits from naked twin 
boxes and remove those digits from the peer boxes if any of them were found.



# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: To solve a regular Sudoku we use constraints on which boxes and units we should take into account when solving the puzzle - we look though the boxes 
of the peers (column, row units as well as square units), we also apply elimination technique which scans through the peers and if it finds a value in
it, it will remove that digit from all of it's peer boxes. In addition to this we apply only choice technique which looks through the peer values and 
if it finds that there is a unit with a value that only fits in one box, it assigns the value to this box. Diagonal sudoku requires all these 
constraints as well as two additional diagonal units (boxes which are on the the main diagonals of the board) which means that we will have to 
include these two diagonals to the list of units. After we add diagonals to the units, we can apply elimination and only choice techniques to solve the
puzzle.



### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

