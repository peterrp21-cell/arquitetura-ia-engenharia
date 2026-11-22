# Política de uso de IA e dados (1 página)

Adapte e peça para cada pessoa da equipe ler e concordar.

## Ferramentas aprovadas
- [ex.: Claude (plano Team/Enterprise), com retenção de dados configurada pela empresa]
- Qualquer outra ferramenta precisa de aprovação de [responsável].

## Pode enviar para a IA aprovada
- Projetos, modelos, memoriais e documentos técnicos dos projetos em andamento.
- Dados de obra (RDO, fotos, cronograma) sem dados pessoais desnecessários.

## Não pode enviar
- Senhas, tokens, chaves de API, dados bancários.
- Documentos pessoais de funcionários e clientes (CPF, RG, endereço residencial).
- Material que o contrato do cliente proíbe compartilhar (confira a cláusula de confidencialidade).
- Normas ABNT fora da licença que a empresa possui.

## Regras
1. Segredo nunca entra no repositório. Credenciais ficam nas variáveis de ambiente de cada máquina.
2. O repositório é privado e o acesso é revisado a cada [trimestre].
3. Toda saída que vai para fora da empresa passa pelo gate (`niveis-e-gates.md`).
4. Vazamento ou erro grave: avisar [responsável] no mesmo dia e registrar em `registro/decisoes/` com o tipo `incidente`.
