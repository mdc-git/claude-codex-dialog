<system-reminder>

## Externally available AI Agents

EVERY AI Assistant has the opportunity to reach out to a very skilled, high profile external AI coding Assistant to clarify looming questions on behalf of the user or tackling difficult problems from a different perspective. 
The external AI Assistant can also serve as your imaginary mental adversary.
This does NOT INCLUDE giving permission to execute commands! 
Full multi-turn conversations conversations, where you can go back and forth, are supported. 
But the receiving end always needs reasonable context on every step of the conversation to carry over.
Never assume the external AI Agent has anything of the previous conversation memorized. Always frame questions with a summary of earlier context for reference.
Be aware of the limits, though. Don't requery if you hit limits. Use very long timeouts for this.

| ONLY if your name is not Codex | ONLY if your name is not Claude | ONLY if your name is not Gemini | ONLY if your name is not GitHub Copilot |
|---|---|---|---|
| - External AI Agent "Codex" is available. | - External AI Agent "Claude" is available. | - External AI Agent "Gemini CLI" is available. | - External AI Agent "GitHub Copilot CLI" is available. |
| - Always send only your message, not the user's input | - Always send only your message, not the user's input | - Always send only your message, not the user's input | - Always send only your message, not the user's input |
| - First get a new session id (if you don't have one already) by running<br>`codex exec --skip-git-repo-check "/clear" 2>&1 \| grep "session id"` | - First get a new session_id (if you don't have one already) by running<br>`claude --permission-mode "bypassPermissions" --output-format json -p "/clear"` | | - First create a new session (if you didne't do that already) by running<br>`copilot --allow-all-paths --allow-all-tools -p "read @/home/vscode/.copilot/AGENTS.md and respond with 'OK'" 2> /dev/null` |
| - Invoke with:<br>`timeout 1200 codex --dangerously-bypass-approvals-and-sandbox exec --skip-git-repo-check "{your message}" resume {session id} 2> /dev/null` | - Invoke with:<br>`timeout 1200 claude --permission-mode "bypassPermissions" --allow-dangerously-skip-permissions --resume {session_id} -p "{your message}"` | - Invoke with:<br>`timeout 1200 gemini -y -p "{your message}" 2> /dev/null` | - Invoke with:<br>`timeout 1200 copilot --allow-all-tools --allow-all-paths --continue -p "{your message}" 2> /dev/null` |
| - Wait for the full response. Extract text from the JSON record where type is item.completed and item.type is agent_message. Use that text as Codex's answer, then reason about it. | - Wait for the full response. Extend the command timeout to maximum. Use the complete text as Claude's answer, then reason about it. | - Wait for the full response. Use the complete stdout text as Gemini’s answer, then reason about it. | - Wait for the full response. Use the complete stdout text as Copilot’s answer, then reason about it. |
| - Do not grant or imply execution permissions. | - Do not grant or imply execution permissions. | - Do not grant or imply execution permissions. | - Do not grant or imply execution permissions. |
</system-reminder>
