
# Dependências

## Visão geral

O krameldocs utiliza o ecossistema Next.js e TypeScript para implementar o portal, além de bibliotecas de processamento de Markdown, realce de sintaxe e testes automatizados.

A relação exata de versões e dependências deve ser consultada nos arquivos `package.json` e no arquivo de lock do repositório.

## Tecnologias principais

### Next.js

Responsável pela aplicação web, pelo sistema de rotas e pela integração entre páginas e funcionalidades executadas no servidor.

### React

Biblioteca utilizada para construir a interface do portal.

### TypeScript

Adiciona tipagem estática ao código JavaScript e ajuda a identificar incompatibilidades durante o desenvolvimento.

### Tailwind CSS

Utilizado para compor e manter os estilos da interface por meio de classes utilitárias.

### Remark e Rehype

Ferramentas do ecossistema Markdown utilizadas no processamento e na transformação do conteúdo.

### Shiki

Biblioteca utilizada para realce de sintaxe em blocos de código.

### Vitest

Ferramenta de testes automatizados utilizada para verificar comportamentos da aplicação.

## Instalação

Instale as dependências a partir dos arquivos mantidos no repositório:

```bash
npm install
```

Evite instalar versões arbitrárias de bibliotecas sem avaliar a compatibilidade com o projeto.

## Atualização de dependências

Antes de atualizar uma dependência:

1. Identifique o problema ou benefício esperado.
2. Consulte as alterações relevantes da nova versão.
3. Verifique os requisitos de compatibilidade.
4. Atualize os arquivos de dependências e lock.
5. Execute lint, verificação de tipos, testes e build.
6. Teste as páginas e os recursos afetados.

## Segurança das dependências

Mantenha as bibliotecas atualizadas de acordo com uma política de manutenção apropriada.

Avalie avisos de vulnerabilidade considerando a versão afetada, a possibilidade de exploração e a existência de correções.

Não aplique atualizações em massa sem verificar os impactos funcionais.

## Fonte oficial

O `package.json` e o arquivo de lock do repositório são as referências para as dependências e versões efetivamente utilizadas.

Este documento explica a função das principais tecnologias e não substitui esses arquivos.
