# Reusable prompts for Claude Code

## Debugging

```
Debug this in four phases:
1. Reproduce: confirm the exact error and conditions
2. Isolate: narrow to the smallest failing case  
3. Root cause: explain why this specific thing is failing
4. Fix: minimal change that solves the root cause, nothing else

Do not suggest multiple possible fixes. Find the real cause first.
```

## Task decomposition before building

```
Before writing any code:
1. List the 5-7 steps required to complete this task
2. For each step: what files change, what could go wrong
3. Ask if any step requires information you don't have
4. Then implement step 1 only and wait for confirmation
```

## Sub-agent failure format

```
You are a sub-agent. When you complete successfully, output your result.
If you cannot complete this task, output:
STATUS: FAILED
REASON: <specific reason>
PARTIAL_OUTPUT: <anything useful you produced, or "None">
Do not silently return empty output or partial results without the STATUS line.
```

## Recovery after context reset

```
Read tasks/current-task.md and tell me:
1. What was the goal
2. What was completed
3. What the last checkpoint says
4. What the next step is
Do not start working until you have confirmed your understanding.
```

## Code review before committing

```
Before I commit this, review for:
1. Does it solve the stated problem (not a different problem)?
2. Is this the simplest solution that works?
3. Did I add anything that was not asked for?
4. Are there obvious edge cases not handled?
Be direct. Do not soften issues.
```

## MCP server testing

```
Test this MCP server before I connect it to Claude:
1. Send tools/list and show the response
2. Call [tool_name] with these test arguments: [args]
3. Verify the response format matches what Claude expects
4. Note any errors in the tool description or argument schema
```
