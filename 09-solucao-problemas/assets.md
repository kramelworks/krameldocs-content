
# Problemas com imagens e anexos

## Objetivo

Orientar o diagnóstico de imagens, PDFs e outros arquivos que não são exibidos corretamente no portal.

## Conferir se o arquivo existe

Verifique se o recurso está presente no repositório de conteúdo e se foi publicado na branch configurada.

Confira a grafia exata do nome, a extensão e os diretórios.

## Conferir o caminho no Markdown

Exemplo de imagem:

```markdown
![Arquitetura](assets/arquitetura.png)
```

Exemplo de link para PDF:

```markdown
[Consultar manual](assets/manual.pdf)
```

Os caminhos devem seguir as regras de resolução de recursos da aplicação. Na configuração atual, os exemplos utilizam caminhos relativos à raiz do conteúdo.

## Verificar a rota

Os recursos são disponibilizados pela rota:

```text
/api/docs-assets/[...path]
```

Abra as ferramentas de desenvolvedor do navegador e confira a solicitação do arquivo.

Observe o status HTTP e a resposta, sem presumir um status específico para todos os tipos de erro.

## Extensão não permitida

A rota aplica uma lista de extensões autorizadas. Um arquivo fora dessa lista pode ser recusado.

A lista documentada inclui PNG, JPEG, GIF, WebP, SVG, ICO, PDF, TXT, CSV, JSON e ZIP. Confirme as extensões efetivamente permitidas no código.

## Arquivo muito grande

A implementação atual estabelece um limite de 2 MB para os arquivos entregues pela rota.

Se o arquivo exceder esse limite, considere reduzi-lo ou utilizar uma solução de armazenamento apropriada para arquivos maiores.

Não aumente o limite sem avaliar os impactos de desempenho e segurança.

## Problemas com imagens

Se uma imagem não aparecer:

1. Confira o caminho e a capitalização.
2. Verifique se o arquivo foi publicado.
3. Abra diretamente a URL do recurso.
4. Confira o formato e o tamanho.
5. Consulte a resposta da rota e os logs.

## Problemas com PDFs

Se um PDF não abrir:

1. Confirme que o arquivo existe.
2. Confira o link no Markdown.
3. Verifique a extensão e o tamanho.
4. Teste a URL do recurso.
5. Confirme que o arquivo é um PDF válido.

## Mudanças recentes

Se um recurso recém-publicado não aparecer, confira o commit, a branch, o diretório-base e o comportamento do cache.

## Segurança

Não contorne as validações de caminhos, extensões ou tamanho para resolver um problema isolado sem antes avaliar a causa.

## Prevenção

Mantenha os recursos organizados, utilize nomes descritivos e confira todos os links após mover ou renomear arquivos.
