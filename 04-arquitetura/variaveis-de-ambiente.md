
# Variáveis de ambiente

## Visão geral

As variáveis de ambiente configuram a origem do conteúdo, a branch utilizada, o diretório-base e o comportamento do cache.

Os valores devem ser configurados tanto no ambiente local quanto no ambiente de implantação, conforme a necessidade.

## Variáveis disponíveis

| Variável | Finalidade | Exemplo |
|---|---|---|
| `DOCS_GIT_REPOSITORY` | Identifica o repositório GitHub que contém a documentação. | `kramelworks/krameldocs-content` |
| `DOCS_GIT_BRANCH` | Define a branch de conteúdo utilizada. | `main` |
| `DOCS_GIT_PATH` | Define o diretório-base dos documentos dentro do repositório. | Vazio para a raiz |
| `DOCS_CACHE_TTL` | Configura o intervalo de cache em segundos. | `60` |
| `GITHUB_TOKEN` | Token usado pelo servidor para acessar o GitHub quando necessário. | Valor secreto |

## Exemplo de configuração

Crie ou atualize o arquivo `.env.local` na raiz do projeto da aplicação:

```dotenv
DOCS_GIT_REPOSITORY=kramelworks/krameldocs-content
DOCS_GIT_BRANCH=main
DOCS_GIT_PATH=
DOCS_CACHE_TTL=60
GITHUB_TOKEN=seu_token_aqui
```

Substitua o valor ilustrativo de `GITHUB_TOKEN` pelo token apropriado no ambiente local. Não publique o token em arquivos versionados.

## DOCS_GIT_REPOSITORY

Identifica o repositório GitHub usado como fonte de conteúdo.

O valor esperado segue o formato:

```text
proprietario/repositorio
```

Exemplo:

```text
kramelworks/krameldocs-content
```

## DOCS_GIT_BRANCH

Define a branch da qual o conteúdo será obtido.

No projeto atual, o valor utilizado é `main`. Se outra branch for configurada, confirme que ela contém a estrutura de navegação e os documentos esperados.

## DOCS_GIT_PATH

Define um diretório-base opcional dentro do repositório de conteúdo.

Quando estiver vazio, a raiz do repositório será utilizada.

Se for preenchido, confirme que os arquivos de navegação, os documentos e os recursos estão organizados de acordo com o comportamento esperado pelo provedor de conteúdo.

## DOCS_CACHE_TTL

Define o intervalo de cache em segundos.

O valor configurado no ambiente é `60`. Alterar essa variável pode afetar a frequência com que o conteúdo é consultado novamente.

O efeito exato depende da estratégia de cache implementada e do ambiente de execução.

## GITHUB_TOKEN

Contém o token de autenticação utilizado pelo servidor para acessar o GitHub quando necessário.

Regras importantes:

- Não usar o prefixo `NEXT_PUBLIC_`.
- Não incluir o token em arquivos Markdown do repositório de conteúdo.
- Não fazer commit de `.env.local`.
- Não registrar o token em logs.
- Não compartilhar o valor do token em mensagens ou capturas de tela.
- Utilizar somente as permissões necessárias para o repositório.

Se o token for exposto acidentalmente, revogue-o e configure um novo.

## Configuração na Vercel

No projeto da aplicação:

1. Abra as configurações do projeto na Vercel.
2. Acesse as variáveis de ambiente.
3. Cadastre as variáveis necessárias.
4. Confira os ambientes aos quais cada variável se aplica.
5. Faça um novo deploy quando uma alteração exigir a reconstrução ou reinicialização da aplicação.

Nunca inclua valores secretos em documentação pública.

## Diagnóstico

Se o portal não conseguir carregar o conteúdo:

1. Confira o nome e o formato do repositório.
2. Verifique se a branch configurada existe.
3. Confirme o valor de `DOCS_GIT_PATH`.
4. Verifique se o token está presente quando necessário.
5. Confira as permissões do token e a visibilidade do repositório.
6. Consulte os logs do ambiente de execução sem expor segredos.
