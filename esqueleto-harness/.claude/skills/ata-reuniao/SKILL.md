---
name: ata-reuniao
description: Transforma transcrição ou anotações de reunião (de projeto, de obra ou com cliente) em ata com decisões, pendências, responsáveis e prazos. Use para "faz a ata", "resume a reunião", "quais foram as decisões".
---

# Ata de reunião

**Nível:** A para uso interno · B se for enviada a cliente ou parceiro. **Registro:** obrigatório.

## Estrutura
1. Cabeçalho: projeto/obra (código), data, local ou link, participantes e empresas.
2. Assuntos tratados (um parágrafo curto por assunto).
3. **Decisões tomadas**: o que foi decidido e por quem.
4. **Pendências**: tabela com o quê, o responsável (nome), o prazo e o status.
5. Próxima reunião.

## Regras
- Decisão só entra como decisão se alguém decidiu na reunião. Discussão sem conclusão vai em "assuntos" e vira pendência.
- Sem responsável ou sem prazo: marque `[DEFINIR]`, não invente.
- Destaque decisões que mudam escopo, custo ou prazo: elas podem virar aditivo.

## Fechamento
1. `registrar-decisao` com tipo `execucao`.
2. Para cada **decisão técnica ou de escopo** tomada na reunião, pergunte se deve registrar também como `decisao_humana` (nível C), com quem decidiu e o motivo. É assim que a reunião entra na trilha de auditoria.
3. Se a ata for para fora da empresa, registre o gate depois da revisão.
