
# Problemas de build e deploy

## Objetivo

Orientar o diagnóstico de falhas de compilação e implantação do krameldocs.

## Build local

Execute os comandos de validação na raiz da aplicação:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Identifique qual etapa falhou e corrija a causa antes de repetir o processo.

## Falha de dependências

Se o projeto não conseguir instalar ou resolver dependências:

1. Confira a versão do Node.js e do npm.
2. Verifique o arquivo `package.json`.
3. Confira o arquivo de lock.
4. Procure mensagens de incompatibilidade.
5. Evite remover o arquivo de lock sem uma justificativa clara.

## Erros de TypeScript

Leia a mensagem de erro e identifique o arquivo e o tipo incompatível.

Corrija o tipo ou o código responsável sem recorrer a conversões inseguras apenas para eliminar o erro.

## Testes com falha

Execute o teste afetado e determine se a causa está no código, na configuração ou em uma dependência externa.

Depois de corrigir o problema, execute novamente a suíte completa.

## Deploy com falha na Vercel

1. Abra os detalhes do deploy.
2. Consulte os logs de build.
3. Identifique a primeira falha relevante.
4. Compare com o último deploy funcional.
5. Reproduza o erro localmente quando possível.
6. Publique uma correção e acompanhe o resultado.

## Aplicação publicada, mas com erro

Se o build tiver sido concluído, mas as páginas falharem, confira:

- As variáveis de ambiente.
- O acesso ao repositório de conteúdo.
- A branch e o diretório-base.
- Os logs de execução.
- A disponibilidade dos recursos.

## Diferenças entre ambientes

Uma falha que ocorre somente em produção pode estar relacionada a variáveis ausentes, permissões, cache, diferenças de sistema operacional ou comportamento do ambiente de execução.

Não conclua que o problema está resolvido apenas porque a aplicação funciona localmente.

## Recuperação

Se um deploy introduzir uma falha crítica, avalie a reversão para uma versão funcional enquanto prepara a correção.

Depois da recuperação, investigue a causa e adicione testes preventivos quando apropriado.

## Encerramento do incidente

Confirme que as páginas, os documentos e os recursos afetados funcionam no ambiente publicado. Registre a causa e a solução para facilitar diagnósticos futuros.
