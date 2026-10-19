
# Objetivos e funcionalidades

## Objetivo principal

O krameldocs tem como objetivo centralizar a documentação técnica de múltiplos sistemas em um portal organizado, consistente e de fácil manutenção.

A plataforma separa o código responsável pela apresentação dos documentos do conteúdo editorial. Os artigos ficam em um repositório GitHub dedicado e são escritos em Markdown, permitindo que as atualizações sigam o fluxo de versionamento do Git.

## Objetivos específicos

- Centralizar a documentação de diferentes sistemas.
- Padronizar a organização dos artigos técnicos.
- Simplificar a criação, a edição e a publicação de conteúdo.
- Manter o histórico das alterações por meio do Git.
- Permitir a inclusão de imagens e anexos compatíveis.
- Facilitar a consulta de procedimentos e referências técnicas.
- Evitar a necessidade de modificar o código da aplicação a cada atualização documental.
- Estabelecer uma base extensível para futuras melhorias.

## Funcionalidades implementadas

A versão atual do portal contempla os seguintes recursos, conforme a implementação existente:

### Renderização de documentos

Os arquivos Markdown são convertidos em páginas de documentação acessíveis pelo navegador.

### Navegação hierárquica

O arquivo `navigation.json` define os títulos, os grupos, a ordem e os caminhos das páginas exibidas no menu.

### Formatação de conteúdo

A renderização oferece recursos de Markdown, incluindo títulos, listas, tabelas, links e blocos de código, de acordo com os recursos habilitados no pipeline.

### Realce de sintaxe

Blocos de código podem ser apresentados com realce de sintaxe por meio do mecanismo de formatação configurado na aplicação.

### Integração com GitHub

O portal consulta o repositório de conteúdo configurado. O acesso pode utilizar autenticação no servidor quando necessária.

### Imagens e anexos

Uma rota específica permite entregar arquivos de conteúdo compatíveis, respeitando as validações e os limites definidos pela aplicação.

### Cache

O carregamento de conteúdo utiliza cache com tempo de validade configurável, reduzindo consultas repetidas ao provedor de conteúdo.

## Características da arquitetura

A plataforma mantém separadas três responsabilidades:

| Componente | Responsabilidade |
| --- | --- |
| Aplicação | Apresentar as páginas, processar Markdown e implementar a navegação. |
| Repositório de conteúdo | Armazenar os artigos, a configuração de navegação e os arquivos associados. |
| GitHub | Versionar o conteúdo e disponibilizar os arquivos para leitura pela aplicação. |

## Evoluções possíveis

As seguintes capacidades podem ser avaliadas para versões futuras, caso sejam necessárias:

- Pesquisa global de conteúdo.
- Suporte a outros provedores de armazenamento.
- Fluxos de revisão editorial mais elaborados.
- Controle de versões documentais apresentado na interface.
- Melhorias de observabilidade e invalidação de cache.

Essas possibilidades não devem ser consideradas funcionalidades disponíveis até que sejam implementadas e validadas.

## Critérios de qualidade

Uma alteração na plataforma deve buscar:

- Preservar a compatibilidade com os documentos existentes.
- Manter a navegação coerente com os arquivos publicados.
- Evitar a exposição de credenciais.
- Validar entradas e caminhos de arquivos.
- Preservar a legibilidade e a acessibilidade das páginas.
- Incluir testes adequados para alterações no código.

## Próximo passo

Consulte [Conceitos principais](conceitos.md) para conhecer os termos e componentes usados ao longo desta documentação.
