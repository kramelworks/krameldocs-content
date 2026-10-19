
# Pipeline Markdown

O pipeline Markdown transforma o conteúdo textual dos artigos em páginas formatadas para apresentação no navegador.

O processamento permite que os autores escrevam documentação em texto simples sem precisar produzir HTML manualmente.

## Entrada

A entrada principal é um arquivo `.md` carregado do repositório de conteúdo.

O arquivo pode conter:

- Títulos e parágrafos.
- Listas ordenadas e não ordenadas.
- Links.
- Tabelas compatíveis com GFM.
- Blocos de código.
- Referências a imagens e anexos.

## Etapas conceituais

O processamento pode ser entendido pelas seguintes etapas:

1. Localizar o documento solicitado.
2. Ler o conteúdo Markdown.
3. Processar a sintaxe Markdown e as extensões habilitadas.
4. Aplicar realce de sintaxe aos blocos de código.
5. Resolver ou transformar links e referências a assets quando necessário.
6. Sanitizar o HTML resultante.
7. Entregar o conteúdo renderizado pela aplicação.

A sequência exata e os módulos envolvidos devem ser confirmados no código-fonte da versão implantada.

## GitHub Flavored Markdown

A configuração atual oferece recursos de GFM, incluindo tabelas e outras extensões compatíveis com o pipeline.

Exemplo:

```markdown
| Campo | Descrição |
| --- | --- |
| Branch | Linha de desenvolvimento |
| Cache | Armazenamento temporário |
```

## Realce de sintaxe

Os blocos de código podem receber realce de sintaxe por meio do mecanismo configurado na aplicação.

Exemplo:

````markdown
```typescript
const titulo: string = "krameldocs";
console.log(titulo);
```
````

Informe a linguagem no início do bloco sempre que possível.

## Links

Links para outros artigos devem ser escritos de maneira consistente com a resolução de caminhos da aplicação.

Ao mover um arquivo, revise as referências existentes para evitar links quebrados.

## Sanitização

O HTML produzido pelo processamento passa por sanitização para restringir elementos e atributos não permitidos.

Essa proteção reduz riscos associados ao conteúdo, mas não significa que qualquer HTML ou script seja um recurso suportado.

## Limitações

O pipeline atual não deve ser tratado como um ambiente de execução de MDX ou JSX.

Não presuma que componentes React, scripts ou HTML arbitrário funcionarão dentro de um artigo.

## Testes

Alterações no pipeline devem ser acompanhadas de testes para verificar, conforme aplicável:

- Formatação dos elementos Markdown.
- Renderização de tabelas e blocos de código.
- Transformação de links.
- Referências a imagens e anexos.
- Sanitização da saída.
- Tratamento de conteúdo inválido.

## Próximo passo

Consulte [Cache](cache.md) para compreender como a aplicação reduz consultas repetidas ao provedor de conteúdo.
