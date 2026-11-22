---
name: propor-melhoria
description: Lê o registro de decisões e as lições, encontra padrões de correção e rejeição, e cria propostas de melhoria para o CLAUDE.md ou para as skills em conhecimento/melhorias/. Também registra uma ideia de melhoria trazida por alguém da equipe. Use quando disserem "o que precisamos melhorar", "roda a retroalimentação", "revisão semanal do harness", "quero que o agente passe a fazer X", "registra essa lição".
---

# Propor melhoria

## Quando a origem é o histórico (rotina semanal)
1. Leia `registro/decisoes/` do período pedido (padrão: últimos 7 dias) e `conhecimento/licoes/` recentes.
2. Agrupe os gates `corrigido` e `rejeitado` por skill e por motivo parecido.
3. Para cada grupo com **2 ou mais ocorrências**, ou para qualquer incidente, escreva uma proposta usando `conhecimento/melhorias/_modelo.md`:
   - cite os ids dos registros que motivaram;
   - escreva o **texto exato** que entraria no CLAUDE.md ou na skill;
   - defina como medir se funcionou.
4. Numere `M-NNN` na sequência das existentes. Status `proposta`.
5. **Não altere** o CLAUDE.md nem as skills. Aplicar só depois de aprovação do dono do processo.
6. Termine com um resumo: quantos registros lidos, taxa de aprovação por skill, propostas criadas.

## Quando a origem é uma pessoa
1. Pergunte: qual o problema, em qual processo, e quem decide sobre ele (ver `governanca/niveis-e-gates.md`).
2. Crie a proposta com status `proposta` e a pessoa como autora.
3. Se for só um aprendizado, sem mudança de regra, crie uma lição em `conhecimento/licoes/` em vez de uma melhoria.

## Quando a proposta for aprovada
Quando o dono do processo disser "aprovo a M-NNN":
1. Aplique o texto no destino. No CLAUDE.md, coloque na seção "Conhecimento da empresa" com "Origem: M-NNN, aprovada em DD/MM/AAAA".
2. Atualize a proposta com status `aplicada` e a decisão.
3. Chame `registrar-decisao` (tipo `decisao_humana`, nível C, `aprovado_por` = dono).
4. Sugira o commit: `harness: aplica M-NNN <título>`.
