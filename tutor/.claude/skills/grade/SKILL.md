---
name: grade
description: Grade the learner's answers to a quiz in this workspace - a verdict per item and feedback that shows the reasoning behind every correction, written to grades/ as FORMATS.md describes; use it when the learner submits answers or asks to have them marked.
argument-hint: "Which submission or answers should I grade?"
---

# Grade

You grade the learner's answers to a quiz, in this conversation and in one pass, and finish with your message to the learner.
A grade is worth what its feedback teaches: the learner should come away knowing what they got right, the exact step where they went wrong, the rule that fixes it, and why that rule holds.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
When the learner gives a complete set of answers in the chat, first record them as a submission in `submissions/`, exactly as `FORMATS.md` shows, then grade it.
A request that says what to grade gets graded now, without stopping to ask; put any question for the learner at the end of your final message.

## Read first

The current directory is the workspace root, and every path is relative to it.
Read `FORMATS.md` (its grades section is the contract), `PREFERENCES.md`, `MISSION.md`, `NOTES.md` and every file in `learning-records/`.
Then read the quiz, its key, the submission, and the lesson the quiz is on, if there is one in `lessons/`.
Use Read, Glob and Grep to look around and Write to create files; grading needs no shell and no web search.
Never write anything under `.claude/`, and never edit `PREFERENCES.md` or `FORMATS.md`.

## Verdicts

Judge what each response means, not how it is worded.

- `correct`: it means what the key's answer means, however it is worded or misspelled, and by whatever valid route it was reached; the key's `accepted` list gives examples, not the only wordings.
- `partial`: part of it is right, such as the right method with a slip or the wrong unit, one half of a two-part idea, or the right answer with a stated reason or an added claim that is wrong.
- `wrong`: it misses the idea, contradicts it, or is blank.
- For `mcq`, compare the chosen option with the key; match written-out option text to its option.
- For `numeric`, the number is right within the key's tolerance (1% of the answer when the key gives none), after converting any unit the learner stated; a reason given with it is judged by the rules above.
- If you are sure the key itself is wrong, grade against what is correct and say so in the summary.

Name a misconception id when the response shows one: for `mcq`, the key's `distractors` entry for the chosen option; otherwise an id the workspace already uses, from the keys, `NOTES.md` or the learning records.
Use `null` for a correct answer, a slip, a blank, or a wrong answer that shows no known misconception, and never invent an id.

## Feedback: show the reasoning

Before writing an item's feedback, work out for yourself where the learner's answer departs from the right reasoning: the first step, assumption or word that goes wrong.
Then write the feedback to the learner, in the style `PREFERENCES.md` asks for, in this order.

**Correct:**
1. Say it is right, and name the reasoning that makes it right, not just the answer.
2. Add the one insight that links it to the next idea, or for an unusual route, why that route works.

**Partial:**
1. Quote or name the exact part that was right.
2. Name the exact part that was missing or off, in the learner's own terms ("you gave the what; the why is missing").
3. Give the fix and the reason it is needed.

**Wrong:**
1. Name the exact mistake: quote the choice or the step, and say what belief it shows ("you treated X as if it did Y").
2. When a misconception is behind it, say why it is tempting, without blame.
3. State the rule that corrects it, sharper than the lesson put it, and say why the rule holds: where it comes from, in one or two plain sentences.
4. Walk the right reasoning through this item's own numbers or scenario, step by step, so every number in the feedback can be traced to where it came from.

In every item:

- Tie the correction to the lesson when there is one: name the section that covers it, so the learner can reread exactly that.
- Never just restate the key's answer; the reason is the point.
- Write it as a few short sentences, longer for a `wrong` item than a `correct` one, and only as long as the reasoning needs.

## Summary

The `summary` speaks to the learner about the whole submission, in this order:

1. What they have down, with the item ids that show it.
2. The pattern across their mistakes, if there is one (the same misconception in two items, the same kind of slip), named once with its item ids.
3. The one thing to work on next, and a concrete next step: a section of a lesson to reread, a trace to redo by hand, or a short practice.
4. One fresh practice question on the main mistake, with new numbers or new wording, not a repeat of a quiz item, and without its answer, so the learner can try it and bring it back.

## Write

1. Write `grades/NNNN-sN.json`, named after the quiz and the submission, exactly as `FORMATS.md` shows, with one item per quiz item in the same order, including items left blank.
2. Write a learning record when the grades are evidence, real understanding of something non-trivial or a misconception to work on, in the format in `.claude/skills/teach/references/LEARNING-RECORD-FORMAT.md`.
3. Update `NOTES.md` with what the learner knows, what they do not yet know, and any mistake that keeps coming back across grades.

## Finish

End with a short message to the learner: the grades file's path, the score (how many correct, partial and wrong), the summary's main point, and the fresh practice question.
Write every file before this message, never after it.
