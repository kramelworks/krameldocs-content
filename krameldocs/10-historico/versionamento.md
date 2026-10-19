
# Versionamento

## Objetivo

Definir orientações para identificar e comunicar versões do krameldocs.

## Código e conteúdo

O projeto possui dois repositórios independentes:

- Aplicação: `kramelworks-admin/krameldocs`
- Conteúdo: `kramelworks/krameldocs-content`

Cada repositório possui seu próprio histórico de commits. Uma alteração documental não precisa necessariamente gerar uma nova versão do código da aplicação.

## Commits

Os commits registram alterações pontuais e permitem rastrear sua origem.

Utilize mensagens que descrevam claramente a finalidade da mudança.

Exemplos:

```text
docs: atualiza guia de instalação
fix: corrige resolução de arquivos
feat: melhora navegação da documentação
```

Os exemplos ilustram uma convenção de mensagens, não uma exigência automática do projeto.

## Tags e versões

Se o projeto adotar versões formais, utilize tags Git para identificar os pontos correspondentes no histórico.

A convenção de versionamento deve ser definida pela equipe e aplicada de forma consistente.

Não declare uma versão oficial sem que ela tenha sido efetivamente criada e publicada.

## Mudanças incompatíveis

Mudanças que alterem rotas, formatos de configuração ou contratos de integração devem ser identificadas e documentadas.

Antes de publicar uma mudança incompatível:

1. Identifique os consumidores afetados.
2. Avalie alternativas de migração.
3. Atualize os documentos pertinentes.
4. Execute os testes.
5. Descreva as alterações no changelog.

## Versionamento do conteúdo

O histórico do repositório documental permite recuperar versões anteriores de arquivos Markdown, de `navigation.json` e dos recursos armazenados no Git.

Ao mover ou renomear documentos, confira também os caminhos referenciados pela navegação e por outros documentos.

## Publicação e rastreabilidade

Quando necessário, registre no changelog a versão, a data ou o commit que identifica uma publicação importante.

Mantenha informações suficientes para relacionar o comportamento observado no portal à versão do código e do conteúdo.

## Boas práticas

- Não confunda o número de um commit com uma versão de produto.
- Não reutilize tags de versões publicadas sem um procedimento explícito.
- Preserve o histórico dos repositórios.
- Registre mudanças incompatíveis.
- Mantenha a documentação coerente com o comportamento realmente publicado.
