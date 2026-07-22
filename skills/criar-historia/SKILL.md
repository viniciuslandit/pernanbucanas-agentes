---
name: criar-historia
description: Cria ou revisa histórias de usuário (Como/Quero/Para) com critérios de aceite, DoR, DoD, validação INVEST e cenários BDD em Gherkin. Use quando o usuário pedir "/criar-historia <demanda>" ou quiser escrever/revisar histórias de backlog.
---

# Criar História

Crie ou revise a história de usuário indicada em `$ARGUMENTS`. Se nada foi indicado, pergunte qual é a demanda ou qual história deve ser revisada.

## Passos

1. Delegue ao agente `product-owner` (via Agent tool), passando:
   - a demanda ou a história existente a revisar;
   - contexto do produto e do projeto disponível (código, documentação, `.feature` existentes);
   - se é criação ou revisão.
2. Ao receber o resultado, reporte ao usuário:
   - a história completa (Como/Quero/Para, critérios de aceite, cenários BDD, DoR, DoD);
   - a avaliação INVEST letra a letra;
   - as perguntas em aberto que precisam de resposta antes do refinamento.

## Regras

- História sempre no formato Como/Quero/Para com valor de negócio explícito no "Para".
- Critérios de aceite numerados, objetivos e testáveis.
- Cenários BDD em Gherkin pt-BR cobrindo caminho feliz, validações e erros (incluindo mensagem tratada na tela para respostas 400/404).
- Se a história for grande demais (falha no S do INVEST), propor a quebra em histórias menores.
- Dúvidas de negócio viram perguntas explícitas, nunca suposições.
