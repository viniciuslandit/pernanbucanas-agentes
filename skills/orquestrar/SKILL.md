---
name: orquestrar
description: Orquestra o fluxo completo de uma demanda com os agentes do time (ler card → história → refinamento → BDD → testes E2E). Use quando o usuário pedir "/orquestrar <demanda ou card>" ou quiser conduzir uma demanda por várias etapas encadeadas.
---

# Orquestrar

Conduza a demanda indicada em `$ARGUMENTS` pelo fluxo do time. Se nada foi indicado, pergunte qual é a demanda (ID de card, história ou descrição da feature) e até qual etapa deve ir.

## Passos

1. Delegue ao agente `orquestrador` (via Agent tool), passando:
   - a demanda completa (ID/URL do card, texto da história ou descrição);
   - até qual etapa executar, se o usuário especificou (ex.: "até o refinamento");
   - o diretório do projeto e artefatos já existentes (história pronta, `.feature`, testes) para não refazer trabalho.
2. Se o orquestrador retornar perguntas em aberto que bloqueiam o fluxo, apresente-as ao usuário e, com as respostas, retome via SendMessage ao mesmo agente.
3. Ao final, apresente o relatório consolidado: artefatos gerados por etapa, perguntas em aberto e próximos passos.

## Regras

- O fluxo completo é: `ler-card` → `criar-historia` → `refinar-historia` → `bdd-gherkin` → `playwright-e2e`, mas o orquestrador executa apenas as etapas que a demanda exige.
- Nunca deixar um subagente supor regra de negócio: dúvida bloqueante volta ao usuário.
