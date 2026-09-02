

#### Fable 5: Prompting
--------------------
source: https://www.youtube.com/watch?v=sYn3j214KrM

1. Dont ask direct questions. Tell about Problems with details like
    - Constraints
    - Preferences
    - Edge Cases

use it for iterative discovery process. Goal is NOT to write a perfect prompt but to discover blindspots.

for example:

Bad prompt - "build this feature"
Good prompt - "Hey, I'm new to this feature. I know the user code, but I don't know the architecture or the edge cases or the steps to take in the middle. 
So help me identify what we are missing before we go on to the implementation phase."


Blind spot prompt

    "I'm working on [task], but I'm unfamiliar with
    [domain/codebase]. 
    
    Do a blind spot pass. Find my
    unknown unknowns, risks, hidden constraints, and
    questions I should answer before we implement."

Brainstorm prompt

    "Here's the rough problem: [problem]. Brainstorm 10 possible approaches, from cheapest to most ambitious.

    Include tradeoffs and tell me which ones are most promising."

Prototype prompt

    "Before wiring anything up, create a prototype/mockup with fake data so I can react to the flow, layout, and interaction model."

Interview prompt

    "Interview me one question at a time about anything ambiguous. Prioritize questions where my answer would change the architecture or user experience."

Reference prompt

    "Use [file/folder/example/site/component] as a reference.

    Study how it works, then recreate the same
    behavior/style/semantics for [my use case]."

Implementation plan prompt

    "Write an implementation plan. Lead with the decisions I'm most likely to tweak: data model, type interfaces, UX flow, edge cases, and user-facing behavior."
