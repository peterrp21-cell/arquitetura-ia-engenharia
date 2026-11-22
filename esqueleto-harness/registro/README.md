# Registro de decisões (trilha de auditoria)

Aqui fica o histórico de **todas as decisões relevantes, da IA e das pessoas**. Serve para três coisas:
1. **Auditoria:** quem decidiu, quando, com base em quê, e quem aprovou.
2. **Retroalimentação:** as correções feitas nos gates mostram o que o harness precisa aprender.
3. **Medição:** tempo economizado, taxa de aprovação de cada skill e evolução mês a mês.

## Como é gravado
- Um arquivo por mês: `registro/decisoes/AAAA-MM.jsonl`.
- **Uma linha por decisão**, em JSON. As linhas só são acrescentadas, nunca editadas ou apagadas. Para corrigir um registro, grave um novo, do tipo `retificacao`, apontando o id do original.
- O arquivo é versionado no Git. Cada commit diz quem gravou e quando, o que impede alterar o passado sem deixar rastro.
- Quem grava é a skill `registrar-decisao`. Toda skill do harness chama essa skill no fim.

## Campos de cada linha

| Campo | Obrigatório | O que é |
|---|---|---|
| `id` | sim | `D-AAAAMMDD-NNN` |
| `data_hora` | sim | ISO 8601, com fuso (ex.: `2026-11-15T19:40:00-03:00`) |
| `tipo` | sim | `execucao` (agente fez), `gate` (humano aprovou/corrigiu/rejeitou), `decisao_humana` (nível C), `incidente`, `retificacao` |
| `projeto` | sim | código do projeto/obra (ou `INTERNO`) |
| `skill` | sim | nome da skill usada (ou `manual`) |
| `nivel` | sim | `A`, `B` ou `C` |
| `quem` | sim | pessoa (nome) ou agente (`agente:<modelo>`) |
| `entrada` | sim | o que foi usado como base: caminhos de arquivo, links, "áudio do encarregado 14/11" |
| `saida` | sim | onde ficou o resultado (caminho ou link) |
| `resultado` | só em gate | `aprovado`, `corrigido`, `rejeitado` |
| `motivo` | em gate corrigido/rejeitado e em decisão C | por que, em uma frase |
| `aprovado_por` | em gate | nome |
| `minutos_humanos` | opcional | tempo que a pessoa gastou (revisão incluída) |
| `minutos_antes` | opcional | quanto levava sem o harness (do baseline) |
| `ref` | opcional | id de outro registro (retificação, decisão relacionada) |

## Exemplo (fictício)
```json
{"id":"D-20261115-001","data_hora":"2026-11-15T18:02:00-03:00","tipo":"execucao","projeto":"O-2026-007","skill":"rdo","nivel":"B","quem":"agente:claude","entrada":"audios/O-2026-007/2026-11-15/","saida":"obras/O-2026-007/rdo/2026-11-15.md"}
{"id":"D-20261115-002","data_hora":"2026-11-15T18:20:00-03:00","tipo":"gate","projeto":"O-2026-007","skill":"rdo","nivel":"B","quem":"Eng. Fulano","entrada":"obras/O-2026-007/rdo/2026-11-15.md","saida":"obras/O-2026-007/rdo/2026-11-15.md","resultado":"corrigido","motivo":"efetivo da empreiteira de alvenaria veio somado com o da própria","aprovado_por":"Eng. Fulano","minutos_humanos":6,"minutos_antes":40}
```

## Regras
- Não grave dados pessoais desnecessários nem conteúdo sigiloso no registro: grave **onde** está, não o conteúdo inteiro.
- Decisão de nível C sem registro é tratada como não tomada.
- Quem pode ler o registro: [defina]. Quem pode gravar: todos, sempre pela skill.
