
# Validação de caminhos

## Objetivo

Documentar os cuidados necessários para resolver caminhos de documentos e recursos sem permitir acesso a arquivos fora da área autorizada.

## Contexto

O krameldocs recebe caminhos derivados da navegação e de solicitações de recursos. Esses caminhos precisam ser interpretados de forma consistente com o diretório-base configurado.

A variável `DOCS_GIT_PATH` pode definir um diretório-base para o conteúdo. Quando estiver vazia, utiliza-se a raiz do repositório.

## Riscos

Uma validação inadequada pode permitir:

- Tentativas de sair do diretório de conteúdo.
- Acesso a recursos não autorizados.
- Referências malformadas ou ambíguas.
- Erros causados por diferenças de normalização entre sistemas.
- Solicitações de arquivos que não deveriam ser disponibilizados.

## Regras de validação

Ao alterar a lógica de resolução de caminhos:

1. Rejeite caminhos que tentem atravessar diretórios, como entradas com `..`.
2. Normalize os caminhos antes de utilizá-los.
3. Restrinja a resolução ao diretório-base permitido.
4. Valide os segmentos recebidos pela rota.
5. Não confie exclusivamente na validação realizada pelo navegador.
6. Trate caminhos inexistentes ou inválidos sem revelar detalhes internos.
7. Aplique as restrições também aos recursos, não apenas às páginas Markdown.

## Nomes e capitalização

Mantenha os caminhos consistentes com os nomes reais dos arquivos.

A capitalização pode afetar o resultado, especialmente em ambientes de implantação que diferenciam letras maiúsculas e minúsculas.

Exemplo:

```text
assets/arquitetura.png
```

Não presuma que `Assets/Arquitetura.png` identifica o mesmo arquivo em todos os ambientes.

## Diretório-base

Quando `DOCS_GIT_PATH` estiver configurado, confirme que documentos e recursos são resolvidos em relação à base pretendida.

Evite combinar caminhos já prefixados com o diretório-base de forma que o prefixo seja aplicado duas vezes.

## Testes recomendados

Inclua testes para:

- Caminhos válidos.
- Arquivos inexistentes.
- Caminhos vazios ou malformados.
- Tentativas de utilizar `..`.
- Segmentos com caracteres codificados.
- Nomes com espaços ou caracteres acentuados, quando suportados.
- Recursos localizados em subdiretórios.
- Caminhos incompatíveis com o diretório-base.

## Tratamento de erros

Uma solicitação inválida deve resultar em uma resposta de erro apropriada, sem fornecer informações desnecessárias sobre a estrutura interna da aplicação ou credenciais.

O status HTTP exato deve seguir o contrato implementado pela rota.

## Manutenção

Toda mudança na resolução de caminhos deve ser acompanhada de testes de regressão e revisão de segurança.
