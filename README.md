# tic-tac-toe
tic tac toe game using python

Minimax background

The minimax algorithm is attributed to John von Neumann (1928, Zur Theorie der Gesellschaftsspiele), but its key features were described earlier by Émile Borel (1921, La théorie du jeu et les équations intégrales à noyau symétrique). It has also been sugested that Charles Babbage may have known about the algorithm. Irregardless of who formalised it, anyone who has ever played Draughts, Chess, Go, or countless other games, has used it. At any point in the game you choose your next move by thinking several ahead, and considering what you and your opponent will do to maximise their respective chances of winning. In the formal version 'several ahead' means all the way to the very end, where one of you has won.

Minimax is an algorithm of game theory (a term invented by von Neumann with Morgenstern), which formalises how to act when you are in competition with others (If you want to know more then The Joy of Game Theory by Presh Talwalkar is a friendly introduction). The basic version introduced here is for finding the optimal move in zero sum games that are turn based with two players where everything is deterministic and observable_, and you have enough computation/memory to exhaust the _search tree. To define these terms:

zero sum: There are n points to be won and they are distributed between the players at the end of the game. In other words, there is no possibility of cooperation, and one players fortune is anther's loss. Any game where one player wins and the other loses satisfies this; a draw is half the points to each player.
turn based: Players take turns to make a move.
two player: There are two players!
deterministic: No dice. The consequence of any action is known, exactly.
observable: No secrets, so both players know everything.
search tree: This is every possible state the game can be in, and the transitions (moves) between them made by the players.
The minimax algorithm is solving the Nash equilibrium (Its discovery is the subject of the film A Beautiful Mind (2001)) for games with the above properties. Note that many of the above properties can be relaxed with more sophisticated versions. Even when it can't approximations are used: Alpha Go used minimax to beat homosapiens at Go, but never could have held the entire search tree of Go in memory; that would be more states than there are atoms in the universe... even after you bulked up by replacing every atom with a copy of the universe. Instead, it used machine learning to estimate what the probability of winning from any state was, so it didn't have to search to the end.


It can be challenging to develop an algorithm without being able to see what it is doing. Your first task is to write a function that visualises the state of the board, using the ascii-art style used above.

To represent board states we're going to use a tuple of tuples, so that you may index them with [row][column], where [0][0] is the top left and [2][2] the bottom right. A space (' ') indicates an unused slot, a cross ('x') somewhere the first player played, a circle ('o') somewhere the second player played.

You will need to call the print() function for each row of output. You will find that the print() function inserts spaces between every item you provide it. This is because the default parameter to the sep keyword parameter is ' ' - you will want to change it to ''. Alternatively, you can use .format() or f''; there are other approaches as well! (if you want to print() without a new line add the keyword parameter end='')


def print_state(state):
    """Prints the state."""
    print(state[0][0]+'|'+state[0][1]+'|'+state[0][2],sep='')
    print(state[1][0]+'|'+state[1][1]+'|'+state[1][2],sep='')      
    print(state[2][0]+'|'+state[2][1]+'|'+state[2][2],sep='')      
    
print_state(((' ',' ',' '),(' ',' ',' '),(' ',' ',' ')))
print() # This adds a newline, so the outputs are not vertically next to each other

print_state((('o','x','x'),(' ','x','o'),('o','x',' ')))
print()

print_state((('o','o','o'),('x','x','x'),(' ',' ',' ')))


