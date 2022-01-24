# Wordle Solver

This simple script solves [the wordle game](https://www.powerlanguage.co.uk/wordle/) by filtering the dictionary and picking the word that maximises the information gained from each word guess. 

The solver is optimal for shallow search (averaging 3.46 words per solve), and guarentees to solve the game within 6 words. 

## Usage

1. Open chrome dev tools (Ctrl + Shift + I) and paste `index.js` into [chrome Content snippets](https://developer.chrome.com/docs/devtools/javascript/snippets/#openmouse).

2. Press (Ctrl + Enter) to run the snippet. 

### How it works

For each round, the solver filters out all the possible moves that can result in the given `Green`, `Yellow`, `Black` combination. It then pickes the word that divides the remaining words (by calculating the array of colours) so that [entropy](https://en.wikipedia.org/wiki/Entropy_(information_theory)) is maximised. 

When using the results dictionary exclusively, the best starting word is `RAISE`. The solver averages 3.600 words per solve, with the maximum being 8 words for `BOXER`.

When using the extended dictionary, **the best starting word is `SOARE`.** The solver averages 3.464 words per solve, with the maximum being 6 words for `WAFER`.

The starting word is cached in the program, making execution extremely fast (faster than the animation takes on the website). 