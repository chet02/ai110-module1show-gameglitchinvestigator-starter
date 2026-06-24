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
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
