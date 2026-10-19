
# Links, imagens e anexos

Os documentos do krameldocs podem referenciar outros artigos e arquivos complementares, desde que os caminhos e os formatos sejam compatíveis com a implementação.

## Links para sites externos

Utilize a sintaxe Markdown:

```markdown
[Documentação do GitHub](https://docs.github.com/)
```

Antes de publicar, confirme se o endereço está correto e se o destino é confiável.

## Links para outros artigos

Os links entre artigos devem apontar para os arquivos Markdown correspondentes.

Exemplo:

```markdown
Consulte [Instalação local](../02-primeiros-passos/instalacao-local.md).
```

O caminho deve ser calculado a partir do diretório do documento atual.

Depois de criar um link, teste-o no portal para confirmar que a aplicação o resolve corretamente.

## Referenciar imagens

Os assets são armazenados no repositório de conteúdo.

Exemplo de estrutura:

```text
krameldocs-content/
├── navigation.json
├── krameldocs/
│   └── 04-arquitetura/
│       └── visao-geral.md
└── assets/
    └── arquitetura.png
```

Para incluir a imagem no documento:

```markdown
![Diagrama da arquitetura](assets/arquitetura.png)
```

Na implementação atual, o caminho do asset é relativo à raiz do conteúdo, e não à pasta em que o artigo está armazenado.

## Texto alternativo

Sempre que possível, forneça uma descrição que comunique a informação importante da imagem.

Exemplo:

```markdown
![Diagrama mostrando o navegador, a aplicação Next.js e o repositório GitHub](assets/arquitetura.png)
```

Isso melhora a acessibilidade e ajuda quando a imagem não pode ser exibida.

## Referenciar PDFs

Um PDF pode ser disponibilizado por meio de um link:

```markdown
[Consultar o manual](assets/manual.pdf)
```

O arquivo precisa existir no repositório e utilizar uma extensão permitida pela rota de assets.

## Formatos permitidos

A implementação atual permite extensões selecionadas, incluindo:

- PNG
- JPG e JPEG
- GIF
- WebP
- SVG
- ICO
- PDF
- TXT
- CSV
- JSON
- ZIP

A lista e os limites devem ser confirmados no código da rota de assets quando houver alterações na aplicação.

## Limite de tamanho

O limite atual da rota é de 2 MB por arquivo.

Se o arquivo ultrapassar esse limite, reduza seu tamanho ou avalie uma estratégia de distribuição compatível com a arquitetura.

## Problemas comuns

### Imagem não aparece

Verifique o nome, a extensão, a capitalização e o caminho relativo à raiz de conteúdo.

### PDF não abre

Confirme que o arquivo existe, que sua extensão é permitida e que o tamanho respeita o limite configurado.

### Link para artigo não funciona

Confira o caminho relativo, a extensão `.md` e a existência do arquivo de destino.

### Arquivo não é encontrado

Verifique se o arquivo foi enviado para a branch configurada na aplicação e se o caminho respeita o diretório-base definido nas variáveis de ambiente.

## Segurança

Não publique arquivos que contenham tokens, senhas, chaves privadas ou dados confidenciais.

A presença de um arquivo no repositório de conteúdo não deve ser utilizada como mecanismo de controle de acesso por si só.

## Próximo passo

Consulte [Publicar alterações](publicar-alteracoes.md) para conhecer o fluxo recomendado para atualizar a documentação.
