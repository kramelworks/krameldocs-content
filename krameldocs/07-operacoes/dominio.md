
# Domínio personalizado

## Objetivo

Documentar a configuração e a validação do domínio público do krameldocs.

## Domínio planejado

O domínio definido para o portal é:

```text
docs.kramelworks.com.br
```

O domínio deve ser associado ao projeto da aplicação na Vercel.

## Adicionar o domínio

1. Abra o projeto na Vercel.
2. Acesse as configurações do projeto.
3. Abra a seção de domínios.
4. Adicione `docs.kramelworks.com.br`.
5. Consulte as instruções DNS fornecidas pela Vercel.
6. Configure os registros necessários no provedor DNS responsável pelo domínio.
7. Aguarde a propagação e a validação.

Os valores exatos dos registros devem ser obtidos na configuração apresentada pela Vercel. Não utilize valores copiados de outro projeto sem confirmação.

## Configuração DNS

A Vercel informa quais registros devem ser criados para associar o domínio ao projeto.

Antes de alterar o DNS:

- Confira se está editando a zona DNS correta.
- Verifique se já existem registros para o subdomínio.
- Evite remover registros que atendam a outros serviços.
- Siga os valores indicados para o domínio específico.

## HTTPS

Após a validação do domínio, confira se o HTTPS está ativo e se o certificado foi provisionado corretamente.

Acesse o endereço utilizando `https://` e verifique se o navegador não apresenta alertas de certificado.

## Validação

Quando o domínio estiver configurado:

1. Acesse `https://docs.kramelworks.com.br`.
2. Confirme que a página inicial abre.
3. Teste `/docs`.
4. Abra documentos internos.
5. Verifique imagens e PDFs.
6. Confirme que os links utilizam o domínio esperado.
7. Verifique se a Vercel indica o domínio como validado.

## Diagnóstico

### Domínio não resolve

Confira os registros DNS e aguarde a propagação, conforme necessário.

### Domínio aponta para o projeto errado

Revise a associação do domínio nas configurações da Vercel e os registros DNS.

### HTTPS não funciona

Consulte o estado de validação do domínio e do certificado na Vercel.

## Manutenção

Se o domínio mudar, atualize a configuração de hospedagem e revise os links absolutos presentes na documentação e em outros recursos.
