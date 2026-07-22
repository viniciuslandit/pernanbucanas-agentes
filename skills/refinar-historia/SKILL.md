---
name: refinar-historia
description: Refina tecnicamente uma história de usuário e a quebra em subtarefas implementáveis. Use quando o usuário pedir "/refinar-historia <história>" ou quiser refinamento técnico, quebra de tarefas ou planejamento de uma feature.
---

# Refinar História

Refine tecnicamente a história indicada em `$ARGUMENTS` e quebre-a em subtarefas. Se nenhuma história foi indicada, pergunte qual história refinar (texto, link ou arquivo).

## Passos

1. Delegue o refinamento ao agente `tech-lead` (via Agent tool), passando:
   - a história completa e critérios de aceite disponíveis;
   - o diretório do projeto para exploração do código real;
   - cenários BDD relacionados, se existirem (arquivos `.feature`).
2. Ao receber o resultado, reporte ao usuário:
   - o documento de refinamento (contexto, solução, tratamento de erros, riscos, fora de escopo);
   - a lista numerada de subtarefas com dependências e ordem sugerida;
   - as perguntas em aberto que precisam de resposta do time antes do desenvolvimento.

## Regras

- O refinamento deve citar arquivos e componentes reais do repositório, não abstrações genéricas.
- Subtarefas pequenas (≤ 1 dia) e verificáveis, incluindo tarefas de teste.
- Tratamento de erros 400/404 com mensagem tratada na tela do frontend deve constar na solução proposta.
- Dúvidas de negócio viram perguntas explícitas, nunca suposições.
