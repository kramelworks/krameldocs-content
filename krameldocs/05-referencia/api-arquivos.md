
# API de arquivos

## Objetivo

A rota de arquivos permite que o navegador acesse recursos armazenados no repositório de conteúdo por meio da aplicação krameldocs.

O endpoint é:

```text
/api/docs-assets/[...path]
```

## Usos comuns

A rota pode ser utilizada para disponibilizar arquivos como:

- Imagens de diagramas e capturas de tela.
- Documentos PDF.
- Arquivos de texto.
- Arquivos CSV e JSON.
- Arquivos ZIP.

A disponibilidade de cada formato depende da lista de extensões permitidas pela implementação.

## Referenciando recursos

Os documentos Markdown podem conter imagens e links para arquivos.

Exemplo de imagem:

```markdown
![Diagrama da arquitetura](assets/arquitetura.png)
```

Exemplo de link para PDF:

```markdown
[Consultar o manual](assets/manual.pdf)
```

A aplicação deve resolver esses caminhos para a rota de arquivos de acordo com as regras de processamento de conteúdo implementadas.

## Repositórios privados

Quando o repositório de conteúdo é privado, a aplicação pode intermediar a leitura dos arquivos utilizando a autenticação configurada no servidor.

O token não deve ser enviado ao navegador nem incluído em URLs públicas.

## Restrições

A implementação atual estabelece restrições para a entrega de arquivos:

- Limite de tamanho de 2 MB.
- Lista permitida de extensões.
- Validação do caminho solicitado.
- Bloqueio de tentativas de sair do diretório permitido.

A lista documentada de extensões inclui PNG, JPEG, GIF, WebP, SVG, ICO, PDF, TXT, CSV, JSON e ZIP. Confirme a lista no código antes de alterá-la.

## Segurança

Ao modificar a rota, preserve os seguintes princípios:

1. Validar os caminhos recebidos.
2. Impedir traversal de diretórios, como tentativas de usar `..`.
3. Restringir os arquivos aos formatos permitidos.
4. Aplicar o limite de tamanho definido.
5. Evitar expor credenciais, mensagens internas ou dados privados.
6. Manter o token do GitHub exclusivamente no servidor.

## Diagnóstico

Se um recurso não carregar:

1. Confirme que o arquivo existe no repositório.
2. Verifique a capitalização do nome e da extensão.
3. Confira se o caminho é relativo à raiz correta do conteúdo.
4. Verifique se a extensão é permitida.
5. Confira o tamanho do arquivo.
6. Analise a resposta da rota e os logs do servidor.

## Alterações na API

Mudanças na rota podem afetar documentos já publicados. Antes de alterar caminhos, limites ou extensões, verifique os documentos que fazem referência aos recursos e execute os testes automatizados.
