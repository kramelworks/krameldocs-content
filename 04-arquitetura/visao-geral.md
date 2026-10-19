
# Visão geral da arquitetura

O krameldocs é uma aplicação web construída com Next.js, React e TypeScript. Sua responsabilidade é apresentar documentos armazenados em um repositório GitHub separado do código-fonte.

A arquitetura separa a interface, o carregamento dos dados, o processamento de Markdown e a entrega de arquivos complementares.

## Componentes principais

### Aplicação web

A aplicação recebe as requisições do navegador, resolve as rotas, carrega os documentos e apresenta a interface.

### Repositório de conteúdo

O repositório contém `navigation.json`, artigos Markdown e assets utilizados nos documentos.

### GitHub

A aplicação consulta os arquivos do repositório por meio da API do GitHub. Quando necessário, utiliza uma credencial configurada no servidor.

### Pipeline Markdown

O pipeline transforma os documentos Markdown em conteúdo apropriado para apresentação no navegador. O processamento inclui os recursos Markdown habilitados, o realce de código e a sanitização da saída.

### Cache

O cache reduz consultas repetidas ao provedor de conteúdo e melhora a eficiência do carregamento.

### Rota de assets

Uma rota específica entrega imagens e anexos permitidos sem exigir que o navegador receba o token de acesso ao GitHub.

## Fluxo de carregamento de uma página

O fluxo lógico de uma página pode ser resumido assim:

```text
Navegador
   |
   v
Rota Next.js
   |
   v
Carregamento do documento
   |
   v
Cache em memória
   |
   +---- Cache válido ----> Reutilizar conteúdo
   |
   +---- Cache ausente ou expirado
                    |
                    v
              GitHub API
                    |
                    v
             Conteúdo Markdown
                    |
                    v
              Pipeline Markdown
                    |
                    v
             Página apresentada
```

Esse diagrama representa o fluxo conceitual. A ordem exata das chamadas depende da rota e da implementação atual.

## Fluxo de entrega de assets

```text
Navegador
   |
   v
/api/docs-assets/...
   |
   v
Validação do caminho e da extensão
   |
   v
Leitura do arquivo no GitHub
   |
   v
Resposta HTTP com o conteúdo
```

O endpoint deve validar os caminhos recebidos e restringir os formatos servidos.

## Separação entre código e conteúdo

A separação dos repositórios traz benefícios importantes:

- Os artigos podem ser alterados sem modificar a interface.
- O código da aplicação pode evoluir independentemente do conteúdo.
- O histórico editorial fica separado do histórico de desenvolvimento.
- Novos sistemas podem ser adicionados à árvore de navegação.

## Configuração

O comportamento relacionado à origem do conteúdo depende das variáveis de ambiente, incluindo:

- `DOCS_GIT_REPOSITORY`
- `DOCS_GIT_BRANCH`
- `DOCS_GIT_PATH`
- `DOCS_CACHE_TTL`
- `GITHUB_TOKEN`

Consulte [Variáveis de ambiente](../05-referencia/variaveis-de-ambiente.md) para os detalhes de configuração.

## Limites da arquitetura

A arquitetura atual utiliza GitHub como provedor de conteúdo. Suporte a outros provedores, cache distribuído e mecanismos adicionais de pesquisa dependem de implementação específica.

## Próximo passo

Consulte [Estrutura do código](estrutura-do-codigo.md) para localizar as principais responsabilidades no repositório da aplicação.
