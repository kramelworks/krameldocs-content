
# Cache e atualização do conteúdo

## Objetivo

Explicar como o cache afeta a atualização dos documentos publicados no krameldocs.

## Por que utilizar cache

O cache reduz requisições repetidas ao repositório de conteúdo, podendo melhorar o tempo de resposta e diminuir a quantidade de acessos à origem.

## Configuração

A variável utilizada para configurar o intervalo é:

```text
DOCS_CACHE_TTL=60
```

O valor `60` representa o intervalo configurado em segundos. O comportamento efetivo depende da implementação do cache e do ambiente de execução.

## Publicação de documentos

O fluxo habitual é:

1. Editar o documento no repositório de conteúdo.
2. Revisar as alterações.
3. Fazer commit e publicar a alteração na branch configurada.
4. Aguardar o mecanismo de atualização do conteúdo.
5. Abrir o portal e conferir o resultado.

## Alterações que podem exigir atenção

Verifique especialmente:

- Alterações em `navigation.json`.
- Mudanças nos caminhos dos documentos.
- Inclusão ou remoção de imagens.
- Atualizações de PDFs e outros anexos.
- Mudanças de configuração do provedor de conteúdo.

## Quando a alteração não aparece

Se um documento continuar exibindo o conteúdo antigo:

1. Confirme que o commit foi publicado na branch correta.
2. Confira se o portal está apontando para o repositório esperado.
3. Verifique o diretório-base configurado.
4. Aguarde o intervalo de cache aplicável.
5. Teste novamente a página.
6. Consulte os logs caso o problema persista.

## Cache e deploy

Alterar um documento no repositório de conteúdo não significa necessariamente que um novo deploy da aplicação seja obrigatório.

A necessidade de deploy depende do tipo de alteração e da implementação. Alterações no código ou em configurações aplicadas durante o build podem exigir uma nova implantação.

## Evitar pressupostos

Não presuma que o cache é compartilhado entre todas as instâncias nem que a expiração ocorre exatamente no mesmo instante em todos os ambientes.

Para diagnosticar comportamento inesperado, consulte o código do provedor de conteúdo e a configuração efetiva do ambiente.

## Boas práticas

- Mantenha o intervalo de cache documentado.
- Evite alterar o TTL sem avaliar o impacto.
- Teste mudanças na navegação e nos recursos.
- Registre problemas recorrentes e suas soluções.
