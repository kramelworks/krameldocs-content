
# Ambientes

## Objetivo

Descrever os ambientes utilizados no desenvolvimento, na validação e na publicação do krameldocs.

## Desenvolvimento local

O ambiente local é utilizado para implementar funcionalidades, editar configurações e executar testes antes de publicar alterações.

Configurações comuns:

- Aplicação Next.js executada localmente.
- Arquivo `.env.local` para valores específicos do desenvolvedor.
- Repositório de conteúdo configurado pelas variáveis de ambiente.
- Testes automatizados executados na máquina de desenvolvimento.

Não versione segredos nem configurações pessoais.

## Produção

O ambiente de produção disponibiliza o portal aos usuários.

Na configuração atual prevista, a aplicação é implantada na Vercel e utiliza um repositório GitHub separado para obter a documentação.

As variáveis de ambiente devem ser configuradas no projeto de hospedagem.

## Repositórios separados

O código da aplicação e o conteúdo documental ficam em repositórios distintos:

- Aplicação: `kramelworks-admin/krameldocs`
- Conteúdo: `kramelworks/krameldocs-content`

Essa separação permite publicar alterações documentais sem precisar alterar o código da aplicação.

## Configuração por ambiente

Cada ambiente deve ter valores coerentes para:

- `DOCS_GIT_REPOSITORY`
- `DOCS_GIT_BRANCH`
- `DOCS_GIT_PATH`
- `DOCS_CACHE_TTL`
- `GITHUB_TOKEN`, quando necessário

Confirme que a aplicação aponta para o repositório, a branch e o diretório corretos.

## Diferenças entre ambientes

O comportamento pode variar devido a:

- Permissões do token.
- Visibilidade do repositório.
- Configurações de cache.
- Variáveis de ambiente ausentes.
- Diferenças entre sistemas operacionais.
- Configurações de build e execução.

Não considere um teste local suficiente para validar todas as condições de produção.

## Boas práticas

1. Teste localmente antes de publicar.
2. Revise as alterações no Git.
3. Execute lint, verificação de tipos, testes e build.
4. Confirme as variáveis de ambiente do destino.
5. Verifique o deploy após a publicação.
6. Teste as páginas e os anexos no ambiente final.

## Alterações de configuração

Quando uma variável de ambiente for alterada, verifique se é necessário reconstruir ou reiniciar a aplicação para que o novo valor seja aplicado.

Registre mudanças relevantes de configuração e atualize a documentação correspondente.
