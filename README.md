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

- [x] Describe the game's purpose: The game lets the player guess a secret number inside a chosen difficulty range. The goal is to guess correctly before running out of attempts.
- [x] Detail which bugs you found: The secret number changed each time because the app was not saving game state between button clicks. The hint messages were also giving the wrong direction for some guesses.
- [x] Explain what fixes you applied: I stored the game state in Streamlit session state, fixed the hint logic, and moved the game rules into logic_utils.py.

## 📸 Demo Walkthrough

1. The player opens the app and chooses a difficulty level.
2. The game shows the guess range and the number of attempts left.
3. The player enters a guess and clicks Submit.
4. The app gives a hint and updates the score based on the result.
5. The player keeps guessing until they win or run out of attempts.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
pytest tests/
# Run this command to verify the game logic tests.
```

## 🚀 Stretch Features

- [x] The app now has clearer hints, score updates, and a simple new-game flow.
