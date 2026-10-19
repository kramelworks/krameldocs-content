
# Estrutura do navigation.json

## Objetivo

O arquivo `navigation.json` define a árvore de navegação apresentada pelo portal.

Ele permite organizar os documentos em grupos e subgrupos sem precisar alterar os componentes da aplicação a cada mudança na estrutura documental.

## Localização

O arquivo fica no repositório de conteúdo, no diretório-base configurado para a documentação.

Quando `DOCS_GIT_PATH` está vazio, o diretório-base corresponde à raiz do repositório.

## Tipos de item

A navegação pode conter dois tipos principais de item:

- **Grupo:** organiza outros itens por meio de `items`.
- **Documento:** aponta para um arquivo Markdown por meio de `file`.

Os grupos podem conter subgrupos, permitindo criar estruturas hierárquicas.

## Exemplo ilustrativo

A estrutura exata deve respeitar o formato esperado pelo código da aplicação. O exemplo a seguir ilustra a organização conceitual:

```json
{
  "title": "krameldocs",
  "items": [
    {
      "title": "Primeiros passos",
      "items": [
        {
          "title": "Instalação",
          "file": "guias/instalacao.md"
        },
        {
          "title": "Configuração",
          "file": "guias/configuracao.md"
        }
      ]
    }
  ]
}
```

Use esse exemplo como referência de estrutura, não como substituto automático do arquivo de navegação já configurado no projeto.

## Propriedade title

Identifica o nome visível do grupo ou do documento.

Prefira títulos curtos e claros, com capitalização consistente.

## Propriedade items

Contém a lista de itens subordinados a um grupo.

Use essa propriedade para organizar os documentos por assunto, sistema, etapa ou público-alvo.

## Propriedade file

Aponta para um arquivo Markdown relativo à raiz do conteúdo configurado.

Exemplo:

```text
guias/instalacao.md
```

O arquivo correspondente deve existir no repositório e respeitar a grafia exata do caminho.

## Propriedade icon

A estrutura pode incluir um ícone opcional, conforme o formato aceito pela implementação.

Antes de definir novos valores, confira quais identificadores de ícones são reconhecidos pelo portal.

## Convenções de organização

- Agrupe documentos por assunto.
- Evite criar grupos com apenas um documento sem necessidade.
- Utilize nomes consistentes.
- Não repita caminhos de arquivos desnecessariamente.
- Mantenha a hierarquia simples de compreender.
- Atualize a navegação quando um documento for movido ou renomeado.

## Validação

Antes de publicar alterações:

1. Confirme que o JSON é sintaticamente válido.
2. Verifique se os grupos possuem a estrutura esperada.
3. Confirme que os arquivos indicados existem.
4. Confira se os links gerados correspondem às URLs esperadas.
5. Abra o portal e navegue pelos documentos alterados.

## Erros comuns

### Arquivo não encontrado

O caminho de `file` não corresponde à localização real do documento.

### JSON inválido

Uma vírgula ausente, uma vírgula extra ou aspas incorretas podem impedir a leitura do arquivo.

### Link quebrado

O documento existe, mas a entrada da navegação contém um caminho diferente ou não foi atualizada após uma movimentação.

### Grupo não exibido como esperado

A estrutura utilizada não corresponde ao formato reconhecido pela implementação. Compare o arquivo com o exemplo funcional já existente no repositório.
