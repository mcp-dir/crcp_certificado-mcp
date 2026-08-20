---
name: crcp_certificado-mcp
description: Skill da REST API do CRCP: Central de Registros de Certificados Profissionais na MCP.AI: 1 endpoint em /api/crcp_certificado. CRCP: Central de Registros de Certificados Profissionais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# CRCP: Central de Registros de Certificados Profissionais — REST API skill

Você tem acesso à **CRCP: Central de Registros de Certificados Profissionais** REST API na MCP.AI.

> CRCP: Central de Registros de Certificados Profissionais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/crcp_certificado
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/crcp_certificado/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cpf":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/crcp_certificado/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `crcp_certificado_consultar`

CRCP: Central de Registros de Certificados Profissionais, consulta em fonte oficial. _(POST /api/crcp_certificado/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Sim | Parâmetro de consulta "cpf". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_crcp_certificado` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
