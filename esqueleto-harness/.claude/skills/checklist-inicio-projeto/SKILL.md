---
name: checklist-inicio-projeto
description: Abre um projeto ou obra novo no padrão da empresa, cadastra o código, confere os insumos de início e lista o que falta pedir ao cliente. Use para "abre o projeto", "novo projeto", "começamos a obra X", "o que falta para começar".
---

# Checklist de início

**Nível:** B. **Registro:** obrigatório.

## Passos
1. Gere o próximo código em `dados/cadastro.csv` (`P-AAAA-NNN` ou `O-AAAA-NNN`) e proponha a linha. Só grave depois de confirmado.
2. Confira os insumos (adapte a lista no CLAUDE.md):
   - contrato assinado e entrada paga;
   - arquitetura na revisão vigente (com data);
   - aprovação no condomínio/prefeitura, se houver;
   - sondagem e planialtimétrico (quando aplicável);
   - ART da arquitetura;
   - matrícula do imóvel;
   - critérios e padrões do cliente.
3. Monte uma tabela: insumo · recebido? · onde está · observação.
4. Redija o e-mail ao cliente pedindo o que falta (use a skill `email-tecnico`).

## Fechamento
`registrar-decisao` (execucao, projeto = novo código). Ao confirmar o cadastro, registre o gate.
