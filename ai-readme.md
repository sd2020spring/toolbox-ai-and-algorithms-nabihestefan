To use this astar GUI/toy, hit the 'l' key to switch to the 'add lava tiles' mode. Then you can click on any cell to add or remove a lava tile from that cell. Hit the spacebar at any time to have Paul plan (or replan) his path, and highlight that path. To see the f,g, and h values that astar calculates, take a look at the instructions in question 1. Feel free to reach out at any time about problems.

0. Read up on astar [here](http://web.mit.edu/eranki/www/tutorials/search/) and [here](http://www.raywenderlich.com/4946/introduction-to-a-pathfinding). Do your best to understand what the pseudocode in the links mean. What are the advantages that A star has over breadth-first search? What advantages does A star have over depth-first search?

1. Take a look at lines 124-127 of the code. Try commenting and uncommenting lines and running python astar.py to see what values are printed in each cell. Take a screenshot of each example with some lava tiles placed down, and in your own words, explain what f_score, g_score, and h_score are, and why you see those specific values in the screenshot.

For questions 2, 3, and 4, you should implement the code to get the specified behavior, but also place tiles and set up a scenario/path where that newly implemented behavior is demonstrated (ex. Paul moving diagonally or moving through a swamp.) Then include a screenshot and explanation. Quoting Paul, "Once you make a change, you should include a screenshot of the pygame window that shows the generated path for a given set of obstacles. You should be ready to explain why the shown path is actually the shortest (for instance… “the diagonal move while costly, is necessary in order to reach the goal, paths consisting of just up, down, left, or right would not be able to reach the goal”)."

2. Read the get_open_adj_coords() function and lines 204 to 210 to get an idea of how valid adjacent cells are found. In the current code, valid adjacent cells only include the surrounding cells in the 4 cardinal directions, and moving to any of these cells costs 1 movement point. Add code changing the get_open_adj_coords() function so that surrounding diagonal cells are considered valid adjacent cells and moving to any of these cells costs 3 movement points. This will allow Paul to
move diagonally.

> diag.png
> In my case, the diagonal photo I added shows Paul having to move diagonally, because, although costly, it is the only possible move.

3. Change the program so that pressing 's' allows you to add swamp tiles. Paul should be able to move through swamp tiles, but they will slow him down! Moving into a swamp tile will cost 3 movement points, so Paul should really avoid moving through swamp tiles unless he has to. A swamp.jpg file has been provided for you in the /images folder. You will probably have to make some changes to the costs in get_open_adj_coords and write your own add_swamp() function to get swamp tiles to behave correctly.

> swamp.png
> In this case, going all the way around and now going through swamp would cost more than just going through, because paul would move across the whole screen, thus, moving through the swamp is faster.

4. Evolve Paul and allow him to jump over lava! Add the ability for Paul to jump one square. This should cost 8 movement points, however. This will involve changing get_open_adj_coords().

> hop.png
> In this case, Paul has to jump over lava because he is completely blocked in, and the jump costs him 8 move points, but it is worth it.
