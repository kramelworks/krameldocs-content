
# Problemas de configuração

## Objetivo

Orientar o diagnóstico de problemas relacionados à configuração do krameldocs.

## O portal não carrega os documentos

Confira estas variáveis:

```dotenv
DOCS_GIT_REPOSITORY=kramelworks/krameldocs-content
DOCS_GIT_BRANCH=main
DOCS_GIT_PATH=
DOCS_CACHE_TTL=60
```

Verifique se os valores correspondem ao repositório e à estrutura de conteúdo esperados.

Se o repositório for privado, confirme também a configuração de `GITHUB_TOKEN`.

## Repositório incorreto

A variável `DOCS_GIT_REPOSITORY` deve identificar o proprietário e o nome do repositório.

Exemplo:

```text
kramelworks/krameldocs-content
```

Confirme que o valor não contém uma URL completa quando a implementação espera somente `proprietario/repositorio`.

## Branch inexistente

Verifique se a branch configurada em `DOCS_GIT_BRANCH` existe e contém os documentos esperados.

## Diretório-base incorreto

Se `DOCS_GIT_PATH` estiver preenchido, confirme que os arquivos estão organizados dentro desse diretório.

Quando a variável estiver vazia, a raiz do repositório é utilizada como diretório-base.

## Token ausente ou inválido

Se o acesso depender de autenticação:

1. Confira se `GITHUB_TOKEN` está configurado.
2. Verifique se o token continua válido.
3. Confirme as permissões de leitura necessárias.
4. Verifique se ele tem acesso ao repositório correto.

Não compartilhe o token durante o diagnóstico.

## Configuração local versus produção

Se funcionar localmente, mas falhar na Vercel, compare os nomes e valores das variáveis, sem copiar segredos para mensagens ou arquivos públicos.

Verifique também se as variáveis foram associadas ao ambiente de implantação correto.

## Alterações não aplicadas

Depois de modificar variáveis de ambiente, confirme se a aplicação precisa de reinicialização ou de um novo deploy para utilizar os novos valores.

## Procedimento geral

1. Reproduza o problema.
2. Identifique a rota afetada.
3. Confira a configuração.
4. Consulte os logs.
5. Corrija uma causa por vez.
6. Teste novamente o comportamento afetado.
7. Registre a solução se o problema puder se repetir.
