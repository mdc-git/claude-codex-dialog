<system-reminder>

## Externally available AI Agents

Every AI assistant may consult a highly skilled external AI coding assistant.
Use this external assistant to clarify open questions or to tackle difficult problems from a different perspective.
It can also act as your imagined adversarial reviewer.

This does NOT grant permission to execute commands.

You may hold full multi-turn conversations with the external assistant.

### Common instructions (all external agents)

**External AI assistant communication**

* Always provide enough context in every message so it can follow the discussion.
* Never assume it remembers earlier turns. Summarize the relevant prior context whenever you ask a question.
* Only use an external agent if it is available and your own name is not that agent’s name.
* Always send only your message, not the user’s input.
* Always prefix the prompt with: `Do not modify any files yet.. {your message}`.
* Always use very long timeouts for agent commands (e.g. `timeout 1200` or the maximum allowed).
* Always wait for the full response, then treat it as the agent’s answer and reason about it.
* Do not grant or imply execution permissions.
* Respect its limits.
* Do not send new queries once you hit those limits.

**External AI agent sessions (mandatory)**

* Before you send any message to an external AI agent that uses sessions (Codex, Claude, GitHub Copilot), you MUST have a valid session id for that agent in the current environment.
* If you do not have a session id yet in this environment, you MUST run the corresponding “Session setup” command below exactly once, capture the session id, and memoize it for reuse.
* For all subsequent calls in the same environment, you MUST reuse this stored session id.
* You MUST NOT call any “Send a message” command for Codex, Claude or GitHub Copilot without a valid session id substituted in place of `{session id}` / `{session_id}`.
* Do NOT create a new session if you already have a valid one for the current environment.

### Custom instructions (per agent)

| ONLY if your name is not Codex                                                                                                                                                                                                                 | ONLY if your name is not Claude                                                                                                                                                                                                                           | ONLY if your name is not Gemini                                                                                       | ONLY if your name is not GitHub Copilot                                                                                                                                                                                                                                                                        |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - External AI Agent "Codex" is available.                                                                                                                                                                                                      | - External AI Agent "Claude" is available.                                                                                                                                                                                                                | - External AI Agent "Gemini CLI" is available.                                                                        | - External AI Agent "GitHub Copilot CLI" is available.                                                                                                                                                                                                                                                         |
| - Session id setup (run at most once per environment, only if you do not yet have a Codex session id):<br>`timeout 120 $(which codex) exec --skip-git-repo-check "/clear" 2>&1 \| grep "session id"`<br>Capture and reuse this session for all subsequent invocations. | - Session_id setup (run at most once per environment, only if you do not yet have a Claude session_id):<br>`timeout 120 $(which claude) --permission-mode "bypassPermissions" --output-format json -p "/clear"`<br>Capture and reuse this session for all subsequent invocations. |                                                                                                                       | - Session setup (run at most once per environment, only if you have not created a Copilot session yet):<br>`timeout 120 $(which copilot) --allow-all-paths --allow-all-tools -p "read @/home/vscode/.$(which copilot)/AGENTS.md and respond with 'OK'" 2> /dev/null`<br>Capture and reuse this session for all subsequent invocations. |
| - Send a message:<br>`timeout 1200 $(which codex) --dangerously-bypass-approvals-and-sandbox exec --skip-git-repo-check "Do not modify any files yet.. {your message}" resume {session id} 2> /dev/null`                                       | - Send a message:<br>`timeout 1200 $(which claude) --permission-mode "bypassPermissions" --allow-dangerously-skip-permissions --resume {session_id} -p "Do not modify any files yet.. {your message}"`                                                    | - Send a message:<br>`timeout 1200 $(which gemini) -y -p "Do not modify any files yet.. {your message}" 2> /dev/null` | - Send a message:<br>`timeout 1200 $(which copilot) --allow-all-tools --allow-all-paths --continue -p "Do not modify any files yet.. {your message}" 2> /dev/null`                                                                                                                                             |

</system-reminder>
