---
title: Wheel of !Fortune
length: 2 weeks
tags: javascript, jquery, svg, mocha, testing
---

2 week paired project for FE Mod 2 (week 2-3)

## Dataset

Copy [this dataset](https://repl.it/@thatpamiam/WheelOfFortune) into a `.js` file under the `src` directory of your repo.


## User Stories

These user stories may be worked on in any order that makes sense to your group.

``` 
Game play,
  - Must have 3 players
  - Must have 4 rounds - 4 rounds make up 1 game
  - The winner is determined by the player with the highest grand total score at the end of all rounds
  - Each player starts with a score/account of 0 at the start of every round
  - Each player's score should be displayed by their name
  - The player who solves the puzzle is the only one keeps all of the money from their account for the current round. This money is added to their grand total score
  - The player with the highest score after 4 Rounds will play in a Bonus Round with a Bonus Wheel.
  - Winning score should be added to a leader board
```

```
Puzzle,
  - The game should have at least one bank of puzzles. One bank should be chosen at the start of the game
  - A word puzzle is randomly chosen at the start of every round
  - Each puzzle has a category (or class) (e.g. "phrase," "person," "things," etc)
  - Each puzzle is one or more words that is an instance of the category/class
  - Initially, the letters of the puzzle will be hidden
  - There will be clear indications in the UI to indicate hidden letters and spaces
  - The UI will keep track of what letters have already been guessed
  - The category for the puzzle will be displayed as a hint 
```

```
Wheel,
  - A new randomized wheel is chosen at the start of every round
  - Wheel must have at least six elements
  - An element can either be a positive whole dollar amount, a "Lose-a-turn", or a "Bankruptcy" element
  - The elements of a wheel are in a 'randomized' order
  - The Bonus Wheel elements can either be a special prize or a dollar amount.
```

```
As a player,
  I should be able to quit/start a new game at any time.
  
  I have three options when it is my turn:
  1) Solve the puzzle
    - If I guess correctly, my grand total score is increased by my current score and the round is over
    - If I guess incorrectly, my turn is over
  2) Spin the wheel
    - A random element will be chosen for my spin
    - If a bankrupt element is chosen, my score/account will be reset to 0
    - If a lose-a-turn element is chosen, my turn will end
    - If an element is chosen with a dollar amount, I will be prompted to choose a consonant
  3) Buy a vowel
    - The cost or buying a vowel is $100
    - I should be prompted to enter what vowel I would like to buy
    - $100 is subtracted from my score/account regardless of whether the vowel is part of the puzzle.
  
  I will participate in the Bonus Round if I am the top player at the end of 4 rounds. I will be given a new puzzle with up to six consonants revealed. I can pick 1 vowel and 3 consonants before attempting to solve the puzzle.
    - If I guess correctly, I will win the prize or cash award from the bonus wheel and the money from my grand total account
    - If I guess incorrectly, I will win the money from the grand total account only. 
```



<!-- Organized User Stories

***EPIC: Game Mechanics*** _#Game Mechanics_  


*Issue title*  
User Story 1, Basic Game Mechanics

```
As a developer of the game, 
I must allow 3 players to play the game,
and I must allow 3 rounds of play for all players, plus one bonus round for the winner.

* [ ] done

child of #Game Mechanics

child of #Core Application
```

*Issue title*  
User Story 2, Game Mechanics, Puzzle

```
As a developer of the game,
I must generate a list of puzzle words (or phrases).
This list is called a "bank" of puzzles.
Each word/phrase has a category such as "phrase", "person", "things" etc

* [ ] done

child of #Game Mechanics

child of #Core Application
```

*Issue title*  
User Story 3, Game Mechanics, Wheels

```
As a developer of the game,
I need to be able to randomly generate a "wheel" for each round.
The wheel will have at least 6 prize sections.
Each section can be one of the following:

- positive dollar amount
- lose a turn
- bankruptcy

My wheel generator must be able to generate a "bonus round" wheel.
The "bonus" wheel only contains positive dollar amounts.
The dollar amounts are 10x larger than a regular wheel.

* [ ] done

child of #Game Mechanics

child of #Core Application
```

*Issue title*  
User Story 4, Beginning a Game

```
As a visitor,
When I visit the web page,
Then I see a button to start a new game.
Clicking this button starts a new game
Even if one was already in progress.
The game chooses at least one "bank" of puzzles.

* [ ] done

child of #Game Mechanics

child of #Core Application

depends on #1
```

*Issue title*  
User Story 5, Setting Up a New Game

```
As a visitor,
When I begin a new game,
All "game" scores are reset to 0,
And I am prompted to enter the names of three players.
The new game begins when I successfully enter three names.
I see scores of 0 next to each player's name.

* [ ] done

child of #Game Mechanics

child of #Core Application

depends on #4
```


***EPIC: Playing a Round*** _#Playing A Round_


*Issue title*  
User Story 6, Playing a Round, Step 1

```
As a player of the game,
When a round begins,
A random puzzle word is chosen
A random wheel is generated
Each player is given a "round" score of $0
This score is not the same as their "game" score.

* [ ] done

child of #Playing A Round

child of #Core Application

depends on #5

depends on #3

depends on #2
```

*Issue title*  
User Story 7, Playing a Round, Step 2

```
As a player of the game,
When a round begins,
The UI hides all letters of the puzzle word/phrase
The UI shows the category of the puzzle
The UI shows clear indications of letters/spaces in the word/phrase

* [ ] done

child of #Playing A Round

child of #Core Application

depends on #6
```

*Issue title*  
User Story 8, Playing a Round, Step 3

```
As a player of the game,
Until the round is finished,
Each player is prompted to choose one of three actions:

- solve the puzzle
- spin the wheel
- buy a vowel

The UI should show an easy way to input this choice.

* [ ] done

child of #Playing A Round

child of #Core Application

depends on #7
```

*Issue title*  
User Story 9, Playing a Round, Step 4

```
As a player of the game,
The UI updates to show all letters and vowels guessed during the round.

* [ ] done

child of #Playing A Round

child of #Core Application

depends on #7

depends on #15

depends on #10
```

*Issue title*  
User Story 10, Buying a Vowel

```
As a player of the game,
If I choose to buy a vowel,
The UI allows me to enter a choice.
My choices are A, E, I, O, U only.

If there are remaining vowels to guess
My "round" score is reduced by $100.
If I guess a vowel that was already chosen,
I get to guess again

If there are no remaining vowels to guess,
My "round" score is not reduced by $100
And my turn is over.

* [ ] done

depends on #8
```


***EPIC: Spinning the Wheel*** _#Spinning the Wheel_


*Issue title*  
User Story 11, Spin the Wheel, Step 1

```
As a player of the game,
If I choose to spin the wheel,
The UI will indicate that the wheel is spinning.
The section of the wheel I land on will determine my outcome.

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #8
```

*Issue title* 
User Story 12, Spin the Wheel, Losing a Turn 
User Story 12, ```
As a visitor,
when a valid customer has been selected,
The `Rooms` page will display all the following customer specific information:

- Summary of all past bookings

If there is no valid information for past booking for this customer,
I will be notified that no valid data exists.
```Spin the Wheel, Losing a Turn

```
As a player of the game,
If I land on "Lose Your Turn" when I spin the wheel
Then my turn is over.

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #11
```

*Issue title*  
User Story 13, Spin the Wheel, Bankruptcy

```
As a player of the game,
If I land on "Bankruptcy" when I spin the wheel
Then my "round" score is reset to $0.
My "game" score is unaffected.
My turn is over.

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #11
```

*Issue title*  
User Story 14, Spin the Wheel, in a regular round, landing on money

```
As a player of the game,
If I land on a dollar amount when I spin the wheel
Then I am prompted by the UI to choose a consonant.

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #11
```

*Issue title*  
User Story 15, Spin the Wheel, choosing a valid consonant

```
As a player of the game,
When I choose a consonant,
If that consonant was previously chosen I am prompted to guess again.
If that consonant is a valid letter in the puzzle:

- each instance of that letter is revealed
- my "round" score increases by the money amount on the wheel multiplied
by the number of letters that were just revealed

My turn continues, and I can solve, buy a vowel, or spin the wheel again

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #11
```

*Issue title*  
User Story 16, Spin the Wheel, Choosing an invalid consonant

```
As a player of the game,
When I choose a consonant,
If that consonant is NOT a valid letter in the puzzle
Then my turn is over.

* [ ] done

child of #Spinning the Wheel

child of #Core Application

depends on #15
```

***EPIC: Solving the Puzzle*** _#Solving the Puzzle_


*Issue title*  
User Story 17, Solving the Puzzle, Step 1

```
As a player of the game,
If I choose to solve the puzzle,
The UI will give me an input field where I type my guess
My guess should not have to be CaSe-SeNsItiVe to be correct.

If I do not solve the puzzle correctly, my turn is over.

* [ ] done

child of #Solving the Puzzle

child of #Core Application

depends on #8
```

*Issue title*  
User Story 18, Solving the Puzzle, Step 2

```
As a player of the game,
If I choose to solve the puzzle,
And I solve the puzzle correctly,
The round is over
Any money I've accumulated in this round is added to my "game" score.
Money accumulated by other players in this round is discarded.

* [ ] done

child of #Solving the Puzzle

child of #Core Application

depends on #17
```

*EPIC: Bonus Round*


*Issue title*  
User Story 19, Solving the puzzle ends the round

```
As a developer of the game,
When a player successfully solves the puzzle,
All players see their accumulated "game" scores so far.
The UI prompts the user to start the next round.
If this was the 3rd round, a game winner is declared
And a bonus round begins.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #18
```

*Issue title*  
User Story 20, Picking a Winner

```
As a developer of the game,
When all 3 rounds have been finished,
The player with the highest accumulated "game" score is the winner.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #19
```

*Issue title*  
User Story 21, Bonus Round, Part 1

```
As a player of the game,
If I am declared the winner,
A new bonus round is started where I am the only player who participates.
A new puzzle is chosen that contains at least 6 consonants.
A new "bonus" wheel is generated.
The UI shows the puzzle the same as the start of a regular round.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #20
```

*Issue title*  
User Story 22, Bonus Round, Part 2

```
As the winning player of the game,
When the bonus round begins,
I spin the "bonus" wheel to select my prize.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #21
```

*Issue title*  
User Story 23, Bonus Round, Part 3

```
As the winning player of the game,
When I have spun the "bonus wheel",
I am prompted to choose 1 vowel and 3 consonants.
The consonants cannot repeat, they must all be different.
Correct letter choices are revealed on the UI
No accumulated money is updated.

* [ ] done

depends on #22
```

*Issue title*  
User Story 24, Bonus Round, Part 4

```
As the winning player of the game,
Once the UI reveals any correct letters,
I am prompted to solve the puzzle.
If I guess correctly, the prize is added to my "game" score
And the game is over.
My full accumulated "game" score is shown on the UI.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #23
```

*Issue title*  
User Story 25, Bonus Round, Part 5

```
As the winning player of the game,
When I am prompted to solve the puzzle,
If I guess incorrectly, the puzzle is revealed.
No additional money is added to my "game" score.
The game is over.
My full accumulated "game" score is shown on the UI.

* [ ] done

child of #Bonus Round

child of #Core Application

depends on #23
```
 -->
