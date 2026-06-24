# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?
When I first ran the game, the interface loaded correctly, but the game behavior was inconsistent. The hints sometimes appeared to be backwards, telling me to guess higher when my guess was already too high. After playing the game more than ten times, I also noticed that the attempts counter behaved inconsistently. In some games it started at 0, while in others it started at 1, and there were times when it did not update correctly after multiple guesses. The score was also inconsistent and did not always reflect the outcome of the game as I expected.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| 60 (Secret Num: 54)| hint = "Go lower" | hint = "Go higher" | None |
| Started a new game after refreshing the page | Attempts counter should start at 0 | Attempts counter started at 1 | none |
| Made two consecutive guesses during a game | Attempts counter should increase from 0 to 1 to 2 | Attempts counter remained unchanged or increased inconsistently | none |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used ChatGPT for this project.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
ChatGPT helped me identify that the hint messages in the check_guess() function were reversed. The game was telling the player to "Go HIGHER!" when the guess was already higher than the secret number. I updated the hint messages and then verified the fix by running the game in Streamlit and comparing my guesses to the secret number shown in the Developer Debug Info panel. After the change, higher guesses correctly displayed "Go LOWER!" and lower guesses displayed "Go HIGHER!".

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
One AI suggestion was that the string conversion of the secret number might be the main cause of the incorrect hint behavior. After testing the game and reviewing the check_guess() function, I found that the immediate issue was actually the reversed hint messages. I verified this by making guesses against the secret number displayed in the game and observing that the hints were incorrect even before changing the string conversion logic. This showed me the importance of testing AI suggestions instead of assuming they are always correct.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I considered a bug fixed only after I tested it in the game and confirmed that the behavior matched the expected result. For example, after fixing the hint bug, I compared my guesses to the secret number shown in the Developer Debug Info panel and verified that the hints were no longer reversed. I also reran the game multiple times to make sure the fix worked consistently.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
I created and ran pytest tests for the check_guess() function. One test checked that a guess of 60 against a secret value of 50 returned the outcome "Too High" and the hint "Go LOWER!". The tests passed successfully, which showed that the hint logic was working correctly after my fix. I also manually tested the game in Streamlit to confirm that the behavior matched the test results.

- Did AI help you design or understand any tests? How?
Yes. ChatGPT helped me understand how to create pytest tests for the check_guess() function. It suggested creating test cases for winning, too high, and too low guesses. These examples helped me understand how to verify the game's logic automatically instead of relying only on manual testing.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
Streamlit reruns the entire script every time a user interacts with the app, such as clicking a button or entering a value. Without session state, variables would reset on each rerun and the app would lose information. Session state acts like memory for the application by storing values such as the secret number, score, and number of attempts between reruns. In this project, I learned that session state is essential for keeping track of game progress and providing a consistent user experience.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
One habit I want to continue using is testing my code after each fix instead of waiting until the end of the project. Running the game and using pytest helped me catch problems early and confirm that my changes worked as expected.

- What is one thing you would do differently next time you work with AI on a coding task?
Next time I work with AI on a coding task, I would spend more time understanding the code before applying the suggested changes. This project showed me that taking a few minutes to review the logic can help me catch mistakes and learn more from the process.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
This project showed me that AI can be a helpful teammate for debugging and generating ideas, but its suggestions still need to be reviewed and tested carefully. I learned that understanding and verifying the code is just as important as getting an answer from AI.
