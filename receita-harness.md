# Receita: o harness de IA de um escritório de engenharia

*Versão 1.0, novembro de 2026. Use, adapte e compartilhe (CC BY 4.0). O esqueleto pronto está na pasta [`esqueleto-harness/`](esqueleto-harness/).*

## O que é um harness
Em inglês, *harness* é o arreio: o que liga a força do cavalo à carroça, na direção certa. Em IA, é **tudo o que fica em volta do modelo** para ele trabalhar do seu jeito, com segurança e com controle: o seu padrão escrito, as tarefas que ele pode fazer, onde ele para e pede a sua decisão, o que fica registrado e como ele aprende com as suas correções.

O modelo de IA (ChatGPT, Claude, Gemini) é igual para todo mundo. **O harness é o que é seu.** E é ele que separa quem ganhou com IA de quem pagou caro.

## O que outros mercados pagaram para aprender, e o que adotaram depois
| Mercado | O erro | O que esse mercado adotou | Como fica na construção | Peça do harness |
|---|---|---|---|---|
| **Jurídico** (caso Avianca, EUA, 2023) | Advogados citaram jurisprudência inventada pela IA e foram multados | Vários juízes passaram a exigir que o advogado **declare que conferiu cada citação** | Norma citada se confere na norma; número que vai para a prancha sai de cálculo conferido | Regra da fonte (passo 3) |
| **Bancos** (EUA, desde 2011) | Modelos com falhas usados em decisões de risco | Todo modelo é **validado por alguém independente de quem o construiu** antes de entrar em uso (guia SR 11-7) | Testar a IA contra projetos já aprovados antes de confiar nela | Gabaritos (passo 6) |
| **Consultoria** (Deloitte Austrália, 2025) | Relatório de AU$ 440 mil com referências e citação inventadas; devolveu parte do contrato | Na versão corrigida, **declarou o uso de IA** | Registrar o que a IA fez e quem conferiu | Registro de decisões (passo 5) |
| **Atendimento** (Air Canada, 2024) | O chatbot prometeu um desconto inexistente; a empresa disse que o robô respondia por si e perdeu no tribunal | O tribunal firmou que **a empresa responde por tudo o que sai em nome dela** | Nada vai para o cliente sem uma pessoa com nome aprovar | Quem decide o quê (passo 2) |
| **Software** (estudo METR, 2025) | Desenvolvedores experientes 19% mais lentos com IA, achando que estavam mais rápidos | **Medir** em vez de confiar na sensação | Cronometrar cada rotina antes e depois | Medição (passo 7) |
| **Empresas em geral** (MIT NANDA, 2025) | 95% dos pilotos de IA generativa sem retorno, com a IA solta, fora do fluxo | Levar a IA **para dentro do processo**, aprendendo com ele | Padrão da casa escrito e rotinas virando skills | Padrão e skills (passos 1 e 4) |
| **Construção** (Autodesk e FMI) | Dado ruim respondeu por 14% de todo o retrabalho | Organizar o dado antes de automatizar | Código de projeto, nomenclatura, fonte oficial de cada informação | Dados mínimos (passo 1) |

**O ponto comum:** nenhum desses mercados resolveu trocando de IA. Todos colocaram uma estrutura em volta dela.

Fontes no fim desta página.

## Ingredientes
- Uma assinatura de IA com opção de não usar seus dados para treino (ex.: Claude Pro ou Team, ChatGPT Team).
- Uma pasta no computador (ou um repositório no GitHub, privado) para o harness.
- O esqueleto deste repositório (`esqueleto-harness/`).
- 3 rotinas repetitivas do seu escritório para começar (ex.: ler a arquitetura recebida, ata, memorial descritivo).
- 2 semanas usando de verdade.

## Modo de fazer

### Passo 1 · Escreva o padrão da casa e os dados mínimos (1 a 2 h)
Abra `CLAUDE.md` e preencha: quem vocês são, como escrevem, as regras que nunca quebram e onde fica cada informação. Depois `dados/nomenclatura.md` (código de projeto, siglas de disciplina, nome de arquivo).
**Por quê:** a IA não conhece o seu jeito. Sem isso, ela responde como para qualquer escritório do mundo.
**Dica (Anthropic):** mantenha esse arquivo curto. Procedimento vai para as skills (passo 4).

### Passo 2 · Defina quem decide o quê (30 min)
Abra `governanca/niveis-e-gates.md` e classifique cada tipo de saída em três caixas:
- **A**: a IA pode fazer sozinha (risco baixo, uso interno).
- **B**: a IA prepara, uma pessoa com nome confere antes de seguir.
- **C**: decisão do engenheiro (dimensionamento, solução técnica, ART, o que vai para o cliente).

### Passo 3 · Regra da fonte e dos dados (30 min)
Abra `governanca/politica-de-dados.md` e as [Regras de IA para quem assina projeto](regras-de-ia-para-quem-assina-projeto.md). Duas regras não se negociam: **número que vai para a prancha sai de ferramenta testada, nunca de texto da IA**, e **norma citada se confere na norma**.

### Passo 4 · Transforme 3 rotinas em skills (2 a 3 h)
Uma skill é um procedimento escrito que a IA segue sempre do mesmo jeito (pasta `.claude/skills/`). O esqueleto já traz 10: RDO, ata, relatório ao cliente, e-mail técnico, memorial descritivo, checklist de início, consulta a procedimentos, registrar decisão, propor melhoria e auditar histórico. Adapte 3 ao seu modelo.
**Dica (Anthropic):** faça uma skill quando você se pega colando o mesmo checklist no chat de novo e de novo.

### Passo 5 · Registre cada decisão (5 min por dia)
Toda vez que a IA fizer algo e você aprovar, corrigir ou rejeitar, grave uma linha em `registro/decisoes/` (a skill `registrar-decisao` faz isso). Quem, quando, com base em quê e por quê.
**Por quê:** é o que te permite responder daqui a seis meses. E a IA não lembra da conversa de ontem; o registro lembra.

### Passo 6 · Teste contra gabarito (1 h)
Guarde 3 exemplos aprovados por skill em `gabaritos/` e compare o que a IA faz com eles.
**Dica (Anthropic):** a IA tende a achar o próprio trabalho melhor do que é. Quem faz não deve ser quem avalia: compare com o gabarito, ou com outra revisão.

### Passo 7 · Meça antes e depois (durante as 2 semanas)
Cronometre cada rotina sem IA (antes) e com o harness (depois). Anote no registro. Sem número, é sensação.

### Passo 8 · Faça a IA aprender com você (15 min por semana)
Uma vez por semana, rode a skill `propor-melhoria`: ela lê as correções e propõe regras novas. Você aprova, e a regra entra no `CLAUDE.md`. A mesma correção não precisa acontecer cinco vezes.

## Quanto tempo leva
Primeira versão funcionando: **um fim de semana** (passos 1 a 4). Harness rodando com medição: **2 semanas** (passos 5 a 8).

## Erros comuns
- Começar por ferramenta cara antes de escrever o padrão.
- Deixar a IA mandar coisa para o cliente sem passar pela caixa B ou C.
- Não registrar: depois ninguém sabe o que foi conferido.
- Querer automatizar o projeto inteiro de uma vez. Comece por 3 rotinas.

## Fontes
- Jurídico, certificação de citações: [Judicature/Duke](https://judicature.duke.edu/wp-content/uploads/sites/3/2023/10/AIOrders_Vol107No2.pdf) · [Law360](https://www.law360.com/pulse/articles/2357542)
- Bancos, validação independente: [Federal Reserve, SR 11-7](https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm)
- Avianca: [Legal Dive](https://www.legaldive.com/news/lawyer-fake-chatgpt-cases-sanctions-fines-lawyers-chatgpt-fake-cases/653741/)
- Air Canada: [American Bar Association](https://www.americanbar.org/groups/business_law/resources/business-law-today/2024-february/bc-tribunal-confirms-companies-remain-liable-information-provided-ai-chatbot/)
- Deloitte Austrália: [AP via CTV News](https://www.ctvnews.ca/business/article/deloitte-to-partially-refund-australian-government-for-report-with-apparent-ai-generated-errors/) · [Fortune](https://fortune.com/2025/10/07/deloitte-ai-australia-government-report-hallucinations-technology-290000-refund/)
- METR: [getDX](https://getdx.com/blog/metr-study-on-how-ai-affects-developer-productivity/)
- MIT NANDA: [Fortune via Yahoo](https://finance.yahoo.com/news/mit-report-95-generative-ai-105412686.html)
- Autodesk e FMI: [ForConstructionPros](https://www.forconstructionpros.com/profit-matters/press-release/21747405/autodesk-construction-solutions-autodesk-and-fmi-study-says-better-data-strategies-could-save-global-construction-185t)
- Anthropic, harness e skills: [harnesses para agentes longos](https://anthropic.com/engineering/effective-harnesses-for-long-running-agents) · [design de harness](https://anthropic.com/engineering/harness-design-long-running-apps) · [Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) · [boas práticas de skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices)
