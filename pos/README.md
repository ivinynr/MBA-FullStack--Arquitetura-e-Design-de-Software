# Commit inicial do projeto

## Necessidades do projeto

- Estruturar a aplicação separando corretamente as camadas (Controller, Service, Entity, DTO, etc.).
- Garantir que cada camada tenha sua própria representação de dados, mantendo a independência das estruturas de objetos.
- Impedir modificações nas informações internas de cada estrutura entre camadas.

## Como faria para que a camada de serviço fosse chamada na camada de controller sabendo que as estruturas dos objetos de cada camada são independentes e que as informações contidas nessas estruturas distintas não podem ser modificadas?

Para resolver esse cenário, usaria um **mapper** (ou transformador de objetos). O objetivo do mapper seria converter o objeto recebido pela Controller (normalmente um DTO ou Request Object) em um objeto apropriado para a Service (normalmente um Model ou Entity).

Existem duas abordagens:

- **Manual Mapping**: Criar classes utilitárias específicas para mapear manualmente os campos entre objetos.
- **Automated Mapping**: Utilizar bibliotecas como **MapStruct** ou **ModelMapper** para automatizar essa conversão de forma segura e consistente.

Dessa forma:
- A Controller apenas recebe a requisição e transforma o objeto para a estrutura esperada pela Service.
- A Service opera com a estrutura que ela entende, sem expor ou depender da estrutura da Controller.
- A independência das camadas é preservada e as informações originais são mantidas imutáveis durante o fluxo.
