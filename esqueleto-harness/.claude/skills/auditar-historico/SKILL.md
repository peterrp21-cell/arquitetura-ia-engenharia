---
name: auditar-historico
description: Responde perguntas de auditoria sobre o histórico de decisões, melhorias e mudanças de regra do harness, sempre citando os registros. Use para "quem aprovou X", "o que a IA fez no projeto Y", "quantas correções tivemos no mês", "por que existe essa regra", "relatório mensal do harness", "o que mudou desde junho".
---

# Auditar histórico

## Fontes (nesta ordem)
1. `registro/decisoes/*.jsonl`: decisões e gates.
2. `conhecimento/melhorias/`: por que cada regra existe.
3. Histórico do Git (`git log -p` nos arquivos relevantes): quem mudou cada regra e quando.

## Regras
- **Toda afirmação cita a fonte:** id do registro (`D-…`), id da melhoria (`M-…`) ou hash do commit.
- Se o histórico não tiver a resposta, diga isso. Nunca complete com suposição.
- Aponte lacunas: decisão de nível C sem registro, gate sem `aprovado_por`, saída enviada ao cliente sem gate, linhas fora de ordem ou retificações em excesso.
- Não altere nenhum arquivo. Auditoria só lê.

## Relatório mensal (quando pedirem)
1. Execuções e gates por skill; taxa de aprovação direta (aprovado / total de gates).
2. Principais motivos de correção.
3. Tempo humano economizado (soma de `minutos_antes - minutos_humanos` onde houver os dois).
4. Melhorias aprovadas e aplicadas no mês, e se as correções daquele tipo caíram.
5. Lacunas de governança encontradas.
