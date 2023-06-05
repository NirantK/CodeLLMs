# CodeLLMs
Everything I know about LLMs for CodeGen


https://arxiv.org/pdf/2305.12050.pdf CodeCompose: A Large-Scale Industrial Deployment of AI-assisted Code Authoring

- CodeOps has 3 recurring patterns
    - Retrieval
        - Files, classes, lines? 
    - Edit
        - See examples I had in mind
    - Verify
        - CI/CD
        - Pass the stacktrace back and complete the loop
- Examples Tasks I had in mind
    - In a FastAPI app, replace a blocking call in a 2-3 file app with a request id response and a new endpoint to poll, use BackgroundTasks or something else as a queue
    - Change a Python function from sync to async and await on it in a different file
    - Rename variable
    - Refactor a script into functions and classes
- Naming the building blocks
    - In-filling
        - Supported by Incoder, StarCoder, can hack GPT4 too
    - Fresh Generate
        - Supported by Incoder, StarCoder, GPT4 
    - Retrieval
        - Code Embedding
            - Maybe something like Replit Code's 1.3b model, finetuned for a specific code? 
        - LLM
            - Pass the codebase structure e.g. files, classes in prefix, ask the LLM  —  what will change instead of asking it to change? 
                - https://chat.openai.com/share/b21ac3d9-cff1-41b1-b040-a0b7e2d65ee3
    - Code Markers
        - Lines and Function prototype
            - https://chat.openai.com/share/b21ac3d9-cff1-41b1-b040-a0b7e2d65ee3
        - Syntax Tree
            - BloopAI uses this with Code Embedding
            - Works well with small classes, and functions in Python, but gives up with object calls
        - Generated diff???
- Ideas that I think we should dive on
    - Using Developer Edits/git commit diffs
        - No code, but DIDACT claims to do this
            - https://ai.googleblog.com/2023/05/large-sequence-models-for-software.html 
            - GPT4 can definitely take Git diff commit and return Git commit messages — indicating some level of code understanding
        - Works with StarCoder with prompting tricks
    - AutoPR
    - BloopAI
