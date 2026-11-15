# 04. Camada de governança

Governança não é burocracia. É o que permite a IA trabalhar de verdade, porque deixa claro quem responde por cada resultado. A estrutura abaixo segue a lógica do framework de gestão de risco de IA do NIST (governar, mapear, medir, gerenciar), adaptada à engenharia.

## 1. Governar: quem decide

- **Quem assina, decide.** Nada gerado por IA vai para cliente, contrato, projeto emitido ou ART sem revisão do responsável técnico.
- **Um dono do tema.** Uma pessoa com tempo reservado para cuidar dos usos de IA, mesmo que seja meio período.
- **Ferramentas aprovadas.** Uma lista curta do que pode ser usado, para que cada um não use a sua.

## 2. Mapear: onde a IA entra e o que pode fazer

Para cada uso de IA, preencha uma linha:

| Uso | O que a IA faz | O que a IA não faz | Quem revisa | Dados que pode receber |
|---|---|---|---|---|
| RDO | Organiza notas e áudios | Não inventa efetivo nem avanço | Engenheiro residente | Notas da obra, sem dados pessoais |
| Triagem de apontamentos | Classifica e sugere responsável | Não altera o projeto | Coordenador BIM | Lista de apontamentos |

**Três classes de dado:** livre (pode ir para qualquer IA aprovada), interno (só ferramentas com contrato e sem treino nos seus dados) e restrito (dados pessoais, valores de contrato, informação de cliente sob sigilo, que exigem aprovação caso a caso).

## 3. Medir: ganho de verdade, não de sensação

Num estudo de 2025, desenvolvedores experientes ficaram 19% mais lentos usando IA, enquanto achavam que estavam mais rápidos. Por isso:

- Meça **antes e depois** o tempo da tarefa escolhida, em pelo menos 5 repetições.
- Conte os **erros encontrados na revisão**. Se a revisão demora mais que fazer do zero, o uso não está pronto.
- Registre **qual prompt ou agente** gerou cada resultado, para saber o que melhorar.

## 4. Gerenciar: revisar e ajustar

- Revisão mensal de cada uso: manter, ajustar ou parar.
- Exigir **fonte rastreável** sempre que a IA citar norma, valor ou dado. No jurídico americano, advogados foram multados por protocolar jurisprudência inventada por IA (caso Avianca, 2023).
- Evoluir aos poucos: proteger o que já funciona e estender por partes, sem reformular tudo de uma vez.

Para empresas que queiram formalizar, a ISO/IEC 42001 trata de sistemas de gestão de IA.
