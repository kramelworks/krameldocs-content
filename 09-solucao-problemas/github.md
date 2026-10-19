
# Problemas de integração com o GitHub

## Objetivo

Ajudar a identificar falhas na leitura de documentos e recursos armazenados no GitHub.

## Sintomas comuns

- Documentos não carregam.
- O portal apresenta erro ao consultar o conteúdo.
- A navegação não corresponde aos arquivos publicados.
- Recursos retornam erro ou não aparecem.
- Alterações recentes ainda não estão visíveis.

## Verificar o repositório

Confirme a variável `DOCS_GIT_REPOSITORY` e verifique se o repositório existe.

O valor deve corresponder à fonte de conteúdo pretendida.

## Verificar a branch

Confira `DOCS_GIT_BRANCH`.

Confirme que a branch existe e contém os arquivos esperados, incluindo `navigation.json` e os documentos referenciados.

## Verificar o diretório-base

Confira `DOCS_GIT_PATH`.

Um diretório-base incorreto pode fazer com que a aplicação procure os arquivos em uma localização diferente da esperada.

## Repositório privado

Se o repositório for privado, verifique:

1. Se `GITHUB_TOKEN` está configurado no servidor.
2. Se o token está válido.
3. Se o tipo de token utilizado possui as permissões necessárias.
4. Se o token tem acesso ao repositório.
5. Se a configuração está disponível no ambiente correto.

Nunca registre ou compartilhe o valor do token.

## Mudanças não aparecem

Se o conteúdo antigo continuar sendo exibido:

1. Confirme que o commit foi publicado.
2. Verifique a branch consultada pela aplicação.
3. Confirme o caminho do documento.
4. Considere o intervalo de cache configurado.
5. Consulte os logs caso a falha persista.

## Erros de acesso

Se a origem recusar uma solicitação, verifique as permissões e as condições de acesso antes de modificar o código.

Não presuma que toda falha é causada pelo token: a branch, o caminho, a conectividade e a disponibilidade do serviço também podem influenciar o resultado.

## Diagnóstico com logs

Utilize os logs da aplicação para identificar a etapa que falhou.

Mensagens de diagnóstico devem evitar expor credenciais ou conteúdo privado desnecessário.

## Escalonamento

Se o problema persistir:

- Registre a rota afetada.
- Anote o horário da falha.
- Descreva o comportamento observado.
- Reúna mensagens de erro sem segredos.
- Identifique as últimas alterações realizadas.
