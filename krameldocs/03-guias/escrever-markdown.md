
# Escrever em Markdown

Markdown é o formato utilizado para escrever os artigos do krameldocs.

Sua sintaxe permite criar documentos legíveis em texto simples e renderizá-los com formatação no portal.

## Títulos

Utilize o caractere `#` para definir os níveis de título.

```markdown
# Título principal

## Seção

### Subseção
```

Recomenda-se utilizar um único título principal por artigo e organizar as seções em uma hierarquia lógica.

## Parágrafos

Separe parágrafos com uma linha em branco.

```markdown
Este é o primeiro parágrafo.

Este é o segundo parágrafo.
```

## Ênfase

```markdown
**Texto em negrito**

*Texto em itálico*

`nome-de-arquivo.md`
```

Use negrito com moderação, reservando-o para informações que mereçam destaque.

## Listas

Lista não ordenada:

```markdown
- Primeiro item
- Segundo item
- Terceiro item
```

Lista ordenada:

```markdown
1. Primeiro passo
2. Segundo passo
3. Terceiro passo
```

Utilize listas numeradas para procedimentos cuja ordem seja importante.

## Links

```markdown
[Texto do link](https://example.com)
```

Para links entre artigos, utilize caminhos relativos aos arquivos Markdown.

Exemplo:

```markdown
Consulte [Configuração inicial](../02-primeiros-passos/configuracao-inicial.md).
```

Após mover ou renomear um arquivo, revise os links que dependem dele.

## Tabelas

```markdown
| Variável | Finalidade |
| --- | --- |
| `DOCS_GIT_BRANCH` | Define a branch de conteúdo |
| `DOCS_CACHE_TTL` | Define o tempo de cache |
```

Utilize tabelas quando facilitarem a comparação de informações.

## Blocos de código

Use três crases para abrir e fechar um bloco de código. Informe a linguagem quando possível.

````markdown
```typescript
const mensagem: string = "Olá";
console.log(mensagem);
```
````

Não coloque tokens, senhas ou outros segredos em exemplos.

## Imagens

```markdown
![Descrição da imagem](assets/arquitetura.png)
```

A descrição alternativa deve explicar o conteúdo relevante da imagem.

Na configuração atual, os assets são referenciados a partir da raiz do conteúdo.

## Citações

```markdown
> Importante: valide a configuração antes de publicar.
```

Utilize citações para observações, ressalvas e informações que precisam se destacar.

## Boas práticas

- Prefira frases objetivas.
- Organize documentos extensos em seções.
- Explique siglas na primeira ocorrência.
- Use exemplos coerentes com a aplicação.
- Revise links e caminhos de arquivos.
- Não inclua dados confidenciais.
- Diferencie recursos existentes de funcionalidades planejadas.

## Limitações

O pipeline atual trabalha com Markdown e não deve ser tratado como um ambiente de execução de MDX ou JSX.

HTML arbitrário, scripts e componentes React embutidos não devem ser considerados recursos suportados.

## Próximo passo

Consulte [Links, imagens e anexos](links-imagens-anexos.md) para aprender a referenciar arquivos complementares.
