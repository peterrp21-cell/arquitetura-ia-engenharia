# [Nome da empresa]: padrões da casa

Este arquivo é lido pelo agente em toda conversa. Escreva como você explicaria a empresa a um engenheiro novo no primeiro dia. Troque tudo que está entre colchetes.

## Quem somos
- Tipo: [escritório de projeto / gerenciadora de obras (GDC) / construtora]
- Disciplinas ou serviços: [ex.: hidrossanitário e elétrico; gerenciamento de obras residenciais]
- Tamanho da equipe: [n pessoas]
- Clientes típicos: [ex.: incorporadoras de médio porte, residencial vertical]

## Como escrevemos
- Idioma: português do Brasil, tom técnico e direto.
- Unidades no SI, vírgula decimal, datas DD/MM/AAAA.
- [Regras próprias: ex.: "nunca usar 'aproximadamente' em memorial"; "sempre citar a norma com o ano"]

## Regras que nunca quebram
1. **Número que vai para cliente, prancha, memorial ou contrato não sai de texto da IA.** Sai de planilha, software de cálculo ou dado registrado. Se não tiver a fonte, escreva [VERIFICAR].
2. **Use só o material fornecido.** Onde faltar informação, escreva [NÃO INFORMADO] e liste as perguntas no fim.
3. **Nada é enviado ao cliente sem aprovação** de quem está definido em `governanca/niveis-e-gates.md`.
4. **Dados de cliente seguem `governanca/politica-de-dados.md`.**
5. **Toda saída de skill termina com o registro da decisão** (skill `registrar-decisao`).

## Onde fica cada informação
| Informação | Fonte oficial | Dono |
|---|---|---|
| Cadastro de projetos/obras | `dados/cadastro.csv` | [nome/cargo] |
| Projetos e modelos | [ex.: Drive > Projetos > CÓDIGO] | [ ] |
| Cronogramas | [ex.: MS Project / ClickUp] | [ ] |
| Contratos | [ ] | [ ] |
| Normas | `normas/` (licenciadas) | [ ] |

## Nomenclatura
Ver `dados/nomenclatura.md`. Use sempre o código do projeto/obra (ex.: `P-2026-014`) em nomes de arquivo, e-mail e registro.

## Conhecimento da empresa (atualizado pela retroalimentação)
*Esta seção cresce com o uso. Cada item entra por uma proposta aprovada em `conhecimento/melhorias/`. Indique sempre a origem.*

- [ex.: "Cliente Incorporadora A não aceita PVC soldável em prumada. Origem: melhoria M-003, aprovada em 20/01/2027."]
