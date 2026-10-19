
# Primeira execução

Este guia apresenta os procedimentos para verificar se o krameldocs está funcionando após a instalação e a configuração inicial.

## 1. Iniciar a aplicação

Na pasta do projeto, execute:

```bash
npm run dev
```

Aguarde o terminal indicar que o servidor de desenvolvimento está pronto.

Por padrão, a aplicação estará disponível em `http://localhost:3000`.

## 2. Acessar a página inicial

Abra o endereço local no navegador.

Confirme que a página inicial é apresentada sem erros.

## 3. Acessar a documentação

Abra a rota:

`http://localhost:3000/docs`

Verifique se a área de documentação carrega corretamente.

## 4. Verificar a navegação

Confira se os grupos definidos em `navigation.json` são exibidos.

Cada item de página precisa apontar para um arquivo Markdown existente no repositório de conteúdo.

Durante a criação inicial da documentação, alguns itens podem ainda não estar disponíveis. Isso é esperado enquanto os artigos não tiverem sido criados.

## 5. Abrir um artigo

Selecione uma página existente na navegação.

Verifique se:

- O título está correto.
- O conteúdo Markdown foi renderizado.
- Os títulos e as listas estão formatados.
- Os blocos de código apresentam a formatação esperada.
- Os links internos apontam para os destinos corretos.

## 6. Verificar imagens e anexos

Caso o documento tenha imagens ou links para arquivos, confirme se eles são carregados.

Se um recurso não aparecer, confira o caminho, o nome do arquivo, a extensão e o tamanho.

## 7. Verificar o terminal

Observe o terminal durante a navegação.

Mensagens de erro podem indicar problemas de configuração, acesso ao GitHub ou referências a arquivos inexistentes.

Não exponha tokens ou outros segredos ao compartilhar logs.

## 8. Validar a versão de produção

Antes de publicar alterações, execute as verificações disponíveis no projeto:

```bash
npm run lint
npx tsc --noEmit
npm test
npm run build
```

Todos os comandos devem terminar sem erros para que a alteração seja considerada validada.

## Resultado esperado

Ao concluir este procedimento, a aplicação deve estar acessível localmente e conseguir apresentar os documentos existentes no repositório configurado.

## Próximo passo

Consulte [Estrutura do conteúdo](../03-guias/estrutura-do-conteudo.md) para compreender como organizar os arquivos documentais.
