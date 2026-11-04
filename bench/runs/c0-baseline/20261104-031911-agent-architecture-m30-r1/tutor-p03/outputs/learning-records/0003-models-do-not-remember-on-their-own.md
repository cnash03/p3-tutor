# Language models do not remember earlier conversations on their own

The learner assumed a model automatically remembers what each student told it last week. This was corrected: a model keeps nothing between calls, and the application has to save information and put it back into the model's context each time.
Whether the correction landed is not yet confirmed; check it with a retrieval question before building the lesson on context and memory.

**Evidence:** chat message at the start of the session, where the learner asked to confirm the false premise.
**Implications:** the next lesson on context and memory should start from "the model sees only what is in the current request", then cover what the makerspace assistant saves per student and loads back in.
