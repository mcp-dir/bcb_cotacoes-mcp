---
name: bcb_cotacoes-mcp
description: Skill da REST API do Banco Central do Brasil (BCB): Cotações na MCP.AI: 1 endpoint em /api/bcb_cotacoes. Banco Central do Brasil (BCB): Cotações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Banco Central do Brasil (BCB): Cotações — REST API skill

Você tem acesso à **Banco Central do Brasil (BCB): Cotações** REST API na MCP.AI.

> Banco Central do Brasil (BCB): Cotações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/bcb_cotacoes
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
curl -X POST https://api.mcp.ai/api/bcb_cotacoes/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/bcb_cotacoes/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `bcb_cotacoes_consultar`

Banco Central do Brasil (BCB): Cotações, consulta em fonte oficial. _(POST /api/bcb_cotacoes/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Não | Parâmetro de consulta "data". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_bcb_cotacoes` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
