
# Pré-requisitos

Este documento descreve os requisitos necessários para utilizar e desenvolver o krameldocs.

## Para consultar a documentação

Para acessar o portal, é necessário:

- Um navegador moderno.
- Conectividade com a URL publicada.
- Uma implantação funcional da aplicação.
- Acesso ao conteúdo disponibilizado pelo portal.

Não é necessário instalar Node.js ou clonar os repositórios para apenas consultar a documentação publicada.

## Para desenvolver a aplicação

O ambiente de desenvolvimento precisa ter:

- Git.
- Node.js compatível com a versão exigida pelo projeto.
- npm.
- Acesso ao repositório da aplicação.
- Permissão para instalar as dependências do projeto.
- Um editor de código de sua preferência.

Consulte o arquivo `package.json` e a documentação do projeto para confirmar as versões exigidas pelas ferramentas.

## Para acessar o repositório de conteúdo

É necessário ter acesso de leitura ao repositório:

`kramelworks/krameldocs-content`

Se o repositório for privado, a aplicação precisará de uma credencial válida no servidor para consultar os arquivos.

## Verificar as ferramentas instaladas

Execute os comandos abaixo no terminal:

```bash
node --version
npm --version
git --version
```

Os comandos devem exibir as versões instaladas.

Se algum deles não for reconhecido, instale ou configure a ferramenta correspondente antes de continuar.

## Segurança das credenciais

Nunca inclua tokens de acesso em arquivos Markdown, no `navigation.json`, no código público ou em commits.

Para desenvolvimento local, utilize `.env.local`. Para produção, configure as variáveis de ambiente na plataforma de hospedagem.

## Próximo passo

Após verificar os requisitos, siga o guia de [Instalação local](instalacao-local.md).
