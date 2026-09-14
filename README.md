# SQL Server MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/mssql)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect SQL Server to AI assistants: schemas, tables, T-SQL and database health for SQL Server and Azure SQL.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use SQL Server from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/mssql-icon.svg" alt="SQL Server MCP Server" width="64" height="64">

## MCP Server URL

```
https://mssql.insightfulmcp.com/
```

## What is SQL Server MCP?

SQL Server MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Browse schemas, inspect tables, and run T-SQL against your own Microsoft SQL Server or Azure SQL instance. Read vs. read-write is decided by the GRANT/REVOKE privileges on the login this connector uses.

## Installation

### Claude

1. Copy the MCP Server URL: `https://mssql.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://mssql.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http mssql https://mssql.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "mssql": {
      "url": "https://mssql.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

8 actions: 7 read, 1 write.

### Read Actions (7)

| Action | Description |
|--------|-------------|
| `analyze_db_health` | Connection state + memory clerks + log-reuse health |
| `explain_query` | SHOWPLAN_XML for a query |
| `get_table_metadata` | Full metadata: columns + constraints + indexes + estimated size |
| `get_table_schema` | Column list for a table or view |
| `get_top_queries` | Heaviest queries from sys.dm_exec_query_stats |
| `list_schemas` | List all schemas in the connected database |
| `list_tables` | List tables, views, or sequences in a schema |

### Write Actions (1)

| Action | Description |
|--------|-------------|
| `run_query` | Execute a T-SQL statement |

## Usage Examples

```
"List the tables in the dbo schema"
```

```
"Show the schema of the Orders table"
```

```
"Check my database health"
```

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [PostgreSQL MCP](https://insightfulpipe.com/mcp-servers/postgresql)
- [MySQL MCP](https://insightfulpipe.com/mcp-servers/mysql)
- [BigQuery MCP](https://insightfulpipe.com/mcp-servers/bigquery)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
