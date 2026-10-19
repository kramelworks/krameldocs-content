
# Apresentação do krameldocs

O **krameldocs** é uma plataforma de documentação técnica projetada para organizar, publicar e manter a documentação de sistemas de software em um único portal.

A plataforma utiliza arquivos Markdown armazenados em repositórios GitHub para separar o conteúdo documental do código responsável por apresentá-lo. Essa abordagem permite que a documentação seja atualizada por meio do fluxo normal de versionamento, revisão e publicação do Git.

## Objetivo da plataforma

O objetivo do krameldocs é oferecer uma estrutura consistente para documentar múltiplos sistemas, produtos e aplicações, mantendo a documentação organizada, navegável e fácil de atualizar.

Cada sistema possui uma área própria na árvore de navegação. Dessa forma, novos sistemas podem ser adicionados ao portal sem misturar seus artigos, procedimentos e referências técnicas.

## Principais características

- **Documentação em Markdown:** conteúdo escrito em arquivos de texto simples, fáceis de revisar e versionar.
- **Navegação hierárquica:** organização por sistemas, categorias, grupos e páginas.
- **Conteúdo separado da aplicação:** os artigos são armazenados em um repositório GitHub independente.
- **Versionamento:** alterações na documentação podem ser acompanhadas pelo histórico do Git.
- **Integração com GitHub:** a aplicação consulta os arquivos do repositório de conteúdo.
- **Suporte a recursos:** páginas podem incluir tabelas, listas, blocos de código, imagens e anexos compatíveis.
- **Publicação centralizada:** diferentes sistemas podem compartilhar o mesmo portal de documentação.
- **Arquitetura extensível:** a estrutura pode evoluir conforme novas necessidades de documentação surgirem.

## Organização da documentação

A navegação do portal é definida pelo arquivo `navigation.json`.

O primeiro nível representa o nome do sistema documentado. Abaixo dele, as informações são agrupadas em categorias padronizadas, como:

1. Visão geral.
2. Primeiros passos.
3. Guias de uso.
4. Arquitetura.
5. Referência técnica.
6. Segurança.
7. Implantação e operações.
8. Desenvolvimento.
9. Solução de problemas.
10. Histórico.

Essa estrutura fornece uma base comum para documentar os sistemas atuais e futuros.

## Separação entre aplicação e conteúdo

O projeto utiliza dois repositórios independentes.

| Repositório | Responsabilidade |
| --- | --- |
| [krameldocs](https://github.com/kramelworks-admin/krameldocs) | Código-fonte da plataforma, interface, rotas e lógica de renderização. |
| [krameldocs-content](https://github.com/kramelworks/krameldocs-content) | Artigos Markdown, arquivo de navegação, imagens e anexos documentais. |

Essa separação permite modificar a documentação sem precisar alterar o código da aplicação a cada atualização editorial.

## Público-alvo

O krameldocs destina-se a:

- Desenvolvedores responsáveis pela implementação e manutenção dos sistemas.
- Equipes técnicas que precisam consultar arquiteturas, APIs e configurações.
- Administradores responsáveis pela implantação e operação das aplicações.
- Autores que produzem e mantêm documentação técnica.
- Pessoas que precisam consultar procedimentos, guias e soluções de problemas.

## Princípios de organização

A documentação deve seguir alguns princípios fundamentais:

- **Clareza:** explicar conceitos e procedimentos de forma direta.
- **Consistência:** utilizar a mesma organização entre sistemas sempre que possível.
- **Rastreabilidade:** manter o conteúdo versionado.
- **Manutenibilidade:** facilitar a atualização e remoção de informações obsoletas.
- **Segurança:** não incluir credenciais, tokens ou informações confidenciais nos artigos.
- **Precisão:** documentar comportamentos existentes e identificar claramente funcionalidades planejadas.

## Evolução da plataforma

O krameldocs foi estruturado para começar com a documentação de seu próprio funcionamento e permitir a inclusão gradual de outros sistemas.

A evolução da plataforma deve preservar a separação entre conteúdo e aplicação, manter a navegação consistente e garantir que novos recursos sejam acompanhados de documentação atualizada.

## Próximo passo

Consulte [Objetivos e funcionalidades](objetivos-e-funcionalidades.md) para conhecer o escopo funcional da plataforma e os recursos disponíveis na versão atual.
