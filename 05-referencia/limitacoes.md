
# Limitações conhecidas

## Objetivo

Este documento registra as limitações funcionais e operacionais conhecidas do krameldocs, ajudando a definir expectativas e orientar melhorias.

As limitações devem ser revisadas quando a implementação evoluir.

## Formato do conteúdo

O conteúdo é escrito em Markdown com suporte a recursos adicionais de formatação.

O portal não deve ser tratado como um ambiente de execução de MDX. Componentes React ou código executável não devem ser inseridos nos documentos esperando que sejam renderizados como componentes da aplicação.

## Origem dos documentos

O conteúdo é obtido de um repositório GitHub configurado por variáveis de ambiente.

A disponibilidade da documentação depende da configuração do repositório, da branch, do diretório-base e do acesso à origem.

## Atualização do conteúdo

O cache reduz consultas repetidas ao repositório, mas pode fazer com que alterações recentes demorem a aparecer.

O intervalo configurado não deve ser interpretado como garantia absoluta de atualização em um momento exato, pois o comportamento também depende da estratégia de cache e do ambiente de execução.

## Arquivos e anexos

A entrega de recursos está sujeita às regras implementadas na rota de arquivos, incluindo limite de tamanho, extensões permitidas e validação dos caminhos.

Arquivos maiores ou de tipos não autorizados podem não ser disponibilizados pela rota atual.

## Dependência de conectividade

A leitura de conteúdo remoto pode falhar por problemas de conectividade, indisponibilidade do GitHub, limitações de acesso ou configuração incorreta.

O comportamento durante falhas depende do mecanismo de cache e do tratamento de erros da aplicação.

## Autenticação do conteúdo

O suporte a repositórios privados depende de um token válido e de permissões suficientes.

A configuração do token deve ser feita no ambiente do servidor. O portal não deve expor credenciais ao navegador.

## Edição de conteúdo

A edição dos documentos ocorre no repositório de conteúdo, e não por meio de um editor visual integrado ao portal.

O fluxo de publicação utiliza os recursos de versionamento do GitHub.

## Recursos não confirmados

Não presuma a existência de funcionalidades como:

- Editor visual de documentos.
- Sistema próprio de autenticação de leitores.
- Controle de acesso individual por documento.
- Pesquisa avançada com indexação dedicada.
- Histórico de versões acessível pela interface.
- Publicação agendada.

Esses recursos somente devem ser considerados disponíveis quando estiverem implementados e documentados.

## Como propor melhorias

Ao identificar uma limitação:

1. Descreva o comportamento atual.
2. Explique o impacto para os usuários.
3. Defina o resultado desejado.
4. Avalie alternativas e riscos.
5. Implemente testes para o novo comportamento.
6. Atualize os documentos relacionados.

## Manutenção deste documento

Revise esta lista quando uma funcionalidade for adicionada, removida ou modificada. Remova limitações que deixarem de se aplicar e registre novas restrições confirmadas pela implementação.
