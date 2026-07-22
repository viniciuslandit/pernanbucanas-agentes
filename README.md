# pernanbucanas-agentes

Plugin do [Claude Code](https://claude.com/claude-code) com 5 agentes e skills para o fluxo de desenvolvimento do time Pernambucanas — do card no Azure DevOps/Jira até o teste E2E.

## Instalação

No Claude Code:

```
/plugin marketplace add viniciuslandit/pernanbucanas-agentes
/plugin install pernanbucanas-agentes@pernanbucanas-agentes
```

## Agentes e skills

| Agente | Skill | O que faz |
|--------|-------|-----------|
| `user-story-reader` | `/ler-card <id ou URL>` | Lê e extrai cards do Azure DevOps ou Jira (via MCP) em formato estruturado: descrição, critérios de aceite, subtarefas, dependências e lacunas. |
| `product-owner` | `/criar-historia <demanda>` | Cria/revisa histórias "Como/Quero/Para" com critérios de aceite, validação INVEST, DoR, DoD e cenários BDD em Gherkin. |
| `tech-lead` | `/refinar-historia <história>` | Refinamento técnico baseado no código real do repositório e quebra da história em subtarefas pequenas e verificáveis, com dependências e ordem. |
| `bdd-gherkin` | `/bdd-gherkin <funcionalidade>` | Escreve cenários BDD em Gherkin pt-BR (Dado/Quando/Então), cobrindo caminho feliz, validações e erros. |
| `playwright-tester` | `/playwright-e2e <fluxo>` | Escreve e executa testes E2E com Playwright, usando o Playwright MCP quando disponível para explorar a aplicação real. |

## Fluxo sugerido

```
/ler-card AB#1234        →  extrai o card do Azure DevOps/Jira
/criar-historia          →  revisa a história (INVEST, DoR/DoD, BDD)
/refinar-historia        →  refinamento técnico + subtarefas
/bdd-gherkin             →  cenários .feature detalhados
/playwright-e2e          →  testes E2E do fluxo implementado
```

## Convenções do time

- Histórias, cenários e testes escritos em **pt-BR**.
- Cenários Gherkin com `# language: pt`.
- Erros de API **400/404** sempre exibem mensagem tratada na tela do frontend — coberto por critérios de aceite, cenários BDD e asserções E2E.

## Pré-requisitos opcionais (MCP)

- **Playwright MCP** — para o `playwright-tester` explorar a aplicação no navegador.
- **Azure DevOps MCP / Atlassian MCP** — para o `user-story-reader` acessar os cards. Sem MCP, o agente aceita o conteúdo do card colado na conversa.
