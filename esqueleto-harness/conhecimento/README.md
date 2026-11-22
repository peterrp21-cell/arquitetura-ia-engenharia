# Conhecimento da empresa (retroalimentação)

É por aqui que o harness aprende o jeito da sua empresa: os padrões peculiares, as lições de cada projeto e as melhorias que alguém quiser implementar.

## Pastas
- `licoes/`: o que aprendemos (um erro, um acerto, uma particularidade de cliente, de norma ou de obra). Qualquer pessoa pode escrever.
- `melhorias/`: propostas de mudança no harness (no CLAUDE.md, numa skill, num gate ou num nível). Precisam ser aprovadas.

## O ciclo
```
1. Fonte        correções nos gates (registro/decisoes), lições, ideias da equipe, mudança de norma
2. Proposta     skill propor-melhoria cria conhecimento/melhorias/M-NNN.md
3. Decisão      o dono do processo aprova ou rejeita (e isso também é registrado)
4. Aplicação    a mudança entra no CLAUDE.md ou na skill, num commit que cita M-NNN
5. Verificação  nas próximas semanas, o registro mostra se as correções daquele tipo caíram
```

## Ritmo sugerido
- **Toda semana (15 min):** o responsável roda `propor-melhoria` sobre as correções da semana.
- **Todo mês (1 h):** reunião rápida para aprovar ou rejeitar as propostas e olhar os números do registro.

## Regras
1. Nenhuma regra nova entra no harness sem proposta aprovada. Isso evita que o agente "aprenda" um erro de uma pessoa só.
2. Toda regra no CLAUDE.md indica a origem (`M-NNN`), para dar pra rastrear por que ela existe.
3. Regra que ninguém lembra por que existe vai para revisão na reunião mensal.
