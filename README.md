# Monty Hall Simulation
* Author: Paul Ebreo

## How To Run
Click the .ipynb file above.

## Purpose
The Monty Hall puzzle is a puzzle that describes a situation where
you are a contestant in a game show where you can win a car by choosing
1 of 3 doors. Behind 2 of the doors is a goat and 1 is a car. 
In this situation, you have chosen Door # 1. Monty Hall, the host of the
show, opens Door #3 and shows you that there's a goat behind that one. 
Is it better to switch to Door #2 (the door without the goat) or stick to your original decision of Door #1?

The purpose of this program is to simulate this situation and compares
the number of winnings of the two strategies a) stay in your original pick of Door #1
or b) choose the other door that doesn't have a goat, in this case Door #2.

## How it works

-For the stay strategy

1. Setup the board in `set_doors()` function by choosing a goat
2. Set player selection by doing `selection = door1`
3. Check if the player wins
4. Add the result to `win_loss_result` list


-For the switch strategy

1. Setup the board as the stay strategy
2. Set the player selection by doing `selection = door1`
3. If the car is in door 2 or door 3, open the door with goat behind it and set `shown_goat = door-x`
4. Based on this condition, the player selection will be the opposite of `door-x`
5. Check if the player wins
6. Add the result to `win_loss_result` list

After running through 1000 iterations, we run `calculate_stay_strategy` and `calculate_switch_strategy` function and calculate
the win ratio `wins / (wins+losses)`. And that's it.

## Results
Based on the results, we see that about 2/3 of the time you win when 
you decide to switch to the Door #2. You win 1/3 of the time when you decide to 
stay.

## Mathematical Discussion
When the board is set, the car will always have 1/3 chance to be in Door #1
and 2/3 chance to be either in door 2 or door 3 (1/3 + 1/3 = 2/3).
When door 3 is opened, the chance of door 3 becomes zero and door 2 becomes
2/3. Because the two doors (2 and 3) combines must always be 2/3 (2/3 + 0 = 2/3).
Another way to think of the always switch strategy is that when you've decided to
always switch to either door 2 or 3 you'll always have 2/3 chance of winning and 1/3
chance of losing (1/3 chance that the car is actually in door 1). And the fact
that Monty shows the goat does not change the odds of 2/3 chance that the car will be in 2 or 3, rather it changes the fact that you know it won't be in door 3. It's important to note
that the total odds don't change, for 2 and 3 just where those odds have shifted.

<insert picture>

Explaining the mistaken intuition:
Most people mistakenly think that total odds change when the door is opened. 
That is they think it becomes 50/50 or 1/2. The odds don't change they just shift
in your favor to door 2 because the sum must always be 2/3 for door 2 OR door 3.



[demolink]: http://pebreo.github.io/blah "IPython Notebook"
