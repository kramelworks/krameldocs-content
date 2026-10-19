
# Tokens e segredos

## Objetivo

Definir como armazenar, configurar, utilizar e substituir credenciais necessárias para o acesso ao repositório de conteúdo.

## Token do GitHub

A variável `GITHUB_TOKEN` pode ser utilizada pelo servidor para autenticar solicitações ao GitHub.

O token deve ter somente as permissões necessárias para a operação realizada. Para um portal que apenas lê conteúdo, evite conceder permissões de escrita quando elas não forem necessárias.

As permissões exatas dependem do tipo de token utilizado e das configurações do repositório.

## Configuração local

No ambiente de desenvolvimento, configure o token em `.env.local`, na raiz da aplicação:

```dotenv
GITHUB_TOKEN=seu_token_aqui
```

O texto acima é apenas um exemplo. Substitua-o localmente pelo valor apropriado, sem compartilhar o segredo.

Confirme que `.env.local` está excluído do controle de versão.

## Configuração em produção

Na Vercel, cadastre o token nas variáveis de ambiente do projeto.

Verifique:

- Se o nome da variável está correto.
- Se o valor foi cadastrado sem espaços acidentais.
- Se a variável está disponível no ambiente de implantação pretendido.
- Se o token tem acesso ao repositório configurado.
- Se um novo deploy é necessário após a alteração.

## Não expor segredos

Nunca:

- Utilize `NEXT_PUBLIC_GITHUB_TOKEN`.
- Inclua o token em arquivos Markdown.
- Faça commit do token.
- Insira o token em URLs.
- Imprima o valor completo em logs.
- Compartilhe capturas de tela que revelem o segredo.

## Rotação de token

Substitua o token quando houver suspeita de exposição, mudança de permissões ou necessidade operacional.

Procedimento recomendado:

1. Gere um novo token com as permissões mínimas necessárias.
2. Atualize o valor em cada ambiente que o utiliza.
3. Confirme que o portal consegue acessar o conteúdo.
4. Revogue o token antigo.
5. Verifique se não há cópias expostas em commits, logs ou arquivos.

Se um token for exposto, revogue-o imediatamente. Apagar o valor de um arquivo não invalida um token que já tenha sido comprometido.

## Diagnóstico de autenticação

Se o acesso ao conteúdo falhar:

1. Confirme se a variável está configurada.
2. Verifique se o token não expirou ou foi revogado.
3. Confira o acesso ao repositório correto.
4. Verifique as permissões necessárias para o tipo de token.
5. Analise o erro retornado sem registrar o segredo.

## Princípio de menor privilégio

Utilize uma credencial exclusiva para a finalidade do portal quando isso for adequado à operação.

Não reutilize tokens pessoais amplamente privilegiados se uma credencial restrita puder atender à necessidade.

## Revisão periódica

Revise periodicamente os tokens ativos, suas permissões e sua necessidade de uso. Remova credenciais que não sejam mais necessárias.
