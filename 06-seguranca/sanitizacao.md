
# Sanitização e renderização de conteúdo

## Objetivo

Definir cuidados para processar documentos Markdown e apresentá-los no navegador com segurança.

## Conteúdo como entrada

Os documentos são armazenados no repositório GitHub, mas isso não significa que todo conteúdo deva ser considerado automaticamente seguro.

Alterações acidentais, conteúdo copiado de fontes externas ou entradas maliciosas podem introduzir HTML ou marcação perigosa.

## Markdown e HTML

O portal processa Markdown e utiliza ferramentas do ecossistema Remark e Rehype.

A configuração de processamento deve ser revisada para confirmar como HTML embutido é tratado e se a sanitização necessária está efetivamente habilitada.

Não presuma que todo pipeline de Markdown sanitiza HTML automaticamente.

## Regras de segurança

- Evite permitir HTML arbitrário sem necessidade.
- Utilize sanitização adequada quando HTML for aceito.
- Não habilite execução de scripts a partir do conteúdo.
- Revise plugins adicionados ao pipeline de processamento.
- Valide URLs de links e recursos conforme as regras do projeto.
- Não introduza funções de renderização que interpretem conteúdo como código executável.
- Mantenha as dependências de processamento atualizadas.

## Links externos

Links para sites externos devem ser avaliados conforme a política de conteúdo do portal.

Se forem abertos em uma nova aba, confira as proteções adequadas para evitar que a página de destino controle a página de origem.

## Imagens e arquivos

Imagens e anexos devem respeitar as regras da rota de arquivos.

A validação de extensão e tamanho é importante, mas não substitui outras medidas de segurança necessárias para o formato servido.

## SVG

Arquivos SVG podem conter recursos ativos e exigem atenção especial.

Antes de permitir ou servir SVG, verifique a política aplicada à sua entrega e se o tratamento é apropriado para conteúdo potencialmente não confiável.

## Revisão do pipeline

Ao modificar o processamento Markdown:

1. Identifique todos os plugins envolvidos.
2. Verifique a ordem de execução.
3. Confirme o comportamento para HTML embutido.
4. Teste links e atributos perigosos.
5. Teste blocos de código e marcações válidas.
6. Execute a suíte de testes e o build.

## Testes recomendados

Inclua casos para:

- Markdown comum.
- Blocos de código.
- Links válidos.
- HTML embutido.
- URLs com esquemas não permitidos.
- Atributos HTML potencialmente perigosos.
- Conteúdo malformado.

Os testes devem confirmar que a formatação legítima continua funcionando sem permitir comportamentos inseguros.

## Atualização deste documento

Descreva aqui o comportamento efetivamente implementado após alterações no pipeline. Não declare que uma medida de sanitização está ativa sem confirmar sua configuração no código.
