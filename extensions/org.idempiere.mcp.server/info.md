# iDempiere MCP Server

**Summary:** This extension implements a [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server for iDempiere ERP. It acts as a bridge between AI assistants (such as Google Gemini and Anthropic Claude) and iDempiere, allowing AI agents to autonomously retrieve data, execute processes, and manage records via tools.

## 🚀 Features

* **AI Interaction:** Enables AI assistants to "use" iDempiere as a toolset.
* **Autonomous Authentication:** Includes `create_auth_token` and `set_auth_token` tool to handle login flows directly through the AI.
* **Data Retrieval:** Bridges AI prompts to iDempiere data models for searching Business Partners, products, or transactions.
* **Process Execution:** Allows AI to trigger and monitor server-side processes and jobs.
* **Flexible Transport:** Supports Streamable HTTP transport (default at `/mcp/`) for integration with various MCP clients.
* **Multi-Tenant Support:** Supports multiple authentication tokens for different iDempiere tenants simultaneously.

## ⚙️ Compatibility

* **iDempiere Version:** 13
* **Protocol Version:** MCP 2025-06-18
* **Requirement:** Must have `com.trekglobal.idempiere.rest.api` installed and started.

## 📦 Database Changes

* **System Metadata:** No direct SQL scripts; relies on existing iDempiere REST API configurations and standard OSGi service registration.

## 🛠 Usage & Configuration

* **Authentication:** * Use the `set_auth_token` tool to provide an existing JWT.
    * Or use `create_auth_token` with standard credentials (User, Password, Client, Org, Role, Warehouse).
* **Environment Variables:**
    * `MCP_HEARTBEAT_INTERVAL_MS`: Default `15000` (15s).
    * `MCP_THREAD_POOL_SIZE`: Default `100`.
    * `MCP_CORS_ORIGIN`: Default `*`.
* **Client Setup:** For Gemini CLI or MCP Inspector, use the endpoint `http://<your-server>:<port>/mcp/`. **Note:** The trailing slash is mandatory.

## 👤 Author / Support

* **Developer:** [hengsin](https://github.com/hengsin)
* **Source Code:** [https://github.com/hengsin/idempiere-mcp](https://github.com/hengsin/idempiere-mcp)
* **Issue Tracker:** [https://github.com/hengsin/idempiere-mcp/issues](https://github.com/hengsin/idempiere-mcp/issues)