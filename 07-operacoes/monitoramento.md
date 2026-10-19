
# Monitoramento

## Objetivo

Definir verificações operacionais para acompanhar a disponibilidade e o funcionamento do krameldocs.

## O que verificar

O monitoramento deve ajudar a identificar:

- Indisponibilidade do portal.
- Falhas no carregamento de documentos.
- Problemas de acesso ao GitHub.
- Erros na entrega de imagens e anexos.
- Falhas de build e implantação.
- Configurações de ambiente incorretas.

## Verificação manual

Após uma implantação, verifique:

1. A página inicial.
2. A rota `/docs`.
3. Um documento em um subdiretório.
4. Uma imagem do conteúdo.
5. Um arquivo PDF.
6. A navegação entre documentos.

Esses testes ajudam a identificar falhas que não são necessariamente detectadas pelo processo de build.

## Logs da aplicação

Quando ocorrer um erro:

1. Abra os logs de execução ou implantação na Vercel.
2. Identifique a rota e o horário do problema.
3. Verifique as mensagens relacionadas à solicitação.
4. Compare com alterações recentes.
5. Evite registrar ou compartilhar tokens e outros segredos.

## Dependências externas

O funcionamento do portal pode depender da disponibilidade do GitHub e das permissões da credencial configurada.

Ao investigar uma falha, diferencie problemas da aplicação de problemas de acesso à origem.

## Alertas

Se forem configurados serviços de monitoramento ou alertas, defina condições que ajudem a detectar falhas relevantes sem gerar notificações excessivas.

Registre o procedimento utilizado para receber, analisar e resolver os alertas.

## Histórico de incidentes

Para incidentes importantes, registre:

- Data e horário.
- Sintoma observado.
- Impacto para os usuários.
- Causa identificada, quando conhecida.
- Solução aplicada.
- Ação preventiva recomendada.

## Evolução do monitoramento

Ajuste os procedimentos conforme o uso do portal aumentar. Não declare a existência de monitoramento automático ou alertas até que esses recursos estejam efetivamente configurados.
