# Harness da Empresa (modelo)

Esqueleto pronto do harness de IA de um escritório de engenharia. Faça uma cópia, preencha com o padrão do seu escritório e use com a equipe pelo Claude Code (ou outro cliente que leia skills e MCP). O passo a passo está em [../receita-harness.md](../receita-harness.md).

> **Status:** v0.1, rascunho de 15/11/2026. Nenhuma skill foi testada em uso real ainda. Antes de usar com cliente, teste com material seu e registre o resultado.

## Os 4 princípios
1. **A IA prepara, o engenheiro decide e assina.** Todo processo tem um nível (A, B ou C) e um gate humano definido em `governanca/`.
2. **Nada sem registro.** Toda decisão relevante, da IA ou de uma pessoa, entra em `registro/decisoes/`. Dá pra auditar depois quem decidiu o quê, quando, com base em quê.
3. **A empresa ensina o harness.** Correções, lições e melhorias entram em `conhecimento/` e, depois de aprovadas, viram regra no `CLAUDE.md` ou numa skill. O harness fica mais parecido com a sua empresa a cada semana.
4. **Toda mudança de regra é versionada.** Mudanças no `CLAUDE.md`, nas skills e na governança passam por commit (ou pull request) no Git. O histórico do Git é a auditoria das regras.

## Estrutura

```
harness-modelo/
├── CLAUDE.md                 padrões da casa (o agente lê sempre)
├── .claude/skills/           procedimentos executáveis, um por processo
├── .mcp.json.example         conectores (copie para .mcp.json; nunca coloque senha ou token aqui)
├── dados/                    cadastro de projetos/obras, nomenclatura, onde fica cada informação
├── governanca/               níveis A/B/C, gates, política de dados
├── registro/decisoes/        trilha de auditoria (um arquivo por mês, uma linha por decisão)
├── conhecimento/             lições, padrões peculiares e propostas de melhoria
├── gabaritos/                exemplos aprovados usados para testar as skills
└── normas/                   base consultável (só normas licenciadas pela empresa)
```

## Os dois ciclos que fazem o harness funcionar

**Ciclo 1: decisão registrada (todo dia)**
```
pedido → skill executa → humano aprova, corrige ou rejeita → registrar-decisao grava em registro/decisoes/
```

**Ciclo 2: retroalimentação (toda semana ou todo mês)**
```
correções e lições acumuladas → propor-melhoria cria proposta em conhecimento/melhorias/
→ responsável aprova → regra entra no CLAUDE.md ou na skill (commit) → próximo uso já sai melhor
```

**Auditoria (quando precisar):** a skill `auditar-historico` responde perguntas como "quem aprovou o memorial da obra X?", "quantas vezes corrigimos o RDO este mês?" ou "que regra mudou depois do erro de junho?".

## Primeiros passos
1. Copie este repositório para a conta da empresa (privado).
2. Preencha o `CLAUDE.md` (seção por seção, com os dados da sua empresa).
3. Preencha `dados/cadastro.csv` e `dados/nomenclatura.md`.
4. Revise `governanca/niveis-e-gates.md` e defina quem aprova o quê.
5. Escolha 3 skills para começar. Meça o tempo de cada rotina antes de usar.
6. Rode por 2 semanas e faça a primeira rodada de `propor-melhoria`.
