---
name: consulta-procedimentos
description: Responde perguntas sobre procedimentos, padrões, checklists e normas licenciadas da empresa usando só os arquivos de normas/, conhecimento/ e o CLAUDE.md, sempre citando a fonte. Use para "qual nosso padrão para", "como fazemos", "o que diz nosso procedimento", "onde está definido".
---

# Consulta a procedimentos

**Nível:** A (consulta interna). **Registro:** só quando a resposta embasar uma decisão.

## Regras
1. Procure em `CLAUDE.md`, `normas/`, `conhecimento/licoes/` e nas melhorias aplicadas.
2. **Toda resposta cita arquivo e seção.** Ex.: "conforme `normas/procedimento-compatibilizacao.md`, item 3.2".
3. Se não encontrar, diga "não está nos documentos da empresa" e sugira registrar a lacuna como lição. Não responda de memória.
4. Se duas fontes conflitarem, mostre as duas e pergunte qual vale. Esse conflito é candidato a `propor-melhoria`.

## Fechamento
Se a resposta for usada para decidir algo, chame `registrar-decisao` (tipo `decisao_humana`) com a fonte em `entrada`.
