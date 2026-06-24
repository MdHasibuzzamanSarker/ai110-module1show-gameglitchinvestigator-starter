# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it? 
  -Ans: It looks like an norrmal guess the number game app. Than I entered several inputs including 0 and negative numbers. Although it gives an error , its inconsistant. Two clear problems stood out right away: the difficulty settings did not feel balanced, and the input handling was not strong enough to prevent bad guesses from breaking the flow.

- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
  - Ans: The Normal and Hard mode ranges wrong. Its easier to guess the number in Hard mode compared to the Normal mode which has range from 1 to 100.  Also it rounds down the integer in the scoreboard when I entered a decimal number . I also noticed that the scoring and attempt logic were not behaving as expected during a win, which made the game feel unfair.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|selected Hard difficulty mode| should give me a bigger range than normal ; since larger the range of number , its harder to guess | Gave me a smaller ranger than Normal|No Error |
| Entered 30.99 | Either the decimal should have been rejected or produce an Error or treated as an invalid input| Decimal has been rounded down to the nearest Integer number | No Error |
| Win on the First Guess| should have given the full 100 Scores | Only 90 points have been Awarded  | No Errors|

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
 Ans: I used Copilot for this project. I used Copilot as a teammate while working through this project. 
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
Ans: One suggestion that was helpful was the idea to focus on input validation , so invalid guesses would be handled safely. I verified that suggestion by testing several invalid inputs and confirming that the game behaved more predictably after the change. 
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
- Ans: One suggestion that was misleading was to treat the issue as only a small UI or button problem when the real cause was the way state was being preserved across reruns. I confirmed that by comparing the behavior of the app before and after moving the important values into session state, which made the game behave correctly.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
Ans: After editing the codes, I restarted the whole program, and  checked for the bug. It was performing the way it should be.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  ANS: I tested the game manually by trying different guesses, difficulty levels, and edge cases, and I also ran pytest to check the core logic. Those checks showed me that some issues were fixed, while others still needed refinement in the way state and input were handled.

- Did AI help you design or understand any tests? How?
ANS: Yea, it gave me a range of different types of inputs and their expected output. I decided a bug was genuinely fixed when I could consistently reproduce the expected behavior manually in the Streamlit app and when my automated tests passed. I used AI to help me understand the TypeError exception block in the original check_guess logic, which helped me realize why my manual tests were acting so random on every other guess before I completely rewrote that section. 
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- Ans: I learned that Streamlit reruns the script every time the user interacts with the app, so ordinary variables can get reset unexpectedly. Session state is what keeps important values, such as the secret number, score, and attempt count, stable across those reruns.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
- Ans: One habit I want to keep is testing one issue at a time and writing down the exact steps to reproduce a bug before changing code. I also want to be more careful about checking AI suggestions against the actual behavior of the app instead of accepting them too quickly. This project changed the way I think about AI-generated code because it showed me that AI can be useful for finding likely causes, but I still need to verify the result myself.