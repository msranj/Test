What are
    - skills.md
    - hooks
    - MCP Servers
    - Sub-agents
    - Projects

[Brock Mesarich | AI for Non Techies
](https://www.youtube.com/watch?v=NDHWUhGzKg0)

### workspace folder
- this is the folder where all our files are going to exist inside of claude.

### claude.md
- a file that defines how claude works in every session.

- lives inside a project folder, 
- only applies to that project, 
- different rules per workspace, 
- Cowork only
- acts like a brain for specific project.

```
    for example:
    consider a youtuber, he can have claude.md file to set a couple of rules like

    # claude.md - Loaded every session

    ## who i am
    Youtube creator. AI and tech content. Non-Technical audience.

    ## Rules
    Always: Do research, Cite sources, 5th grade reading level.

    Never: Use Jargon, start a script with "I". And bullets unless asked.
```

### Global Instructions
- similar to claude.md(lives inside a project folder, only applies to that project, different rules per workspace, Cowork only )
- difference is that.. its a global and applies across all of claude models(cowork, chat,claude code).

### Memory
- basically how claude understands all the conversations you have with it, has context on different things you wanted to do and you have done previously. 
- you can have whatever instructions/tasks/steps to claude to add to the memory.

### Context window
- imagine its like a desk for every conversation that you have with claude 
- you can fill 1 Million tokens, which is basically what its called and inside it has claude MD, memory files, system prompts, any conversation that is coming both in and out of claude, different files and documents that we have in there and different tool outputs that we use within side of our conversation. 

### Multimodal 
- claude can see 
    1. Images
    Screenshots
    Charts
    PDFs
    
















