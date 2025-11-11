## Seamless context-aware AI Agent dialogs

![Claude Pro Sonnet 4.5](https://img.shields.io/badge/Claude%20Pro-Sonnet%204.5-7A1FF2?style=flat-square) ![Codex ChatGPT](https://img.shields.io/badge/Codex%20ChatGPT-GPT--5-74AA9C?style=flat-square)

## Claude: add to CLAUDE.md

https://code.claude.com/docs/en/memory

## Codex: add to AGENTS.md

https://developers.openai.com/codex/guides/agents-md


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
