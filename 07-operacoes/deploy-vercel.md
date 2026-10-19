
# Deploy na Vercel

## Objetivo

Documentar o fluxo de implantação do krameldocs na Vercel.

## Pré-requisitos

Antes de iniciar, confirme:

- O código da aplicação está no GitHub.
- O projeto está conectado à Vercel.
- As variáveis de ambiente necessárias foram configuradas.
- O repositório de conteúdo está acessível à aplicação.
- O build local foi executado com sucesso.

## Importar o projeto

Se o projeto ainda não estiver conectado:

1. Acesse a Vercel.
2. Importe o repositório da aplicação.
3. Confira as configurações de build detectadas.
4. Configure as variáveis de ambiente.
5. Inicie a implantação.

Utilize o repositório da aplicação, e não o repositório que contém apenas os documentos.

## Variáveis de ambiente

Confira a configuração das seguintes variáveis, conforme aplicável:

```text
DOCS_GIT_REPOSITORY
DOCS_GIT_BRANCH
DOCS_GIT_PATH
DOCS_CACHE_TTL
GITHUB_TOKEN
```

O token deve ser cadastrado como segredo no ambiente de hospedagem, sem prefixo `NEXT_PUBLIC_`.

## Build

A Vercel executa o processo de build configurado para o projeto.

Se o deploy falhar:

1. Abra os logs da implantação.
2. Identifique a etapa que apresentou erro.
3. Reproduza o problema localmente, quando possível.
4. Corrija o código ou a configuração.
5. Execute os testes e tente novamente.

## Verificação após o deploy

Após a implantação:

1. Abra a URL fornecida pela Vercel.
2. Confirme que a página inicial carrega.
3. Acesse `/docs`.
4. Abra um documento interno.
5. Teste imagens e PDFs.
6. Verifique a navegação entre documentos.
7. Confira os logs em caso de falha.

## Novos deploys

Alterações no código da aplicação podem iniciar novos deploys conforme as configurações de integração com o Git.

Alterações no repositório de conteúdo são independentes do repositório da aplicação. A atualização visível depende do cache e da forma como o conteúdo é consultado.

## Falhas de implantação

### Build com erro

Consulte os logs para identificar problemas de compilação, tipagem, dependências ou configuração.

### Portal abre, mas os documentos não carregam

Confira as variáveis de ambiente, as permissões de acesso ao GitHub e a estrutura do repositório de conteúdo.

### Imagens ou PDFs não aparecem

Verifique os caminhos utilizados no Markdown e as restrições da rota de arquivos.

## Manutenção

Após mudanças importantes na infraestrutura, revise este procedimento e mantenha os nomes das configurações coerentes com o projeto atual.
