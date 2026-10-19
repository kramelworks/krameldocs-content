
# Integração com GitHub

O krameldocs utiliza o GitHub como provedor do conteúdo documental.

A aplicação consulta os arquivos do repositório configurado e utiliza seus dados para construir as páginas e entregar os assets permitidos.

## Repositório de conteúdo

O repositório utilizado como referência neste projeto é:

`kramelworks/krameldocs-content`

A aplicação não deve depender de caminhos fixos espalhados pelo código para identificar a origem do conteúdo. Essa origem é configurada por variáveis de ambiente.

## Configuração do repositório

### `DOCS_GIT_REPOSITORY`

Identifica a organização e o repositório, no formato:

`organização/repositório`

### `DOCS_GIT_BRANCH`

Define a branch que será consultada.

### `DOCS_GIT_PATH`

Permite configurar um diretório-base para o conteúdo, conforme o comportamento implementado pela aplicação.

Quando estiver vazio, a raiz do repositório é utilizada como base.

## Autenticação

A variável `GITHUB_TOKEN` fornece uma credencial para chamadas autenticadas ao GitHub.

O token deve:

- Ter apenas as permissões necessárias.
- Ter acesso ao repositório correto.
- Permanecer no ambiente do servidor.
- Ser mantido fora do controle de versão.
- Ser renovado ou revogado quando houver suspeita de exposição.

Não coloque o token em variáveis com prefixo `NEXT_PUBLIC_`, documentos Markdown, arquivos de configuração públicos ou código executado no navegador.

## Acesso a arquivos

A integração permite consultar os arquivos utilizados pela documentação, incluindo:

- `navigation.json`.
- Artigos Markdown.
- Imagens e anexos permitidos.

O comportamento específico de cada chamada depende do módulo de integração e das APIs do GitHub utilizadas na implementação.

## Repositórios públicos e privados

Em um repositório público, alguns arquivos podem ser acessados sem autenticação, respeitando as regras da API.

Em um repositório privado, a aplicação precisa de credenciais com permissões adequadas para ler o conteúdo.

A disponibilidade de um documento no portal depende tanto da configuração quanto das permissões de acesso.

## Cache

As respostas podem ser armazenadas em cache para evitar consultas repetidas.

O tempo de validade é configurado por `DOCS_CACHE_TTL`.

Uma alteração no GitHub pode não aparecer imediatamente se uma instância ainda estiver utilizando uma entrada válida de cache.

## Tratamento de erros

Falhas na integração podem ocorrer por motivos como:

- Token inválido ou expirado.
- Permissões insuficientes.
- Repositório ou branch incorretos.
- Arquivo inexistente.
- Limites de requisição do GitHub.
- Indisponibilidade temporária da API.
- Problemas de conectividade.

Os erros devem ser tratados de forma controlada. Respostas públicas não devem revelar tokens ou outros dados confidenciais.

## Diagnóstico

Ao investigar uma falha:

1. Confirme o repositório configurado.
2. Verifique o nome da branch.
3. Confirme a existência do arquivo.
4. Verifique as permissões do token sem divulgar seu valor.
5. Consulte os logs do servidor.
6. Considere o efeito do cache.

## Próximo passo

Consulte [Pipeline Markdown](pipeline-markdown.md) para entender como os documentos são preparados para apresentação.
