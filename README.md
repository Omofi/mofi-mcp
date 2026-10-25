# Mofi

[![MCP Registry](https://img.shields.io/badge/MCP%20Registry-br.com.omofi%2Fmofi-0b7285)](https://registry.modelcontextprotocol.io/v0/servers?search=br.com.omofi/mofi)
[![Site](https://img.shields.io/badge/site-omofi.com.br-68d3c9)](https://omofi.com.br/?utm_source=github&utm_medium=readme&utm_campaign=fundadores-2026-11)

**PT-BR** · [English](#english)

Entenda seus gastos em segundos.

O Mofi conecta suas contas bancárias brasileiras via Open Finance. **A conexão bancária é somente leitura.**
Você pergunta, o Mofi responde com seus dados reais:
no app, no WhatsApp (em testes) ou pelo seu agente de IA via MCP e CLI.

- Não move dinheiro.
- O login do banco acontece só no widget Pluggy Connect. O Mofi nunca vê a senha do seu banco.
- Funciona com bancos brasileiros participantes do Open Finance.
- Demo com dados fictícios: https://omofi.com.br/demo?utm_source=github&utm_medium=readme&utm_campaign=fundadores-2026-11

Este repositório só tem documentação e manifestos. O código do Mofi não é público.

## Conectar via MCP
Servidor remoto (Streamable HTTP + OAuth):

```
https://omofi.com.br/api/mcp
```

Claude, ChatGPT ou Cursor: adicione um conector/servidor MCP personalizado com a URL acima e entre com sua conta Mofi.
Guia completo: https://omofi.com.br/docs/mcp

Exemplos:
- "Quanto gastei com delivery em setembro?"
- "Qual cartão fecha esta semana?"
- "Onde meus gastos subiram em relação ao mês passado?"

## Autenticação e ferramentas
OAuth 2.1 com PKCE e registro dinâmico de cliente.
Escopos: `mcp:read` (leitura) e `mcp:sync` (sincronizar conexões).

13 ferramentas. Nenhuma move dinheiro.

Leitura (11):
- `mofi_identity_get`
- `mofi_accounts_get`
- `mofi_cards_get`
- `mofi_spending_get`
- `mofi_spending_summary_get`
- `mofi_connections_get`
- `mofi_recurring_get`
- `mofi_classifications_get`
- `mofi_transactions_get`
- `mofi_statements_get`
- `mofi_sync_get`

Escrita não destrutiva (2):
- `mofi_classifications_save`: salva a categoria de transações.
- `mofi_connections_sync`: pede uma nova sincronização com o banco.

Visão geral: https://omofi.com.br/mcp · Docs: https://omofi.com.br/docs/mcp

## CLI
```sh
curl -fsSL https://omofi.com.br/install.sh | sh
mofi login
```
Instala em `~/.local/bin`. Confira o script antes de rodar.

## Privacidade e termos
- Política de privacidade: https://omofi.com.br/privacidade
- Termos de uso: https://omofi.com.br/termos
- Contato: contato@omofi.com.br

## Onde o Mofi está listado
- Registry oficial MCP: `br.com.omofi/mofi`
- Glama · Smithery · mcp.so · mcpservers.org (links quando publicados)

---

## English

Understand your spending in seconds.

Mofi connects Brazilian bank accounts through Open Finance. **The bank connection is read-only.**
Ask questions and get answers from your real data:
in the app, on WhatsApp (in testing), or from your AI agent via MCP and CLI.

- Never moves money.
- Bank login happens only in the Pluggy Connect widget. Mofi never sees your bank password.
- Works with Brazilian banks in Open Finance. Brazil only.
- Demo with fictional data: https://omofi.com.br/demo?utm_source=github&utm_medium=readme&utm_campaign=fundadores-2026-11

This repository holds docs and manifests only. Mofi's source code is not public.

### Connect via MCP
Remote server (Streamable HTTP + OAuth): `https://omofi.com.br/api/mcp`
Add it as a custom connector in Claude, ChatGPT or Cursor and sign in with your Mofi account.
Guide (Portuguese): https://omofi.com.br/docs/mcp

### Auth and tools
OAuth 2.1 with PKCE and dynamic client registration.
Scopes: `mcp:read` (read) and `mcp:sync` (sync connections).

13 tools; none moves money.
11 read: `mofi_identity_get`, `mofi_accounts_get`, `mofi_cards_get`, `mofi_spending_get`, `mofi_spending_summary_get`, `mofi_connections_get`, `mofi_recurring_get`, `mofi_classifications_get`, `mofi_transactions_get`, `mofi_statements_get`, `mofi_sync_get`.
2 non-destructive writes: `mofi_classifications_save` (save transaction categories), `mofi_connections_sync` (request a bank sync).

Overview: https://omofi.com.br/mcp · Docs (Portuguese): https://omofi.com.br/docs/mcp

### CLI
```sh
curl -fsSL https://omofi.com.br/install.sh | sh
mofi login
```

### Privacy and terms
- Privacy policy: https://omofi.com.br/privacidade
- Terms: https://omofi.com.br/termos
- Contact: contato@omofi.com.br
