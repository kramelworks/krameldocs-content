
# Comandos de desenvolvimento

## Objetivo

Este documento reúne os comandos mais utilizados para instalar dependências, executar a aplicação e validar alterações no krameldocs.

Execute os comandos na raiz do repositório da aplicação, salvo indicação contrária.

## Instalar dependências

```bash
npm install
```

Instala as dependências definidas pelo projeto.

## Executar em desenvolvimento

```bash
npm run dev
```

Inicia o servidor de desenvolvimento do Next.js. Utilize o endereço local informado no terminal para acessar o portal.

## Executar o lint

```bash
npm run lint
```

Executa as verificações de lint configuradas no projeto.

## Verificar os tipos

```bash
npx tsc --noEmit
```

Executa a verificação de tipos do TypeScript sem gerar arquivos de saída.

## Executar os testes

```bash
npm test
```

Executa a suíte de testes configurada no projeto.

## Gerar o build de produção

```bash
npm run build
```

Executa a compilação de produção do Next.js.

## Ordem sugerida de validação

Antes de publicar uma alteração, execute:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Se algum comando falhar, corrija o problema antes de considerar a alteração validada.

## Consultar os scripts disponíveis

Os scripts disponíveis dependem do conteúdo de `package.json`.

Para conferir os scripts registrados:

```bash
npm run
```

Não adicione comandos a este documento sem verificar se eles existem na versão atual do projeto.

## Observações

- Execute os comandos no repositório correto.
- Mantenha as dependências consistentes com o arquivo de lock.
- Não inclua tokens ou outros segredos nos comandos registrados no histórico do terminal.
- Consulte a mensagem completa de erro antes de alterar configurações.
