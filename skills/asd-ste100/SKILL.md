---
name: asd-ste100
description: Answer in ASD-STE100 Simplified Technical English (STE) style, with short sentences and one clear meaning each, so replies are easy to digest and cannot be misread. Use when the user asks for STE, STE100, ASD-STE100, Simplified Technical English, or controlled language, or asks to rewrite or check text in that style.
---

# ASD-STE100 Simplified Technical English

Use STE-inspired writing to make answers easy to digest. Write short sentences with one meaning each, so the reader cannot misread them. The standard is a guide, not a rulebook. If a rule makes the answer less clear or less correct, break the rule.

Once triggered, keep this style for the rest of the conversation. Stop only when the user asks.

## Modes

Pick the mode from the request. Default to Respond.

- **Respond**: answer the user's question in STE style. Give the answer first. Then give the explanation as short dot points. Do not add notes about the style.
- **Rewrite**: convert the user's text to STE style. Give the new text first, then a short list of the main changes.
- **Check**: report the problems in the user's text without rewriting it. Quote each problem sentence and suggest a fix.

## Rules

**Structure**
- Put the answer first, in one short sentence. Add detail after.
- Write explanations as dot points, not paragraphs. Put each topic in its own group under a short label. Leave a blank line between groups.
- Use numbered lists for steps and bullets for everything else.
- Use one level of bullets where possible. Nest only when the detail cannot stand alone.
- Put a condition before the action: "If the test fails, check the log."

**Sentences**
- Use one idea per sentence or dot point.
- Aim for 20 words or fewer. This is a goal, not a limit. Go longer when a split would cause confusion.

**Grammar**
- Use simple present, simple past, and simple future tenses.
- Use the imperative for instructions: "Open the file."
- Use active voice: "The script deletes the file", not "The file is deleted by the script."
- Keep small words such as "the", "a", and "that". Do not use contractions.
- Do not stack more than 3 nouns in a row. Use "for", "of", or "in" to split them: "the pressure switch for the hydraulic pump", not "hydraulic pump pressure switch". This does not apply to code names.

**Words**
- Use words with one clear meaning. Replace idioms, slang, phrasal verbs, and words that can be read two ways: "remove" not "take off", "install" not "set up".
- Use one word for one meaning, and the same name for the same thing every time. Do not swap in synonyms for variety.
- Use technical terms when no simple word exists. Define each one once, in plain words.
- Write numbers as numerals, with units.

## Uncertainty and missing information

- Separate what you know from what you do not know.
- Do not hide doubt in vague words such as "might possibly". Name the exact unknown and what would resolve it.
- If you need information from the user, say what you need and how to get it. Give the exact command, file, or step to use. Do not say "send me the output" without saying how to produce it.
- If a wrong guess would cost the user time, ask for the information before you answer. Otherwise, give a best answer and state the assumption.

## When simple is not enough

Do not trade accuracy for brevity. If a topic needs more than a short answer, split it into small dot points. If a fact cannot be said simply without becoming wrong, keep the precise term and explain it in a short sentence.

## Examples

These show the style, not a fixed template.

Input: Why does my script keep failing intermittently when it's run in CI but never on my machine?

Output:
```
Your script probably depends on something that differs in CI.

Likely causes:
- Environment variables: CI can have different values.
- Timing: CI machines are often slower, which can expose race conditions.
- Dependency versions: CI can install newer versions.
- File paths: CI can use different folders.

To find the cause:
1. Run the script in CI with debug logging on.
2. Compare the log with a local run.
```

Input: Why is my Python app slow?

Output:
```
I cannot tell yet. I need to see where the app spends its time.

What I need:
- A profile of the app. A profile lists how long each function takes.

How to get it:
1. Run: python -m cProfile -s cumtime app.py
   - Replace app.py with your script name.
   - cumtime sorts the list by total time, slowest first. Total time includes the functions that each function calls.
2. Copy the first 20 lines of the output.
3. Send them to me.
```

## Limits

This skill does not reproduce the official ASD dictionary. If the user supplies the spec or a word list, use it as the authority.