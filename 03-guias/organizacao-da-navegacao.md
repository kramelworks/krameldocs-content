
# Organização da navegação

A navegação do krameldocs é definida pelo arquivo `navigation.json`, localizado na raiz do repositório de conteúdo configurado.

Esse arquivo determina a hierarquia dos grupos, os títulos das páginas e os caminhos utilizados para localizar os documentos.

## Estrutura básica

O objeto raiz possui a propriedade `items`, que contém a lista dos itens de navegação.

Existem dois tipos principais de item:

- **Grupo:** contém `title` e `items`.
- **Página:** contém `title` e `file`.

A propriedade `icon` é opcional quando suportada pelo componente de navegação.

## Exemplo de configuração

```json
{
  "items": [
    {
      "title": "krameldocs",
      "icon": "book-open",
      "items": [
        {
          "title": "Visão geral",
          "items": [
            {
              "title": "Apresentação",
              "file": "krameldocs/01-visao-geral/apresentacao.md"
            }
          ]
        }
      ]
    }
  ]
}
```

## Propriedades

### `title`

Define o texto que será apresentado para o grupo ou a página.

Utilize títulos claros e curtos, evitando abreviações que dificultem a compreensão.

### `items`

Contém os itens de um grupo.

Cada item pode ser outro grupo ou uma página. Isso permite organizar a navegação em vários níveis.

### `file`

Aponta para o arquivo Markdown correspondente à página.

O caminho deve ser relativo à raiz de conteúdo configurada, incluindo a extensão `.md`.

### `icon`

Define um identificador de ícone, quando suportado pela interface.

Utilize apenas nomes compatíveis com o conjunto de ícones utilizado pela aplicação.

## Organização para múltiplos sistemas

O primeiro nível da navegação deve identificar o sistema documentado.

Cada sistema pode conter categorias padronizadas, como visão geral, primeiros passos, arquitetura, referência técnica e solução de problemas.

Essa convenção facilita a consulta e mantém uma experiência consistente entre sistemas.

## Validação antes de publicar

Antes de enviar mudanças, confirme:

- O JSON é válido.
- Todos os grupos possuem títulos.
- Todas as páginas possuem título e caminho.
- Os caminhos apontam para arquivos existentes.
- Não existem referências duplicadas ou obsoletas.
- A ordem dos itens é intencional.
- Os nomes dos ícones são compatíveis com a aplicação.

## Erros comuns

### Vírgula extra

JSON não permite vírgulas após o último elemento de um objeto ou de uma lista.

### Caminho incorreto

Um erro de digitação no nome da pasta ou do arquivo pode impedir a localização do documento.

### Arquivo ausente

Adicionar uma página à navegação antes de criar seu Markdown deixa uma referência incompleta.

### Estrutura incorreta

Um grupo precisa utilizar `items`, enquanto uma página deve apontar para um arquivo por meio de `file`.

## Próximo passo

Consulte [Escrever em Markdown](escrever-markdown.md) para aprender a produzir os artigos.
