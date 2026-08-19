---
name: tribunal_tjsc_pedido_certidao-mcp
description: Skill da REST API do Tribunal TJSC: Pedido de Certidão na MCP.AI: 1 endpoint em /api/tribunal_tjsc_pedido_certidao. Tribunal TJSC: Pedido de Certidão, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TJSC: Pedido de Certidão — REST API skill

Você tem acesso à **Tribunal TJSC: Pedido de Certidão** REST API na MCP.AI.

> Tribunal TJSC: Pedido de Certidão, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_tjsc_pedido_certidao
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
curl -X POST https://api.mcp.ai/api/tribunal_tjsc_pedido_certidao/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"instancia":"...","tipo":"...","nome":"...","uf":"...","municipio":"...","email":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_tjsc_pedido_certidao/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_tjsc_pedido_certidao_consultar`

Tribunal TJSC: Pedido de Certidão, consulta em fonte oficial. _(POST /api/tribunal_tjsc_pedido_certidao/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `instancia` | string | Sim | Parâmetro de consulta "instancia". |
| `tipo` | string | Sim | Parâmetro de consulta "tipo". |
| `finalidade_certidao` | string | Não | Parâmetro de consulta "finalidade_certidao". |
| `nome` | string | Sim | Parâmetro de consulta "nome". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `rg` | string | Não | Parâmetro de consulta "rg". |
| `orgao_expedidor` | string | Não | Parâmetro de consulta "orgao_expedidor". |
| `uf` | string | Sim | Parâmetro de consulta "uf". |
| `municipio` | string | Sim | Parâmetro de consulta "municipio". |
| `email` | string | Sim | Parâmetro de consulta "email". |
| `nome_mae` | string | Não | Parâmetro de consulta "nome_mae". |
| `nome_pai` | string | Não | Parâmetro de consulta "nome_pai". |
| `birthdate` | string | Não | Parâmetro de consulta "birthdate". |
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_tjsc_pedido_certidao` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
