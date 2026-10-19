
# Testes automatizados

## Objetivo

Descrever como validar alterações no krameldocs e reduzir o risco de regressões.

## Ferramentas

O projeto utiliza Vitest para executar testes automatizados. A configuração efetiva dos testes deve ser consultada nos arquivos do repositório.

## Executar a suíte de testes

Na raiz da aplicação, execute:

```bash
npm test
```

O comando executa a suíte de testes configurada no projeto.

Consulte a saída do terminal para identificar testes aprovados, falhas e eventuais erros de configuração.

## Verificações complementares

Além dos testes automatizados, execute:

```bash
npm run lint
npx tsc --noEmit
npm run build
```

Esses comandos verificam aspectos diferentes:

- **Lint:** identifica problemas de estilo e padrões de código configurados.
- **TypeScript:** verifica a consistência dos tipos.
- **Build:** verifica se a aplicação consegue gerar a versão de produção.

Nenhuma dessas verificações substitui completamente as demais.

## O que testar

Priorize testes para as funcionalidades afetadas pela alteração.

### Navegação

- Leitura da estrutura de navegação.
- Grupos e subgrupos.
- Referências para documentos.
- Tratamento de caminhos inválidos.

### Conteúdo Markdown

- Renderização de títulos e parágrafos.
- Listas, tabelas e links.
- Blocos de código.
- Âncoras de títulos.
- Tratamento seguro de HTML.

### Integração com o GitHub

- Construção correta dos caminhos.
- Tratamento de respostas inválidas.
- Falhas de acesso à origem.
- Uso das configurações do ambiente.
- Comportamento do cache.

### Arquivos e recursos

- Caminhos válidos.
- Arquivos inexistentes.
- Extensões permitidas e bloqueadas.
- Limites de tamanho.
- Tentativas de acessar caminhos fora da área autorizada.

## Testes isolados de serviços externos

Sempre que possível, utilize simulações controladas para testar a lógica da aplicação sem depender de uma conexão real com o GitHub.

Testes que dependem de serviços externos podem falhar por indisponibilidade ou mudanças fora do controle do projeto.

## Corrigir uma falha

Quando um teste falhar:

1. Leia a mensagem de erro completa.
2. Identifique o comportamento esperado.
3. Reproduza o problema.
4. Corrija a causa, não apenas o sintoma.
5. Execute novamente o teste afetado.
6. Execute a suíte completa antes de publicar.

## Testes de regressão

Ao corrigir um defeito, adicione um teste que represente o comportamento problemático sempre que for viável.

Isso ajuda a evitar que alterações futuras reintroduzam o mesmo problema.

## Critério de conclusão

Considere uma alteração validada somente depois de executar as verificações relevantes e analisar todas as falhas. Não ignore erros apenas para concluir a publicação.
