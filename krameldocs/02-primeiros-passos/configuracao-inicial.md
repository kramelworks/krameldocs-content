
# Configuração inicial

O krameldocs utiliza variáveis de ambiente para definir de onde o conteúdo será carregado e como ele será acessado.

Essas configurações devem ser definidas tanto no ambiente local quanto no ambiente de produção.

## Variáveis necessárias

O exemplo abaixo apresenta os nomes das variáveis e os valores de referência utilizados neste projeto.

```dotenv
DOCS_GIT_REPOSITORY=kramelworks/krameldocs-content
DOCS_GIT_BRANCH=main
DOCS_GIT_PATH=
DOCS_CACHE_TTL=60
GITHUB_TOKEN=
```

O campo `GITHUB_TOKEN` está vazio intencionalmente. Não copie tokens reais para arquivos versionados ou para esta documentação.

## Descrição das variáveis

### `DOCS_GIT_REPOSITORY`

Identifica o repositório GitHub de conteúdo.

Formato esperado:

`organização/nome-do-repositório`

Valor de referência:

`kramelworks/krameldocs-content`

### `DOCS_GIT_BRANCH`

Define a branch que contém o conteúdo consultado pela aplicação.

Valor de referência:

`main`

O nome configurado deve corresponder a uma branch existente no repositório.

### `DOCS_GIT_PATH`

Define opcionalmente uma pasta-base para os arquivos de conteúdo.

Quando estiver vazio, a raiz do repositório será utilizada como base.

Se essa variável for preenchida, confirme como a versão atual da aplicação resolve os caminhos de documentos e assets antes de alterar a estrutura do repositório.

### `DOCS_CACHE_TTL`

Define o tempo de validade do cache em segundos.

Valor de referência:

`60`

Esse valor corresponde a 60 segundos. A atualização visível do conteúdo também depende do comportamento do cache e da implantação.

### `GITHUB_TOKEN`

Credencial utilizada no servidor para autenticar as requisições ao GitHub quando necessário.

Para repositórios privados, o token precisa ter as permissões de leitura apropriadas.

O token deve permanecer exclusivamente no ambiente do servidor.

## Configuração local

1. Abra a pasta do projeto.
2. Crie ou edite o arquivo `.env.local`.
3. Defina as variáveis necessárias.
4. Salve o arquivo.
5. Reinicie o servidor de desenvolvimento para que as alterações sejam carregadas.

Não publique o arquivo `.env.local` no repositório.

## Configuração na Vercel

No projeto da Vercel:

1. Abra as configurações do projeto.
2. Entre na seção de variáveis de ambiente.
3. Cadastre cada variável necessária.
4. Confira se os valores correspondem ao repositório e à branch desejados.
5. Configure `GITHUB_TOKEN` como segredo de servidor.
6. Faça um novo deploy quando necessário para aplicar as alterações.

Não utilize o prefixo `NEXT_PUBLIC_` no token.

## Verificação

Depois de configurar as variáveis:

- Confirme que o repositório está correto.
- Confirme que a branch existe.
- Verifique se a aplicação consegue carregar `navigation.json`.
- Abra um documento listado na navegação.
- Verifique se os assets compatíveis são carregados.
- Consulte os logs do servidor caso ocorram erros de acesso.

## Cuidados

Não coloque tokens em logs, mensagens de erro públicas, commits ou arquivos Markdown.

Se um token for exposto acidentalmente, revogue-o e gere uma nova credencial.

## Próximo passo

Consulte [Primeira execução](primeira-execucao.md) para validar a aplicação após a configuração.
