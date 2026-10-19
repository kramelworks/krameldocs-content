
# Instalação local

Este guia explica como preparar uma cópia local do krameldocs para desenvolvimento e validação.

## 1. Clonar o repositório

No terminal, execute:

```bash
git clone https://github.com/kramelworks-admin/krameldocs.git
cd krameldocs
```

O primeiro comando baixa o código-fonte. O segundo entra na pasta do projeto.

## 2. Instalar as dependências

Execute:

```bash
npm install
```

Aguarde a instalação terminar. Caso ocorram erros, verifique a versão do Node.js, a conectividade e as mensagens apresentadas pelo npm.

## 3. Configurar as variáveis de ambiente

Crie o arquivo `.env.local` na raiz do projeto.

Use as variáveis documentadas em [Configuração inicial](configuracao-inicial.md).

Não adicione esse arquivo ao Git. Ele pode conter credenciais de acesso ao repositório de conteúdo.

## 4. Iniciar o servidor de desenvolvimento

Execute:

```bash
npm run dev
```

Por padrão, o Next.js disponibiliza a aplicação local em:

`http://localhost:3000`

Abra esse endereço no navegador.

Se a porta padrão estiver ocupada, o terminal poderá indicar outra porta. Utilize o endereço informado pelo próprio processo.

## 5. Validar a aplicação

Depois de iniciar o projeto, confira:

- A página inicial abre.
- A rota `/docs` responde corretamente.
- Os documentos listados na navegação podem ser acessados.
- Os links internos funcionam.
- As imagens e os anexos compatíveis são exibidos.
- O terminal não apresenta erros inesperados.

## 6. Executar as verificações

Antes de enviar alterações, execute os comandos disponíveis no projeto:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Esses comandos verificam, respectivamente, problemas de lint, tipos TypeScript, testes e build de produção. Confirme no `package.json` que os scripts estão definidos na versão atual do repositório.

## Solução de problemas

Se a instalação ou a inicialização falhar:

1. Leia a mensagem completa do terminal.
2. Confirme as versões do Node.js e do npm.
3. Verifique se as dependências foram instaladas.
4. Confira as variáveis de ambiente.
5. Consulte [Problemas de configuração](../09-solucao-problemas/configuracao.md).

## Próximo passo

Após a instalação, configure o acesso ao repositório de conteúdo seguindo [Configuração inicial](configuracao-inicial.md).
