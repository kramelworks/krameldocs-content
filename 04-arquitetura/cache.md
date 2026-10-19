
# Cache

O krameldocs utiliza cache para reduzir consultas repetidas ao repositório de conteúdo e melhorar a eficiência do carregamento das páginas.

## Objetivo

Sem cache, requisições repetidas podem gerar chamadas desnecessárias ao GitHub.

O cache permite reutilizar dados consultados anteriormente enquanto as entradas forem consideradas válidas.

## Tempo de validade

O tempo de validade é configurado pela variável:

`DOCS_CACHE_TTL`

O valor de referência utilizado neste projeto é de 60 segundos.

O tempo efetivo de atualização depende de como o cache é aplicado aos diferentes tipos de conteúdo e do ciclo de vida do processo da aplicação.

## Funcionamento conceitual

```text
Requisição
    |
    v
Consultar cache
    |
    +---- Entrada válida ----> Reutilizar dados
    |
    +---- Sem entrada válida
                 |
                 v
            Consultar GitHub
                 |
                 v
            Armazenar resultado
                 |
                 v
            Retornar conteúdo
```

Esse fluxo é conceitual. A implementação específica determina quais dados são armazenados e como entradas expiradas são tratadas.

## Efeito sobre alterações

Quando um artigo é atualizado no GitHub, o portal pode continuar exibindo temporariamente uma versão anterior.

Isso não significa necessariamente que o commit falhou. A entrada utilizada pode ainda estar válida no cache.

## Cache em memória

O cache em memória pertence ao processo que o mantém.

Em ambientes com várias instâncias, cada instância pode ter seu próprio estado de cache. Por isso, não se deve presumir que uma atualização seja propagada instantaneamente para todas as instâncias.

## Diagnóstico de conteúdo desatualizado

Se uma alteração não aparecer:

1. Confirme que o commit foi enviado para a branch correta.
2. Verifique se a aplicação utiliza o repositório e o diretório esperados.
3. Aguarde o TTL configurado.
4. Atualize a página e verifique novamente.
5. Consulte os logs se o conteúdo continuar desatualizado.

## Ajustar o TTL

Um TTL menor pode reduzir o tempo durante o qual uma entrada antiga permanece válida, mas também pode aumentar a frequência de chamadas ao GitHub.

Um TTL maior pode reduzir as chamadas, mas aumenta a possibilidade de exibir conteúdo antigo por mais tempo.

Escolha um valor que equilibre atualidade e eficiência.

## Limitações

Cache em memória não equivale a cache distribuído e não garante sincronização imediata entre instâncias.

Qualquer alteração no mecanismo de cache deve ser validada com testes e com o comportamento observado no ambiente implantado.

## Próximo passo

Consulte [Decisões técnicas](decisoes-tecnicas.md) para registrar os motivos das principais escolhas arquiteturais.
