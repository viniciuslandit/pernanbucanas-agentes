---
name: playwright-e2e
description: Cria ou atualiza testes E2E com Playwright para um fluxo da aplicação. Use quando o usuário pedir "/playwright-e2e <fluxo>" ou quiser gerar testes end-to-end de uma tela ou jornada (ex.: login, checkout, busca de produto).
---

# Playwright E2E

Gere testes E2E com Playwright para o fluxo indicado em `$ARGUMENTS`. Se nenhum fluxo foi indicado, pergunte qual fluxo testar antes de começar.

## Passos

1. Delegue a escrita dos testes ao agente `playwright-tester` (via Agent tool), passando:
   - o fluxo/jornada a testar;
   - o diretório do projeto e convenções encontradas (`playwright.config.ts`, pasta de testes existente);
   - instrução para usar o Playwright MCP se disponível.
2. Ao receber o resultado, rode os testes (`npx playwright test --reporter=line`) se o agente ainda não tiver rodado, e reporte ao usuário:
   - arquivos criados/alterados;
   - resultado da execução;
   - como rodar localmente (incluindo `--ui` para modo interativo).

## Regras

- Cobrir o caminho feliz e ao menos um cenário de erro (incluindo mensagens tratadas para respostas 400/404 exibidas na tela).
- Seguir as convenções do projeto; não criar nova estrutura de testes se já houver uma.
