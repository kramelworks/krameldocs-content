
# Conceitos principais

Este documento apresenta os conceitos necessários para compreender a arquitetura e a operação do krameldocs.

## Aplicação

É o projeto Next.js responsável por receber as requisições, carregar o conteúdo, renderizar os documentos e apresentar a interface de navegação.

O código-fonte da aplicação fica no repositório `kramelworks-admin/krameldocs`.

## Repositório de conteúdo

É o repositório GitHub que armazena os artigos Markdown, o arquivo `navigation.json` e os recursos utilizados nos documentos.

O repositório configurado para este projeto é `kramelworks/krameldocs-content`.

## Sistema documentado

Representa um produto, serviço ou aplicação cuja documentação está disponível no portal.

Cada sistema deve ter uma área própria na navegação e uma estrutura de arquivos organizada. Isso permite adicionar novos sistemas sem misturar seus documentos.

## Documento Markdown

É um arquivo de texto com extensão `.md`, escrito utilizando a sintaxe Markdown.

Os documentos podem conter títulos, parágrafos, listas, tabelas, links, blocos de código e referências a recursos compatíveis.

## Navegação

É a estrutura que organiza os documentos no menu do portal.

A navegação é declarada em `navigation.json`, por meio de grupos e páginas. Os grupos contêm outros itens; as páginas apontam para arquivos Markdown.

## Caminho do documento

É o caminho relativo de um arquivo Markdown dentro da raiz de conteúdo configurada.

Exemplo:

`krameldocs/01-visao-geral/apresentacao.md`

Esse caminho é utilizado na configuração da navegação e serve de base para a resolução da página correspondente.

## Asset

É um arquivo complementar utilizado por um documento, como uma imagem, um PDF ou outro formato permitido pela aplicação.

Os assets podem ser organizados em uma pasta compartilhada, como `assets/`.

## Git e versionamento

Git é o sistema de controle de versão utilizado para registrar alterações no código e no conteúdo.

Cada commit registra um conjunto de mudanças. O histórico facilita a revisão, a auditoria e a recuperação de versões anteriores.

## Branch

Uma branch é uma linha de desenvolvimento dentro de um repositório Git.

A aplicação utiliza a branch definida na variável `DOCS_GIT_BRANCH` para consultar o conteúdo.

## GitHub Contents API

É a interface de programação do GitHub utilizada pela aplicação para consultar arquivos do repositório configurado.

Quando o repositório é privado, as consultas autenticadas dependem de uma credencial válida mantida no servidor.

## Variável de ambiente

É uma configuração fornecida ao processo da aplicação sem precisar inserir o valor diretamente no código-fonte.

As variáveis definem, por exemplo, o repositório de conteúdo, a branch, o diretório-base e o tempo de cache.

## Cache

É um mecanismo de armazenamento temporário que permite reutilizar dados já consultados.

O cache reduz chamadas repetidas ao GitHub, mas pode fazer com que alterações recentes demorem algum tempo para aparecer.

## TTL

Sigla de *Time To Live*, ou tempo de vida. Indica por quanto tempo uma entrada de cache pode ser considerada válida.

No krameldocs, o tempo de cache é configurado por `DOCS_CACHE_TTL`.

## Renderização Markdown

É o processo que converte o texto Markdown em conteúdo HTML para apresentação no navegador.

O pipeline pode incluir processamento de extensões Markdown, realce de código, transformação de links e sanitização da saída.

## Sanitização

É o tratamento do HTML produzido pelo processamento do documento para restringir elementos e atributos potencialmente inseguros.

A sanitização faz parte das medidas de segurança, mas não substitui a validação de entradas nem outras proteções da aplicação.

## Deploy

É o processo de disponibilizar uma versão da aplicação em um ambiente de hospedagem, como a Vercel.

A publicação da aplicação e a publicação dos documentos são operações distintas: o código é implantado a partir do repositório da aplicação, enquanto os documentos são atualizados no repositório de conteúdo.

## Próximo passo

Consulte o [Glossário](glossario.md) para uma lista resumida dos termos utilizados nesta documentação.
