# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
The purpose of the game is to have the player guess a randomly generated secret number within a limited number of attempts. The game provides hints after each guess, tracks the player's score, and ends when the player either guesses correctly or runs out of attempts.
- [ ] Detail which bugs you found.
During testing, I found that the hint messages were reversed. When a guess was higher than the secret number, the game incorrectly told the player to guess higher instead of lower. I also found that the attempts counter started at 1 instead of 0, which caused the number of attempts remaining to be inaccurate at the start of a new game.

- [ ] Explain what fixes you applied.
I fixed the hint bug by updating the logic in the check_guess() function so that guesses above the secret number return the hint "Go LOWER!" and guesses below the secret number return "Go HIGHER!". I also fixed the attempts counter by initializing it to 0 instead of 1. In addition, I refactored the core game logic functions into logic_utils.py and added pytest tests to verify that the game logic worked correctly.

## 📸 Demo Walkthrough
1. Start a new game and view the secret number in the Developer Debug Info panel for testing purposes.
2. Enter a guess lower than the secret number. The game returns "Too Low" and displays the hint "Go HIGHER!".
3. Enter a guess higher than the secret number. The game returns "Too High" and displays the hint "Go LOWER!".
4. Continue making guesses until the correct number is entered. The score updates after each guess.
5. Enter the correct number. The game displays a win message, shows the final score, and ends the game.


## 🧪 Test Results

```
===================================================================== test session starts ======================================================================
platform linux -- Python 3.12.1, pytest-9.1.1, pluggy-1.6.0
rootdir: /workspaces/ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.14.0
collected 3 items

tests/test_game_logic.py ...                                                                                                                             [100%]

====================================================================== 3 passed in 0.02s =======================================================================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
