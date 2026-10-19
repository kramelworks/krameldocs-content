
# Backup e recuperação

## Objetivo

Descrever como preservar e recuperar o código da aplicação e o conteúdo documental do krameldocs.

## Código da aplicação

O código é armazenado no repositório GitHub da aplicação:

```text
kramelworks-admin/krameldocs
```

O histórico do Git permite recuperar versões anteriores dos arquivos e revisar alterações.

## Conteúdo documental

Os documentos e recursos são mantidos separadamente no repositório:

```text
kramelworks/krameldocs-content
```

Esse repositório contém arquivos Markdown, a estrutura de navegação e os recursos associados.

## Histórico do Git

Commits e branches ajudam a recuperar versões anteriores do conteúdo.

Antes de reverter uma alteração:

1. Identifique o commit que introduziu o problema.
2. Revise as mudanças envolvidas.
3. Determine se a reversão deve afetar um arquivo ou um conjunto de arquivos.
4. Confirme que a versão recuperada é válida.
5. Teste o resultado no portal.

Evite sobrescrever alterações posteriores que ainda sejam necessárias.

## Cópias adicionais

Para requisitos de recuperação mais rigorosos, mantenha cópias adicionais dos repositórios em um local apropriado e com acesso controlado.

A estratégia de backup deve considerar:

- Frequência das cópias.
- Retenção das versões.
- Proteção contra exclusão acidental.
- Controle de acesso.
- Procedimento de restauração.
- Verificação periódica da integridade das cópias.

## Recuperação de documentos

Se um documento for removido ou alterado incorretamente:

1. Localize a última versão válida no histórico do Git.
2. Recupere o conteúdo necessário.
3. Confira os links e os recursos referenciados.
4. Atualize `navigation.json` se necessário.
5. Publique a correção.
6. Confirme que o portal apresenta o conteúdo esperado.

## Recuperação da aplicação

Se uma alteração no código causar falhas:

1. Consulte os logs do deploy.
2. Identifique a última versão funcional.
3. Avalie a reversão do deploy ou a correção do código.
4. Verifique as variáveis de ambiente.
5. Execute as verificações de qualidade.
6. Confirme o funcionamento após a recuperação.

## Credenciais

Backups não devem incluir segredos desprotegidos.

Se for necessário preservar configurações sensíveis, utilize um mecanismo apropriado de gerenciamento de segredos, com acesso restrito.

## Teste de recuperação

Uma cópia de segurança só é útil se puder ser restaurada.

Realize testes periódicos de recuperação e documente o procedimento que funcionou.

## Observação

O histórico do Git não substitui todas as formas de backup: ele pode não proteger contra perda de acesso à conta, exclusão de repositórios ou comprometimento de credenciais.
