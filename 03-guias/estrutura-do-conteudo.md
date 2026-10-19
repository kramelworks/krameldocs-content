
# Estrutura do conteúdo

O repositório de conteúdo é responsável por armazenar os artigos, a configuração de navegação e os arquivos complementares utilizados pela documentação.

A organização dos diretórios deve facilitar a manutenção e permitir a inclusão de novos sistemas.

## Estrutura geral

A estrutura recomendada para o repositório é:

```text
krameldocs-content/
├── navigation.json
├── index.md
├── krameldocs/
│   ├── 01-visao-geral/
│   ├── 02-primeiros-passos/
│   ├── 03-guias/
│   ├── 04-arquitetura/
│   ├── 05-referencia/
│   ├── 06-seguranca/
│   ├── 07-operacoes/
│   ├── 08-desenvolvimento/
│   ├── 09-solucao-problemas/
│   └── 10-historico/
└── assets/
```

Os diretórios são criados conforme os arquivos são adicionados ao GitHub.

## Arquivo de navegação

O arquivo `navigation.json` define a hierarquia apresentada no portal.

Cada grupo pode conter outros grupos ou páginas. Cada página referencia um arquivo Markdown por meio da propriedade `file`.

A configuração precisa corresponder à estrutura real do repositório.

## Organização por sistema

Cada sistema documentado deve ter seu próprio diretório na raiz do conteúdo.

Exemplo:

```text
krameldocs-content/
├── navigation.json
├── krameldocs/
│   ├── 01-visao-geral/
│   └── 02-primeiros-passos/
├── outro-sistema/
│   ├── 01-visao-geral/
│   └── 02-primeiros-passos/
└── assets/
```

O nome da pasta do sistema deve corresponder ao prefixo usado nos caminhos dos artigos em `navigation.json`.

## Convenção de nomes

Recomenda-se:

- Utilizar nomes em letras minúsculas.
- Separar palavras com hífens.
- Evitar espaços e caracteres especiais nos nomes dos arquivos.
- Utilizar a extensão `.md` para os documentos.
- Manter nomes claros e relacionados ao assunto.
- Preservar a mesma convenção entre sistemas.

Exemplo:

`krameldocs/03-guias/estrutura-do-conteudo.md`

## Diretório de assets

Arquivos complementares podem ser armazenados em uma pasta compartilhada, como `assets/`.

Exemplo:

```text
assets/
├── arquitetura.png
└── manual.pdf
```

Com a configuração atual, os caminhos de assets são relativos à raiz do conteúdo. Portanto, uma imagem pode ser referenciada assim:

```markdown
![Arquitetura](assets/arquitetura.png)
```

Não presuma que um caminho relativo à pasta do artigo será resolvido da mesma forma.

## Cuidados ao alterar a estrutura

Antes de renomear ou excluir arquivos:

1. Atualize as referências em `navigation.json`.
2. Revise os links de outros documentos.
3. Confira as referências a imagens e anexos.
4. Teste as páginas afetadas.

## Próximo passo

Consulte [Organização da navegação](organizacao-da-navegacao.md) para aprender a estruturar o menu.
