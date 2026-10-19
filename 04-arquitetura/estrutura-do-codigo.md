
# Estrutura do código

O código do krameldocs é organizado por responsabilidades para facilitar a manutenção, os testes e a evolução da aplicação.

Esta página descreve a organização conceitual dos principais módulos. A estrutura exata deve ser confirmada no repositório ao realizar alterações significativas.

## Diretório `src/app`

Contém as rotas e as páginas da aplicação Next.js.

As responsabilidades incluem:

- Página inicial.
- Rotas de documentação.
- Layouts da aplicação.
- Endpoint de entrega de assets.
- Respostas HTTP associadas às rotas.

## Diretório `src/components`

Contém componentes reutilizáveis da interface, incluindo elementos relacionados à documentação e à navegação.

Os componentes de interface devem manter responsabilidades claras e evitar duplicação desnecessária de lógica.

## Diretório `src/lib`

Contém módulos de lógica compartilhada e serviços utilizados pelas rotas.

Entre as responsabilidades estão:

- Leitura e validação da configuração.
- Comunicação com o GitHub.
- Cache de conteúdo.
- Resolução da navegação.
- Processamento de Markdown.
- Transformação de links e caminhos.

## Tipos TypeScript

Os tipos descrevem estruturas utilizadas pela aplicação, como itens de navegação e dados de documentos.

Quando uma estrutura compartilhada mudar, seus tipos e os testes relacionados devem ser revisados.

## Testes

Os testes ajudam a verificar o comportamento de módulos isolados e funcionalidades importantes.

Alterações em navegação, acesso ao GitHub, processamento Markdown ou entrega de assets devem incluir verificações proporcionais ao risco da mudança.

## Fluxo de uma requisição

Uma rota recebe a requisição, utiliza os módulos necessários para localizar e carregar o conteúdo, processa os dados e retorna a página ou o recurso solicitado.

A lógica de acesso ao GitHub deve permanecer no servidor quando envolver credenciais privadas.

## Convenções de manutenção

- Prefira módulos pequenos com uma responsabilidade clara.
- Evite duplicar a lógica de acesso ao conteúdo.
- Valide dados externos antes de utilizá-los.
- Mantenha os tipos atualizados.
- Adicione testes para comportamentos novos ou corrigidos.
- Evite expor detalhes internos ou segredos em mensagens de erro.
- Atualize a documentação quando uma decisão arquitetural mudar.

## Como confirmar a estrutura real

Antes de alterar um módulo:

1. Abra o repositório `kramelworks-admin/krameldocs`.
2. Localize a rota ou o componente relacionado.
3. Identifique os módulos que ele importa.
4. Leia os testes associados.
5. Faça a alteração no local apropriado.
6. Execute lint, verificação de tipos, testes e build.

## Próximo passo

Consulte [Integração com GitHub](integracao-github.md) para entender como a aplicação acessa os arquivos documentais.
