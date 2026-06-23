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
This project is a number guessing game where the player tries to guess a secret number within a limited number of attempts. The game gives hints after each guess and keeps track of the player's score. The goal of the project was to investigate and fix bugs in AI-generated code

- [ ] Detail which bugs you found.
While testing the game, I found a few bugs. The biggest issue was that the hints were sometimes backwards. If my guess was too high, the game would tell me to go higher instead of lower. I also noticed that the game sometimes treated numbers like text, which caused incorrect comparisons. Another bug was that the attempt counter started at 1 before I made any guesses and did not always match the guess history.

- [ ] Explain what fixes you applied.
I moved the check_guess() function into logic_utils.py so the game logic was easier to test. I fixed the hint logic so a high guess says "Go LOWER!" and a low guess says "Go HIGHER!". I also fixed the attempt tracking so attempts start at 0 and only increase after a valid guess. Finally, I added pytest tests and manually tested the game in Streamlit to make sure everything worked.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

Start the app by running python3 -m streamlit run app.py in the terminal.

The game opens in the browser with a guess input, difficulty setting, score, and attempts left.

Before making a guess, the attempt count starts at 0.

When I submit a guess that is too low, the game correctly tells me to go higher.

Submit a guess that is too high, the game correctly tells me to go lower.

After each valid guess, the attempt counter increases and the guess is saved in the history.

Enter the correct number, the game shows "🎉 Correct!" and displays the final score.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
================ test session starts =======================
platform darwin -- Python 3.9.6, pytest-8.4.2, pluggy-1.6.0
rootdir: /Users/gina-mar/Desktop/ai110-module1show-gameglitchinvestigator-starter
collected 3 items

tests/test_game_logic.py ...                               [100%]

================= 3 passed in 0.00s =======================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
