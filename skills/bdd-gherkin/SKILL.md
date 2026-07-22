---
name: bdd-gherkin
description: Gera cenários BDD em Gherkin (Dado/Quando/Então) para uma história de usuário ou funcionalidade. Use quando o usuário pedir "/bdd-gherkin <funcionalidade>" ou quiser transformar requisitos em arquivos .feature.
---

# BDD Gherkin

Gere cenários BDD em Gherkin (pt-BR) para a funcionalidade ou história indicada em `$ARGUMENTS`. Se nada foi indicado, pergunte qual funcionalidade ou história de usuário deve ser coberta.

## Passos

1. Delegue a escrita ao agente `bdd-gherkin` (via Agent tool), passando:
   - a história/funcionalidade e qualquer critério de aceite fornecido;
   - onde encontrar o código ou documentação relevante no projeto;
   - as convenções de arquivos `.feature` já existentes, se houver.
2. Ao receber o resultado, reporte ao usuário:
   - arquivos `.feature` criados/alterados;
   - resumo dos cenários (caminho feliz, validações, erros);
   - dúvidas de regra de negócio levantadas pelo agente que precisam de resposta do time.

## Regras

- Cenários em português com `# language: pt`.
- Cobrir caminho feliz, validações e erros de integração (incluindo mensagem tratada na tela para respostas 400/404).
- Não inventar regras de negócio: o que não estiver claro vira pergunta ao usuário, não cenário.
