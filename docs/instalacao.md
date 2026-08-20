# Instalação detalhada

CRCP: Central de Registros de Certificados Profissionais é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/p_crcp_certificado`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/p_crcp_certificado` | OAuth 2.1 ou agent-auth |
| Cursor | `https://api.mcp.ai/p_crcp_certificado` | OAuth 2.1 ou agent-auth |
| VS Code (Copilot) | `https://api.mcp.ai/p_crcp_certificado` | OAuth 2.1 ou agent-auth |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.crcp_certificado` (ou `servers.crcp_certificado` no VS Code) do config do cliente e reinicie.
