
# Ambiente de desenvolvimento

## Objetivo

Documentar a preparação do ambiente necessário para desenvolver e validar o krameldocs.

## Pré-requisitos

Antes de começar, tenha:

- Node.js em uma versão compatível com o projeto.
- npm.
- Git.
- Acesso ao repositório da aplicação.
- Acesso ao repositório de conteúdo, quando necessário.
- Um editor de código de sua preferência.

Consulte os arquivos de configuração do projeto para confirmar a versão recomendada do Node.js e as versões das dependências.

## Repositórios

O projeto utiliza dois repositórios independentes:

- Aplicação: `kramelworks-admin/krameldocs`
- Conteúdo: `kramelworks/krameldocs-content`

Clone o repositório da aplicação para trabalhar no código. O repositório de conteúdo é utilizado para editar os documentos e recursos publicados.

## Instalação

Na pasta da aplicação, execute:

```bash
npm install
```

A instalação deve utilizar as dependências declaradas pelo projeto.

## Configuração local

Crie o arquivo `.env.local` na raiz da aplicação, se necessário.

Exemplo:

```dotenv
DOCS_GIT_REPOSITORY=kramelworks/krameldocs-content
DOCS_GIT_BRANCH=main
DOCS_GIT_PATH=
DOCS_CACHE_TTL=60
GITHUB_TOKEN=seu_token_aqui
```

O token é ilustrativo. Configure o valor real somente no ambiente local e não o publique no Git.

## Executar a aplicação

Inicie o servidor de desenvolvimento:

```bash
npm run dev
```

Acesse o endereço local informado pelo terminal.

Teste a página inicial, `/docs`, um documento interno e os recursos associados.

## Verificações de qualidade

Antes de concluir uma alteração, execute os comandos disponíveis no projeto:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Se um comando falhar, investigue a causa e corrija o problema antes de publicar.

## Atualização do ambiente

Ao atualizar o código:

1. Confira o estado do Git.
2. Obtenha as alterações mais recentes.
3. Instale as dependências necessárias.
4. Revise as alterações que afetam sua tarefa.
5. Execute os testes relevantes.

Evite descartar alterações locais sem antes verificar se precisam ser preservadas.

## Boas práticas

- Mantenha o ambiente local separado da produção.
- Não versione segredos.
- Faça alterações pequenas e fáceis de revisar.
- Prefira commits com uma finalidade clara.
- Atualize a documentação quando o comportamento mudar.
