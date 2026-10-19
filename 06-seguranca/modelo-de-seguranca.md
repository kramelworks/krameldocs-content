
# Modelo de segurança

## Objetivo

Este documento descreve os princípios de segurança do krameldocs, incluindo proteção de credenciais, validação de caminhos e tratamento do conteúdo recebido do repositório.

## Princípios

O projeto deve seguir estes princípios:

- **Menor privilégio:** utilizar somente as permissões necessárias para acessar o conteúdo.
- **Segredos no servidor:** manter tokens e credenciais fora do navegador.
- **Validação de entradas:** verificar caminhos e parâmetros recebidos pelas rotas.
- **Conteúdo controlado:** processar Markdown e HTML com medidas de segurança adequadas.
- **Falha segura:** evitar expor dados internos quando ocorrer um erro.
- **Manutenção contínua:** manter dependências e configurações atualizadas.

## Fronteiras de confiança

O portal interage com diferentes componentes:

1. **Navegador:** solicita páginas e recursos.
2. **Aplicação Next.js:** processa rotas e apresenta os documentos.
3. **Repositório GitHub:** armazena a documentação e os anexos.
4. **Ambiente de execução:** fornece as variáveis de configuração e os segredos.

Os dados provenientes do repositório devem ser tratados de acordo com o formato esperado e as regras de segurança da aplicação.

## Proteção de credenciais

O token do GitHub deve ser disponibilizado somente ao código que precisa acessar o repositório no servidor.

Não coloque credenciais:

- Em arquivos Markdown.
- Em URLs públicas.
- Em componentes executados no navegador.
- Em variáveis com prefixo `NEXT_PUBLIC_`.
- Em mensagens de erro ou logs.
- Em commits do repositório.

## Acesso ao conteúdo

O acesso aos documentos depende da configuração da fonte de conteúdo.

Um repositório público pode permitir leitura sem autenticação, conforme a implementação. Um repositório privado exige credenciais válidas e permissões adequadas.

A existência de um repositório privado não substitui a necessidade de verificar se a aplicação entrega corretamente os dados aos usuários.

## Validação de caminhos

As rotas que recebem caminhos de documentos ou arquivos devem impedir que a solicitação ultrapasse o diretório permitido.

Entradas como `..`, caminhos malformados e nomes de arquivos não autorizados devem ser tratados com segurança.

## Processamento de Markdown

O conteúdo Markdown deve ser processado sem permitir que HTML perigoso ou entradas maliciosas executem ações inesperadas no navegador.

A configuração do processador deve ser revista sempre que forem alterados os plugins ou as opções de renderização.

## Dependências

Mantenha as dependências atualizadas e avalie os avisos de segurança relevantes.

Após atualizações importantes, execute os testes, a verificação de tipos, o lint e o build.

## Tratamento de erros

Mensagens exibidas aos usuários devem ser úteis sem revelar tokens, detalhes internos de infraestrutura ou informações privadas.

Os logs operacionais também devem evitar a inclusão de segredos.

## Verificações antes da publicação

Antes de disponibilizar uma alteração:

1. Confirme que nenhum segredo foi incluído nos arquivos versionados.
2. Verifique as permissões do token utilizado.
3. Teste os caminhos de documentos e arquivos.
4. Revise a sanitização do conteúdo.
5. Execute os testes automatizados.
6. Verifique os logs após a implantação.

## Responsabilidade de manutenção

Este documento descreve os princípios esperados. A segurança efetiva depende da implementação atual, das permissões configuradas e da manutenção contínua do ambiente.
