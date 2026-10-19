
# Como contribuir

## Objetivo

Orientar contribuições para o código e para a documentação do krameldocs.

## Tipos de contribuição

As contribuições podem incluir:

- Correções de defeitos.
- Melhorias de acessibilidade e usabilidade.
- Ajustes na navegação.
- Melhorias no processamento Markdown.
- Correções de segurança.
- Atualizações de dependências.
- Melhorias nos testes.
- Correções e novos documentos.

## Escolher o repositório

Antes de começar, identifique onde a mudança deve ocorrer.

**Repositório da aplicação**

`kramelworks-admin/krameldocs`

Utilize-o para alterações no código, nas rotas, na interface, nos testes e na configuração da aplicação.

**Repositório de conteúdo**

`kramelworks/krameldocs-content`

Utilize-o para alterações nos documentos Markdown, na navegação e nos recursos publicados.

## Preparar a alteração

1. Leia a documentação relacionada à tarefa.
2. Verifique o estado do repositório.
3. Identifique o comportamento esperado.
4. Faça alterações pequenas e focadas.
5. Adicione ou atualize testes quando necessário.

## Documentação

Ao criar ou modificar um documento:

- Utilize títulos descritivos.
- Prefira instruções claras e reproduzíveis.
- Confira os comandos antes de publicá-los.
- Valide links e caminhos de arquivos.
- Atualize a navegação quando necessário.
- Evite incluir segredos ou informações privadas.
- Remova instruções que já não correspondam à implementação.

## Código

Ao contribuir com o código:

- Siga os padrões existentes.
- Preserve a separação entre interface e acesso ao conteúdo.
- Valide entradas externas.
- Trate erros de forma adequada.
- Inclua testes para novos comportamentos.
- Evite dependências desnecessárias.

## Validação

Antes de enviar uma contribuição, execute as verificações relevantes.

Na aplicação, os comandos principais são:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Confirme que os comandos terminaram corretamente e analise eventuais avisos relevantes.

## Revisão

Antes de publicar:

1. Revise as diferenças do Git.
2. Confirme que somente arquivos pertinentes foram alterados.
3. Verifique se nenhum segredo foi incluído.
4. Confira a documentação relacionada.
5. Escreva uma mensagem de commit clara.
6. Abra um pull request quando aplicável.

## Descrição da contribuição

Ao apresentar uma mudança, explique:

- Qual problema ela resolve.
- O que foi alterado.
- Como foi validada.
- Se existe algum impacto sobre compatibilidade ou configuração.

## Princípio geral

Contribuições devem melhorar o projeto sem comprometer a segurança, a consistência documental ou a facilidade de manutenção.
