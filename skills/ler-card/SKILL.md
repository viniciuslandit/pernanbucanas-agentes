---
name: ler-card
description: Lê e extrai um card/work item do Azure DevOps ou Jira (via MCP) em formato estruturado. Use quando o usuário pedir "/ler-card <id ou URL>" ou quiser trazer o conteúdo de uma história, bug ou épico para dentro da conversa.
---

# Ler Card

Extraia de forma estruturada o card indicado em `$ARGUMENTS` (ID como `AB#1234` / `PROJ-123` ou URL do Azure DevOps/Jira). Se nenhum card foi indicado, pergunte o ID ou a URL.

## Passos

1. Delegue a extração ao agente `user-story-reader` (via Agent tool), passando:
   - o identificador ou URL do card;
   - o sistema (Azure DevOps ou Jira), se conhecido;
   - se deve incluir subtarefas, card pai e dependências (padrão: sim).
2. Ao receber o resultado, apresente ao usuário:
   - o documento estruturado do card (metadados, descrição, critérios de aceite, subtarefas, dependências, comentários relevantes);
   - a seção de lacunas identificadas (o que falta no card).

## Regras

- Conteúdo fiel ao card: critérios de aceite e regras de negócio transcritos, nunca parafraseados.
- Se não houver MCP nem CLI configurados, informar o que falta e oferecer que o usuário cole o conteúdo do card.
- Nunca alterar o card — esta skill é somente leitura.

## Combinações úteis

Após a leitura, sugira o próximo passo quando fizer sentido:
- `/criar-historia` para revisar a história extraída (INVEST, DoR/DoD);
- `/refinar-historia` para o refinamento técnico e quebra em subtarefas;
- `/bdd-gherkin` para gerar os cenários BDD do card.
