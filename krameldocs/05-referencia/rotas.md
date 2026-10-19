
# Rotas da aplicação

## Visão geral

O krameldocs utiliza rotas do Next.js para apresentar a documentação e disponibilizar recursos armazenados no repositório de conteúdo.

## Rotas principais

| Rota | Finalidade |
|---|---|
| `/` | Página inicial da aplicação. |
| `/docs` | Entrada da documentação. |
| `/docs/[...slug]` | Exibe documentos identificados por um caminho variável. |
| `/api/docs-assets/[...path]` | Disponibiliza arquivos e recursos do repositório de conteúdo. |

## Página inicial

A rota `/` apresenta a entrada do portal e orienta o usuário para a documentação.

A estrutura visual e os links apresentados dependem da implementação atual da aplicação.

## Índice da documentação

A rota `/docs` representa a entrada principal da documentação.

O documento inicial e a navegação devem estar coerentes com a estrutura configurada no repositório de conteúdo.

## Documentos por caminho

A rota `/docs/[...slug]` utiliza um segmento dinâmico que pode conter vários níveis de caminho.

Por exemplo, um arquivo de conteúdo como:

```text
guias/instalacao.md
```

corresponde à URL:

```text
/docs/guias/instalacao
```

O caminho efetivamente disponível depende da existência do documento e da configuração de navegação.

## Recursos e anexos

A rota `/api/docs-assets/[...path]` entrega recursos associados ao conteúdo, como imagens e PDFs.

Exemplo de referência em um documento Markdown:

```markdown
![Arquitetura](assets/arquitetura.png)
```

O endereço final do recurso depende da forma como o Markdown é processado pela aplicação.

## Navegação

A navegação é definida pelo arquivo `navigation.json` no repositório de conteúdo.

Os documentos devem ter caminhos consistentes entre esse arquivo e a estrutura de diretórios. Um item de navegação que aponta para um arquivo inexistente pode resultar em um link quebrado.

## Diagnóstico de rotas

Se uma página não abrir:

1. Confira o endereço acessado.
2. Confirme se o arquivo Markdown existe no repositório.
3. Verifique se a navegação aponta para o arquivo correto.
4. Confira a branch e o diretório-base configurados.
5. Analise os logs da aplicação para identificar erros de leitura ou processamento.
