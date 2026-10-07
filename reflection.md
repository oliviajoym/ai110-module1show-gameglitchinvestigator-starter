# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?
  There are 3 issues that I noticed. 
  - The hint is not correct
  - The game doesn't start over properly
  - The game information message does not adjust for difficulty

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|  guess of 60 | Hint: Too Low (answer was 64) | Hint: Too High | None |
| guess of -9 | "Not in range" or an error because number is not in range | acts like it's a valid response | None |
| New Game clicked | text cleared and attempts reset | text stays (either "You already won. Start a new game to play again." or "Out of attempts! The secret was 9. Score: -35") | None |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
    - I used Claude for this project
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
    - One suggestion that Claude gave was to change the check_guess function. It was funny because at first I thought of changing it a different way. However, the AI suggestion was more effiecent and streamlined.
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.
    - One suggestion was on decimal truncation. Claude explained that any decimal given is truncated to an integer. I feel like that is not need for this since the final secret is an integer anyways.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
    - I decided based on the tests run and how it ran on the user interface side with the Streamlit.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
    - I ran one test on the check_guess function that was moved to logic. I checked it manually on through the game and in test_game_logic.py. 
- Did AI help you design or understand any tests? How?
    - AI helped when I was getting an AssertionError. The result was looking for a string while the function was returning a tuple. The solution was just to pull the first element in the tuple. After that fix, the test ran smoothly.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
  - It's similar to a webpage. Each session is a local run of a webpage that can be changed based on the session variables and environment.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
  - While I did used AI to assist with my project, I did not connect it to my VSCode. I need to set that up so that Claude can write directly into my projects when assistance is needed.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
  - I think of the code as more of a tool now. It is a way of checking if I am on the right path through the suggestions it gives, kind of like confirming that I am heading in the right logical steps.