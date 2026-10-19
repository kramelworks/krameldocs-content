
# Decisões técnicas

## Objetivo

Este documento registra as principais decisões técnicas do krameldocs e os motivos que orientam sua arquitetura.

## Next.js com App Router

O portal utiliza Next.js com App Router para organizar páginas, layouts e endpoints no mesmo projeto.

Essa escolha permite:

- Organizar as páginas por rotas.
- Executar a leitura do conteúdo no servidor.
- Disponibilizar endpoints próprios para recursos.
- Integrar a aplicação com plataformas de hospedagem compatíveis com Next.js.

## TypeScript

TypeScript é utilizado para identificar incompatibilidades de tipos durante o desenvolvimento e tornar os contratos internos mais explícitos.

Alterações em estruturas como a navegação ou o provedor de conteúdo devem preservar os tipos existentes e ser acompanhadas de testes.

## GitHub como fonte de conteúdo

O conteúdo da documentação é armazenado em um repositório Git separado do código da aplicação.

Essa separação permite:

- Atualizar documentos sem alterar o código do portal.
- Revisar alterações por meio de commits e pull requests.
- Manter o histórico dos documentos.
- Configurar o conteúdo por repositório, branch e diretório-base.

## Provedor de conteúdo isolado

A integração com o GitHub fica separada das páginas e dos componentes visuais.

Essa divisão reduz o acoplamento entre a interface e a origem dos documentos, facilitando a manutenção e a eventual implementação de outros provedores.

## Markdown em vez de MDX

O conteúdo utiliza Markdown com recursos adicionais de formatação, incluindo funcionalidades do GitHub Flavored Markdown.

O portal não deve ser tratado como um ambiente de execução de MDX. Documentos devem conter conteúdo, não componentes React ou código executável embutido.

## Cache

A leitura dos documentos utiliza cache para reduzir requisições repetidas ao repositório de conteúdo.

O intervalo é configurado pela variável `DOCS_CACHE_TTL`. Alterações no conteúdo podem levar algum tempo para aparecer, dependendo do comportamento do cache e do ambiente de execução.

## Segredos no servidor

O token do GitHub é configurado pela variável `GITHUB_TOKEN` e deve permanecer exclusivamente no ambiente do servidor.

Ele não deve ser exposto em variáveis com prefixo `NEXT_PUBLIC_`, no código enviado ao navegador ou em mensagens de erro.

## Entrega de arquivos

Imagens, PDFs e outros recursos são disponibilizados por uma rota da própria aplicação. Isso permite que o portal intermedie o acesso aos arquivos armazenados no repositório de conteúdo.

O comportamento e as extensões aceitas devem permanecer alinhados com a implementação da rota de arquivos.

## Testes automatizados

Os testes automatizados ajudam a preservar o comportamento esperado durante alterações na navegação, no processamento dos documentos e na integração com o repositório.

Mudanças relevantes devem incluir testes apropriados e passar pelas verificações de qualidade do projeto.

## Revisão das decisões

As decisões técnicas podem ser revistas quando houver necessidade concreta, como mudanças de escala, segurança, custos ou requisitos funcionais.

Uma revisão deve considerar:

1. O problema que motivou a mudança.
2. As alternativas avaliadas.
3. Os impactos sobre compatibilidade e manutenção.
4. Os testes necessários.
5. A atualização da documentação relacionada.
