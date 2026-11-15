# 02. Camada de dados

IA em cima de dado bagunçado só erra mais rápido. Antes de qualquer ferramenta, a pergunta é: **como a sua operação funciona no mundo real, e onde isso está registrado?**

## Os 5 princípios

1. **Comece pelo mundo real, não pelas tabelas.** Primeiro liste as "coisas" da sua operação (obra, contrato, medição, apontamento) e só depois veja em qual sistema cada uma está. Esse é o caminho que a Palantir recomenda para modelar dados operacionais.
2. **Separe a coisa do que aconteceu com ela.** A obra é uma coisa. A medição de março é um evento sobre ela. Misturar os dois na mesma planilha é o que impede a IA de responder "o que mudou?".
3. **Um código único por coisa, usado em todo lugar.** O mesmo código da obra no orçamento, no cronograma, no RDO e no financeiro. Sem isso, nenhum cruzamento é confiável.
4. **Um lugar oficial para cada informação.** Pode haver cópias, mas só uma fonte vale. É a mesma lógica do ambiente comum de dados (CDE) da ISO 19650: em elaboração, compartilhado, publicado, arquivado.
5. **Nomes que as pessoas entendem.** "Contrato do empreiteiro de alvenaria", não "TB_CTR_047". A IA lê nomes do mesmo jeito que uma pessoa nova na equipe.

## Modelo mínimo por tipo de empresa

Não precisa de tudo no primeiro dia. Comece pelas coisas em **negrito**.

### Escritório de projetos

| Coisa | Eventos sobre ela | Onde costuma estar |
|---|---|---|
| **Empreendimento** | revisões, emissões | pasta, gestor de projetos |
| **Disciplina** e **projetista responsável** | entregas, atrasos | planilha, e-mail |
| **Apontamento de compatibilização** | aberto, respondido, resolvido, reaberto | BCF, planilha |
| Contrato e escopo | aditivos | jurídico, e-mail |
| Horas da equipe | apontamento de horas | planilha, sistema de gestão |

### Gerenciadora de obras (GDC)

Empresas que gerenciam obras para o cliente e oferecem orçamento, planejamento e operação técnica em obra.

| Coisa | Eventos sobre ela | Onde costuma estar |
|---|---|---|
| **Contrato gerenciado** (obra do cliente) | marcos, aditivos, medições aprovadas | planilha, ERP do cliente |
| **Orçamento** e **item de custo** | revisões, custo realizado, desvio | planilha, software de orçamento |
| **Cronograma de referência** | avanço medido, replanejamento | MS Project, Primavera, planilha |
| **Pendência ou não conformidade** | aberta, cobrada, encerrada | planilha, e-mail, app de campo |
| Relatório ao cliente | emissões | Word, PDF |
| Fornecedores, empreiteiros e projetistas | desempenho, prazos | planilha |

### Construtora

| Coisa | Eventos sobre ela | Onde costuma estar |
|---|---|---|
| **Obra** e **etapa ou frente** | avanço físico, RDO | cronograma, diário |
| **Orçamento** e **item de custo** | custo realizado, desvio | ERP, planilha |
| **Contrato de empreiteiro** | medições, retenções | ERP, planilha |
| Pedido de compra e material | entregas, estoque | ERP, suprimentos |
| Unidade (incorporação) | venda, distrato, repasse | CRM, comercial |

## Primeiro passo prático

Pegue **uma** obra ou projeto e preencha a tabela do seu tipo de empresa com os nomes reais dos seus sistemas e planilhas. Só esse mapa já mostra onde a informação se perde.
