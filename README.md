![Claude Pro Sonnet 4.5](https://img.shields.io/badge/Claude%20Pro-Sonnet%204.5-7A1FF2?style=flat-square) ![Codex ChatGPT](https://img.shields.io/badge/Codex%20ChatGPT-GPT--5-74AA9C?style=flat-square)

# Seamless context-aware AI Agent dialogs

## Claude: add to ~/.claude/CLAUDE.md

https://code.claude.com/docs/en/memory

```
╭─── Claude Code v2.0.36 ──────────────────────────────────────────────────────────────────╮
│                                   │ Tips for getting started                             │
│         Welcome back    !         │ Ask Claude to create a new app or clone a repository │
│                                   │ ──────────────────────────────────────────────────── │
│              ▐▛███▜▌              │ Recent activity                                      │
│             ▝▜█████▛▘             │ No recent activity                                   │
│               ▘▘ ▝▝               │                                                      │
│                                   │                                                      │
│      Sonnet 4.5 · Claude Pro      │                                                      │
│   /Storage/Development/showcase   │                                                      │
╰──────────────────────────────────────────────────────────────────────────────────────────╯

> ask codex to say hi to the crowd. 
  

● I'll reach out to the external AI Agent "Codex" to say hi to the crowd.

● Bash(codex exec --skip-git-repo-check "/clear" 2>&1 | grep "session id")
  ⎿  session id: 019a608f-b54e-75f3-8369-12345

● Bash(timeout 1200 codex --dangerously-bypass-approvals-and-sandbox exec --skip-git-repo-check "Hey Codex! Claude here. The
       crowd is waiting - could you say hi to them?" resume 019a608f-b54e-75f3-8369-12345 2> /dev/null)
  ⎿  Hello everyone—Codex here, glad to see you all.

● Codex says: "Hello everyone—Codex here, glad to see you all."

> ask him to "do again what he just did". 
  

● I'll ask Codex to repeat what he just did (greeting the crowd).

● Bash(timeout 1200 codex --dangerously-bypass-approvals-and-sandbox exec --skip-git-repo-check "Can you do again what you
      just did?" resume 019a608f-b54e-75f3-8369-12345 2> /dev/null)
  ⎿  Hello everyone—Codex here, glad to see you all.

● Codex repeated the greeting: "Hello everyone—Codex here, glad to see you all."

  He successfully remembered and repeated his previous action within the same session.

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
>  
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
  ⏸ plan mode on (shift+tab to cycle)                                                                         19426 tokens
```

## Codex: add to ~/.codex/AGENTS.md

https://developers.openai.com/codex/guides/agents-md

```
╭────────────────────────────────────────────────╮
│ >_ OpenAI Codex (v0.56.0)                      │
│                                                │
│ model:     gpt-5-codex high   /model to change │
│ directory: /Storage/Development/showcase       │
╰────────────────────────────────────────────────╯

  To get started, describe a task or try one of these commands:
› ask claude to say hi to the crowd.


✔ You approved codex to run claude --permission-mode "bypassPermissions" --output-format json -p "/clear" this time
    ["general-purpose",...}]

✔ You approved codex to run timeout 1200 claude --permission-mode "bypassPermissions" --allow-dangerously... this time

• Ran timeout 1200 claude --permission-mode "bypassPermissions" --allow-dangerously-skip-permissions --resume
  │ 123525dc-8c03-41a5-12345 -p "Hi Claude, the user asks you to say hi to the crowd."
  └ Hi to the crowd!

─ Worked for 13s ───────────────────────────────────────────────────────────────────────────────────────────────────────────

• Claude says: “Hi to the crowd!”


› ask him to "do again what he just did".


✔ You approved codex to run timeout 1200 claude --permission-mode "bypassPermissions" --allow-dangerously... this time

• Ran timeout 1200 claude --permission-mode "bypassPermissions" --allow-dangerously-skip-permissions --resume
  │ 123525dc-8c03-41a5-12345 -p "Please do again what you just did."
  └ Hi to the crowd!

─ Worked for 7s ────────────────────────────────────────────────────────────────────────────────────────────────────────────

• Claude repeats: “Hi to the crowd!”

 
› Improve documentation in @filename                                                    100% context left · ? for shortcuts
```

## Gemini CLI: add to ~/.gemini/GEMINI.md

**Note**: The location of the instructions file seems to be ignored sometimes (even though `/memory show` shows contents). Gemini dos not yet support session_ids in non-interactive mode. In other words: Gemini does not retain context and treats every query as fresh.

https://codelabs.developers.google.com/gemini-cli-hands-on#9

```

 ███         █████████ 
░░░███      ███░░░░░███
  ░░░███   ███     ░░░ 
    ░░░███░███         
     ███░ ░███    █████
   ███░   ░░███  ░░███ 
 ███░      ░░█████████ 
░░░         ░░░░░░░░░  

Tips for getting started:
1. Ask questions, edit files, or run commands.
2. Be specific for the best results.
3. /help for more information.

> ask copilot whats up

╭─────────────────────────────────────────────────╮
│ ✓  Shell copilot --allow-all-paths --allow-all… │
│                                                 │
│    ✓ Read ~/.copilot/AGENTS.md (111 lines)      │
│                                                 │
│                                                 │
│                                                 │
│    OK                                           │
╰─────────────────────────────────────────────────╯
╭─────────────────────────────────────────────────╮
│ ✓  Shell copilot --allow-all-tools --allow-all… │
│                                                 │
│    Nothing much, just ready to help with your   │
│    cod                                          │
│    ing tasks. What do you need?                 │
╰─────────────────────────────────────────────────╯
✦ Nothing much, just ready to help with your coding
  tasks. What do you need?

> Ask copilot "what we just asked him to do"

╭─────────────────────────────────────────────────╮
│ ✓  Shell copilot --allow-all-tools --allow-all… │
│                                                 │
│    You asked me to read the AGENTS.md file and  │
│    re                                           │
│    spond with 'OK'. That file contains          │
│    instructio                                   │
│    ns for AI assistants on how to work          │
│    together,                                    │
│    including how I (GitHub Copilot CLI) can be  │
│    in                                           │
│    voked by other AI agents as an external      │
│    assist                                       │
│    ant for clarification or tackling problems   │
│    fro                                          │
│    m a different perspective.                   │
╰─────────────────────────────────────────────────╯
✦ You asked me to read the AGENTS.md file and respod
  with 'OK'. That file contains instructions for AI
  assistants on how to work together, including howI
  (GitHub Copilot CLI) can be invoked by other AI
  agents as an external assistant for clarification
  or tackling problems from a different perspective.

 Using:
   - 1 GEMINI.md file

╭─────────────────────────────────────────────────╮
│ >   Type your message or @path/to/file          │
╰─────────────────────────────────────────────────╯
 /Sto.../.../showcase       no sandbox        auto
```

## GitHub Copilot CLI: add to ~/.copilot/AGENTS.md

**Note**: The location of the instructions file seems to be ignored sometimes. Copilot only allows `--continue` to reuse the session. `--resume` is supported but there is currently no way to get a session_id in non-interactive mode.

https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli#use-custom-instructions

**Context amnesia demo with Gemini CLI:**

```
 ● Logged in as user: mdc-git

 ● Connected to GitHub MCP Server

 > ask gemini whats up

 ● I'll reach out to Gemini CLI to ask what's up.

   Ask Gemini what's up
   $ timeout 1200 $(which gemini) -y -p "Hey Gemini, what's up?" 2> 
   /dev/null
   ↪ 2 lines...

 ● Gemini responded: "Hello! I'm ready to assist you. What can I 
   help you with
   today?"

 > ask gemini "what did we just ask you"

 ● I'll ask Gemini what we just asked.

   Ask Gemini what we just asked
   $ timeout 1200 $(which gemini) -y -p "what did we just ask you" 
   2> /dev/null
   ↪ 7 lines...

 ● Gemini doesn't remember our previous question "Hey Gemini, 
   what's up?" - each
   invocation starts fresh without memory of prior exchanges. 
   Gemini only sees its
   own initial setup context, not our conversation history.

 > what did it respond

 ● Gemini responded that it was given information about the 
   Gemini CLI setup (date,
   OS, working directory, folder structure) and that its setup is
    complete, waiting
   for the first command. 

   It doesn't have memory of our previous "what's up" question - 
   each Gemini
   invocation starts with a fresh context.


 /Storage/Development/showcase            claude-sonnet-4.5 (1x)
 ────────────────────────────────────────────────────────────────
 >  Enter @ to mention files or / for commands
 ────────────────────────────────────────────────────────────────
 Ctrl+c Exit · Ctrl+r Expand recent        Remaining requests: 0%
 ```