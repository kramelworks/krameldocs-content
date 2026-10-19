
# Fluxo Git

## Objetivo

Padronizar o fluxo de trabalho com Git para alterações no código da aplicação e no conteúdo documental.

## Repositórios

O krameldocs utiliza repositórios separados:

- Aplicação: `kramelworks-admin/krameldocs`
- Conteúdo: `kramelworks/krameldocs-content`

Antes de executar comandos, confirme em qual repositório você está trabalhando.

## Verificar o estado

Para consultar a branch atual e as alterações locais:

```bash
git status
```

Para identificar a branch atual:

```bash
git branch --show-current
```

Confira as alterações antes de iniciar um commit.

## Atualizar a branch

Antes de começar uma tarefa, obtenha as alterações remotas conforme o fluxo adotado pelo projeto.

Em um fluxo baseado na branch `main`, um exemplo é:

```bash
git switch main
git pull
```

Se houver alterações locais, avalie como preservá-las antes de trocar de branch ou atualizar os arquivos.

## Criar uma branch de trabalho

Para uma tarefa independente:

```bash
git switch -c docs/nome-da-alteracao
```

Utilize nomes curtos e descritivos. Adapte a convenção ao padrão adotado pela equipe.

## Revisar alterações

Para visualizar as diferenças:

```bash
git diff
```

Para conferir os arquivos preparados para commit:

```bash
git diff --cached
```

Nunca inclua tokens, arquivos temporários ou alterações sem relação com a tarefa.

## Criar um commit

Prepare apenas os arquivos necessários:

```bash
git add caminho/do/arquivo
git commit -m "docs: atualiza documentação"
```

A mensagem deve descrever a finalidade da alteração.

## Publicar alterações

Para enviar a branch ao repositório remoto:

```bash
git push -u origin HEAD
```

Depois, abra um pull request quando esse for o fluxo utilizado pelo projeto. Revise as alterações antes de integrá-las à branch principal.

## Publicação de conteúdo

No repositório documental, revise também:

- O conteúdo Markdown.
- Os caminhos dos recursos.
- A estrutura do `navigation.json`.
- Os links para documentos relacionados.
- A grafia dos nomes dos arquivos.

Uma mudança de nome ou diretório pode exigir atualizações na navegação e em links existentes.

## Resolver conflitos

Se houver conflito:

1. Identifique os arquivos envolvidos.
2. Compare as alterações de cada versão.
3. Preserve o conteúdo correto.
4. Remova os marcadores de conflito.
5. Execute as verificações pertinentes.
6. Revise o resultado antes de concluir a integração.

## Boas práticas

- Mantenha commits pequenos e coerentes.
- Não misture alterações independentes sem necessidade.
- Não faça commit de segredos.
- Evite sobrescrever alterações de outras pessoas.
- Confirme o estado do repositório após operações importantes.
