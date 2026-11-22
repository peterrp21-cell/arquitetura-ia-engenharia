---
name: registrar-decisao
description: Grava uma decisão (execução de agente, aprovação/correção/rejeição humana, decisão técnica de nível C, incidente ou retificação) na trilha de auditoria em registro/decisoes/. Use no fim de toda skill, quando alguém aprovar, corrigir ou rejeitar uma saída, ou quando disserem "registra isso", "anota a decisão", "aprovei", "corrigi o RDO".
---

# Registrar decisão

Grava **uma linha** em `registro/decisoes/AAAA-MM.jsonl` (mês atual), no formato de `registro/README.md`.

## Passos
1. Identifique o tipo: `execucao`, `gate`, `decisao_humana`, `incidente` ou `retificacao`.
2. Reúna os campos obrigatórios. Se faltar `projeto`, `quem` ou (em gate) `aprovado_por`, **pergunte**; não invente.
3. Em gate `corrigido` ou `rejeitado` e em `decisao_humana`, peça o **motivo em uma frase**. É o dado mais valioso para a retroalimentação.
4. Gere o `id`: `D-AAAAMMDD-NNN`, com NNN = próximo número do dia no arquivo.
5. Use data e hora reais com fuso (rode `date` se precisar). Nunca estime.
6. **Acrescente** a linha no fim do arquivo (crie o arquivo se não existir). Nunca edite nem apague linhas existentes. Para corrigir, grave uma `retificacao` com `ref` apontando o id original.
7. Não copie conteúdo sigiloso para o registro: grave o caminho ou o link em `entrada` e `saida`.
8. Mostre a linha gravada e lembre: "faça commit para fechar o registro no histórico".

## Exemplo de pedido
"Aprovei o RDO de hoje da O-2026-007 com uma correção: o efetivo da alvenaria estava somado." → tipo `gate`, resultado `corrigido`, com o motivo.
