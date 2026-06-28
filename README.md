# RadTask MCP Server

**Connect any AI to your task cockpit.** RadTask is an AI task manager whose agent actually *does* the task — and asks first before anything irreversible. It runs a live **MCP** (Model Context Protocol) server, so Claude, ChatGPT, Cursor, or your own agent can create and track tasks that land in the user's [RadTask](https://radtask.ai) cockpit, where a safe autonomous agent runs them.

> Private beta. A tool with a safety design — not a guarantee.

## Connect

**Endpoint** (Streamable HTTP, JSON-RPC 2.0):

```
https://radtask.ai/api/mcp?token=YOUR_TOKEN
```

Get your private token at **[radtask.ai/connect](https://radtask.ai/connect)**. The token is your cockpit's namespace — tasks an AI adds appear in your RadTask.

### Claude Desktop / Cursor

```json
{
  "mcpServers": {
    "radtask": { "type": "http", "url": "https://radtask.ai/api/mcp?token=YOUR_TOKEN" }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `create_task` | Capture a task in plain English (optional `project`) |
| `list_tasks` | List tasks, optionally filtered by `status` |
| `complete_task` | Mark a task done by `id` |

## Why RadTask is different

Most "task manager" MCP servers are queues — they track what an AI *should* do. RadTask **does the task**: a real agent researches, drafts, writes documents, and schedules in a sandbox — and a deterministic risk classifier holds *only* the irreversible steps (sending, spending, deleting, publishing) for the user's one-tap approval.

The safety posture is published and machine-verifiable:

- **Safety contract:** https://radtask.ai/.well-known/agent-safety.json
- **MCP manifest:** https://radtask.ai/.well-known/mcp.json
- **For AI agents:** https://radtask.ai/for-agents
- **llms.txt:** https://radtask.ai/llms.txt

Design goal: **zero unsupervised destructive actions.** Irreversible actions are always held for a human.

## Links

- Product: https://radtask.ai
- MCP page: https://radtask.ai/mcp
- A Sureel product · part of the Rad family (RadMail · RadTask · RadHealth)

## License

MIT © Sureel
