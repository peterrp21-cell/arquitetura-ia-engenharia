---
name: memorial-descritivo
description: Monta ou revisa memorial descritivo de projeto a partir dos critérios, do padrão da empresa e das informações do projeto, sem inventar dado técnico. Use para "faz o memorial", "revisa o memorial", "confere o memorial contra o projeto".
---

# Memorial descritivo

**Nível:** B (o responsável técnico aprova). **Registro:** obrigatório.

## Modo montar
1. Peça: disciplina, código do projeto, critérios adotados, normas (com ano), materiais e sistemas definidos, e o modelo de memorial da empresa.
2. Monte seguindo o modelo. Todo valor técnico (diâmetro, carga, vazão, potência) vem do material fornecido, com a fonte indicada. Sem fonte: `[VERIFICAR]`.
3. Liste no fim: premissas assumidas e itens `[VERIFICAR]`.

## Modo revisar
Compare o memorial com o material do projeto e aponte, numa tabela: inconsistências, normas sem ano ou desatualizadas, itens sem fonte, termos vagos ("aproximadamente", "a critério"), divergências com as pranchas citadas.

## Regras
- A IA não calcula para o memorial. Ela organiza e verifica coerência.
- Não cite norma que não está no material ou em `normas/`.

## Fechamento
`registrar-decisao` (execucao) e o gate do RT, com motivo de cada correção. Correções de norma ou de critério são boas candidatas a `propor-melhoria`.
