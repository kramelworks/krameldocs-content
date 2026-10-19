
# Publicar alterações

Este documento descreve o processo recomendado para atualizar a documentação do krameldocs.

O conteúdo editorial fica separado do código da aplicação, permitindo publicar alterações nos artigos sem precisar realizar um novo deploy da aplicação para cada mudança.

## Onde realizar as alterações

Os documentos devem ser editados no repositório:

`kramelworks/krameldocs-content`

A aplicação consulta o conteúdo a partir do repositório e da branch definidos nas variáveis de ambiente.

## Publicar um novo artigo

1. Identifique a categoria em que o artigo deve aparecer.
2. Crie o arquivo Markdown no diretório correspondente.
3. Escreva e revise o conteúdo.
4. Adicione uma entrada para o artigo em `navigation.json`.
5. Confira os links internos e os assets utilizados.
6. Faça o commit das alterações.
7. Envie as mudanças para a branch configurada.
8. Acesse o portal e valide o artigo publicado.

## Publicar uma alteração em artigo existente

1. Abra o arquivo Markdown.
2. Faça as alterações necessárias.
3. Revise a precisão técnica e a formatação.
4. Confirme que os links e os anexos continuam válidos.
5. Faça o commit.
6. Valide a página no portal após a atualização.

## Atualizar a navegação

Ao alterar `navigation.json`, confirme que:

- O JSON continua válido.
- Todos os caminhos apontam para arquivos existentes.
- Os títulos estão claros.
- A ordem dos itens é intencional.
- Não foram removidas referências necessárias.

## Commit pelo terminal

Um fluxo básico de Git pode ser executado assim:

```bash
git status
git add navigation.json krameldocs/
git commit -m "docs: atualizar documentação do krameldocs"
git push origin main
```

Execute os comandos no clone local do repositório de conteúdo. Ajuste os caminhos conforme os arquivos modificados.

No GitHub, também é possível criar ou editar arquivos pela interface web e registrar as alterações por meio de um commit.

## Cache e propagação

A aplicação utiliza cache em memória. Por isso, alterações recém-publicadas podem não aparecer imediatamente.

O tempo de validade é configurado por `DOCS_CACHE_TTL`, mas o comportamento observado também pode depender do processo e da instância que atende à requisição.

## Revisão recomendada

Antes de publicar, verifique:

- Ortografia e clareza.
- Precisão das instruções.
- Correspondência entre a navegação e os arquivos.
- Links internos e externos.
- Imagens e anexos.
- Ausência de tokens, senhas e informações confidenciais.

## Reverter uma alteração

Se uma mudança introduzir um erro, utilize o histórico do Git para identificar o commit responsável e preparar uma reversão.

Antes de restaurar arquivos, avalie se outros documentos dependem das mudanças mais recentes.

## Próximo passo

Consulte [Visão geral da arquitetura](../04-arquitetura/visao-geral.md) para entender como a aplicação apresenta o conteúdo.
