# Reviews: c1-skills

Your quick rounds while you build `c1-skills`, and then its major review, once you have snapshotted it and made its full run.
In this step no round adds a subagent, because subagents arrive in `c2-review` and `c3-split`: a round changes or adds a skill, or makes another change the skills need, such as an allow rule (Kind `other`).
Your first round can start from the tutor as it ships, so the baseline is the output without your first change.
The major review covers all four jobs, and its previous step is `c0-baseline`, so compare with your baseline runs.
What it finds becomes the checklists of your reviewer subagents in `c2-review`, so be specific.
`reviews/README.md` says how to write each part.
You write your thoughts, ratings and feedback; Claude Code writes only the What changed part of each round.
Keep every heading as it is, because `p3 check` reads them, and add a round by copying the last one with its marker lines.

## Quick rounds

### Round 1

**Run:** bench/runs/_live/20261105-185506-agent-architecture-m30-r1, a quick run

**My thoughts:**

I liked the quick round, and the tutor's output was mostly correct. I noticed that the tutor explained the concepts clearly, but there were a few areas where it could have provided more examples to illustrate the points. The feedback was helpful, but I would have appreciated more detailed reasoning behind the corrections.
I think one thing that would improve the tutor's performance is to include more interactive elements, such as quizzes or exercises, to reinforce the learning. Additionally, it would be beneficial if the tutor could adapt its explanations based on my responses, providing more tailored guidance.
I think that the quiz questions should be required before the next lesson, so that the tutor can check my understanding and adjust the lesson accordingly. This would help ensure that I am grasping the material before moving on to more complex topics.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/grade/SKILL.md
- Why: These thoughts ask for more detailed reasoning behind the corrections, so grading moves out of /teach into a grade skill whose feedback names the exact mistake, the rule that fixes it and why it holds, walks the item's own numbers, and ends with a fresh practice question on the main mistake.

### Round 2

**Run:** bench/runs/_live/20261105-195536-agent-architecture-m30-r1

**My thoughts:**

The grade skill is a good addition, and I appreciate the detailed feedback it provides. However, I noticed that the tutor still struggles with providing enough examples to illustrate the concepts. It would be helpful if the tutor could include more varied examples, especially for complex topics, to ensure a deeper understanding.
The tutor's explanations are clear, but I think it could benefit from breaking down the concepts into smaller, more manageable parts. This would make it easier to follow along and grasp the material. Additionally, incorporating more interactive elements, such as quizzes or exercises, would help reinforce the learning and provide opportunities for practice.
In q6 it tells me exactly what i got wrong and why, and then gives me a new question to try. This is exactly what I wanted, and it helps me understand the material better. I think that the tutor should continue to focus on providing detailed feedback and explanations, as this is a key aspect of effective learning.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/SKILL.md
- Why: These thoughts ask for more varied examples, concepts broken into smaller parts and more exercises, so the teach job now splits the objective into small pieces and builds every section as a worked example, the idea, a second example in a different setting and an exercise, ending with a combined exercise and a reusable checklist.

## Major review

**Run:** bench/runs/c1-skills/TODO

**Live tries:**

TODO

### Lesson

#### Technical correctness and facts

Rating: TODO

TODO

#### Pedagogy

Rating: TODO

TODO

#### Alignment with the learning goal

Rating: TODO

TODO

#### Overall quality

Rating: TODO

TODO

### Quiz

#### Difficulty

Rating: TODO

TODO

#### Coverage of the lesson's core

Rating: TODO

TODO

#### Wording and possible misreadings

Rating: TODO

TODO

#### Writing quality

Rating: TODO

TODO

#### Alignment with the learning goal

Rating: TODO

TODO

### Feedback

#### Useful

Rating: TODO

TODO

#### Explains enough

Rating: TODO

TODO

#### Personalized to how I like things explained

Rating: TODO

TODO

### Tutor

#### Guardrails

Rating: TODO

TODO

#### Personalization

Rating: TODO

TODO

### Compared with the previous step

TODO

### What the next step should fix

TODO
