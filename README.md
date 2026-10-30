# Mofi

[![MCP Registry](https://img.shields.io/badge/MCP%20Registry-br.com.omofi%2Fmofi-0b7285)](https://registry.modelcontextprotocol.io/v0.1/servers?search=br.com.omofi)
[![Site](https://img.shields.io/badge/site-omofi.com.br-68d3c9)](https://omofi.com.br/desenvolvedores?utm_source=github&utm_medium=directory&utm_campaign=mcp-directories)

**PT-BR** · [English](#english)

Entenda seus gastos em segundos.

O Mofi conecta suas contas bancárias brasileiras via Open Finance. **Acesso somente leitura ao banco; nunca movimenta dinheiro.** Algumas ferramentas escrevem só dentro do Mofi (categorias e pedido de nova sincronização).
Você pergunta, o Mofi responde com seus dados reais:
no app ou pelo seu agente de IA via MCP (planos pagos) e CLI.

- Não move dinheiro.
- O login do banco acontece só na janela segura do provedor regulado. O Mofi nunca vê a senha do seu banco.
- Funciona com bancos brasileiros participantes do Open Finance.
- Demo com dados fictícios: https://omofi.com.br/demo?utm_source=github&utm_medium=directory&utm_campaign=mcp-directories

Este repositório só tem documentação e manifestos. O código do Mofi não é público.

## Conectar via MCP
**O MCP está incluído em todos os planos pagos do Mofi (Solo, Premium e Pro), a partir de R$10/mês. Não há plano gratuito.** Sem plano ativo, o servidor responde 402.

Servidor remoto (Streamable HTTP + OAuth):

```
https://omofi.com.br/api/mcp
```

Cursor e Grok Bot (testados) ou outro cliente MCP compatível com OAuth: adicione um servidor MCP personalizado com a URL acima e entre com sua conta Mofi.
Guia completo: https://omofi.com.br/docs/mcp

Exemplos:
- "Quanto gastei com delivery em setembro?"
- "Qual cartão fecha esta semana?"
- "Onde meus gastos subiram em relação ao mês passado?"

## Autenticação e ferramentas
OAuth 2.1 com PKCE (S256), Client ID Metadata Documents (CIMD) e registro dinâmico de cliente (DCR). Sem chave de API.
Escopos: `mcp:read` (leitura) e `mcp:sync` (sincronizar conexões).

13 ferramentas. Nenhuma move dinheiro. As 2 de escrita alteram dados só dentro do Mofi, nunca no banco.

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

Para desenvolvedores: https://omofi.com.br/desenvolvedores?utm_source=github&utm_medium=directory&utm_campaign=mcp-directories · Docs: https://omofi.com.br/docs/mcp

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
- Glama: https://glama.ai/mcp/connectors/br.com.omofi/mofi
- Outros diretórios: links quando publicados

---

## English

Understand your spending in seconds.

Mofi connects Brazilian bank accounts through Open Finance. **Read-only bank access, never moves money.** A few tools write only inside Mofi (transaction categories, re-sync requests).
Ask questions and get answers from your real data:
in the app or from your AI agent via MCP (paid plans) and CLI.

- Never moves money.
- Bank login happens only in the regulated provider's secure window. Mofi never sees your bank password.
- Works with Brazilian banks in Open Finance. Brazil only.
- Demo with fictional data: https://omofi.com.br/demo?utm_source=github&utm_medium=directory&utm_campaign=mcp-directories

This repository holds docs and manifests only. Mofi's source code is not public.

### Connect via MCP
**MCP is included in every paid Mofi plan (Solo, Premium, Pro), from R$10/month. No free plan.** Without an active plan, the server returns 402.

Remote server (Streamable HTTP + OAuth): `https://omofi.com.br/api/mcp`
Add it as a custom MCP server in Cursor or Grok Bot (tested) or another MCP client with OAuth support and sign in with your Mofi account.
Guide (Portuguese): https://omofi.com.br/docs/mcp

### Auth and tools
OAuth 2.1 with PKCE (S256), Client ID Metadata Documents (CIMD) and dynamic client registration (DCR). No API key.
Scopes: `mcp:read` (read) and `mcp:sync` (sync connections).

13 tools; none moves money. The 2 write tools change data only inside Mofi, never at the bank.
11 read: `mofi_identity_get`, `mofi_accounts_get`, `mofi_cards_get`, `mofi_spending_get`, `mofi_spending_summary_get`, `mofi_connections_get`, `mofi_recurring_get`, `mofi_classifications_get`, `mofi_transactions_get`, `mofi_statements_get`, `mofi_sync_get`.
2 non-destructive writes: `mofi_classifications_save` (save transaction categories), `mofi_connections_sync` (request a bank sync).

For developers: https://omofi.com.br/desenvolvedores?utm_source=github&utm_medium=directory&utm_campaign=mcp-directories · Docs (Portuguese): https://omofi.com.br/docs/mcp

### CLI
```sh
curl -fsSL https://omofi.com.br/install.sh | sh
mofi login
```

### Privacy and terms
- Privacy policy: https://omofi.com.br/privacidade
- Terms: https://omofi.com.br/termos
- Contact: contato@omofi.com.br
