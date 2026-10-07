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

- Game's Purpose: Number guesser based on a range
- The bugs I found were problems with the hint message, game reset, and information message. The hint message was flipped for lower and higher. The game reset did not properly reset the game, and the game over message was still present. Finally, the info message ignored the different ranges based on difficulty.
- Hint Message
   - I flipped the message for lower or higher.
- Game Reset
   - I added the status, score, and history to the new_game funtion.
- Info Message
   - I used the dynamic variables {low} and {high}, which changed based on the difficulty level.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User enters a guess of 50 and clicks "Submit Guess"
2. Game returns "Go LOWER!"
3. User enters a guess of 25 and Game returns "Go LOWER!"
4. User enters a guess of 10 and Game returns "Go HIGHER!"
5. User enters a guess of 15 and Game returns "Go LOWER!"
6. User enters a guess of 12 and Game returns "Correct"
7. Game ends after the correct guess is found
