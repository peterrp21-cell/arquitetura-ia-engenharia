---
name: rdo
description: Monta o Relatório Diário de Obra (RDO) a partir de áudios transcritos, mensagens, anotações e fotos do dia. Use quando disserem "faz o RDO", "diário de obra de hoje", "monta o RDO com esses áudios".
---

# RDO

**Nível:** B (o engenheiro da obra aprova). **Registro:** obrigatório.

## Antes de começar
Confirme o código da obra (`dados/cadastro.csv`) e a data. Se o CLAUDE.md não definir o modelo de RDO da empresa, pergunte numa única mensagem: campos do modelo, fase da obra, empreiteiras ativas e quem vai ler (equipe, cliente ou fiscalização).

## Monte com estas seções
1. Condições do tempo (manhã e tarde) e se houve impedimento.
2. Efetivo: próprio e terceirizado, por função e por empresa, com quantidades. Não some empresas diferentes.
3. Serviços executados, por frente ou pavimento, com o avanço informado.
4. Equipamentos utilizados.
5. Materiais recebidos.
6. Ocorrências, problemas e pendências, com responsável quando citado.
7. Visitas e orientações recebidas.

## Regras
- Use só o material. Faltou: `[NÃO INFORMADO]`.
- Não calcule avanço percentual que não foi informado.
- No fim, liste as perguntas a fazer ao encarregado.
- Salve em `[pasta oficial da obra]/rdo/AAAA-MM-DD.md` (ou onde o CLAUDE.md indicar).

## Fechamento
1. Chame `registrar-decisao` com tipo `execucao`.
2. Peça ao engenheiro a revisão. Quando ele responder, registre o `gate` (aprovado / corrigido / rejeitado, com motivo e minutos gastos).
