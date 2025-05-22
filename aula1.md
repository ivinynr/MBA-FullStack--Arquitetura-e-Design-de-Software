
# Aula 1 - MBA FullStack Arquitetura e Designer de Software



# 1. Fundamentos do Desenvolvimento Web

## 🔁 Cliente x Servidor
No desenvolvimento web, a comunicação entre o cliente (navegador ou app) e o servidor (onde a lógica de negócios e o banco de dados são armazenados) é a base. O cliente faz a requisição e o servidor processa e retorna a resposta, geralmente com dados ou um status de operação.

- **Cliente**: Envia a requisição ao servidor, por exemplo, quando um usuário acessa um site ou envia um formulário.
- **Servidor**: Recebe a requisição, executa as operações necessárias (como consultar um banco de dados) e retorna uma resposta ao cliente.

##  Comunicação:
- **Síncrona**: O cliente faz uma requisição e aguarda a resposta antes de continuar a execução. Isso é típico em requisições simples, onde a sequência de ações depende da resposta.
  
  - **Exemplo**: Em uma busca no Google, o usuário aguarda os resultados antes de realizar outra ação.

- **Assíncrona**: O cliente faz uma requisição e pode continuar realizando outras ações enquanto aguarda a resposta do servidor. Isso torna a experiência mais fluida e interativa.

  - **Exemplo**: Usar AJAX para carregar novos itens de uma lista sem precisar recarregar a página inteira.

### 📌 Exemplo:
AJAX, por exemplo, carrega dinamicamente uma tabela com dados sem precisar recarregar a página inteira, mantendo a experiência do usuário mais interativa.

---

#  2. Modelos Arquiteturais

Os modelos arquiteturais descrevem como os componentes de um sistema são organizados e interagem entre si.

- **Monolítico**: Um único bloco onde todos os componentes da aplicação são interligados. É simples de começar, mas pode ser difícil de escalar e modificar à medida que o sistema cresce. Qualquer mudança pode afetar todas as partes do sistema.
  
  - **Exemplo**: Uma aplicação tradicional onde todas as funcionalidades (autenticação, processamento de pedidos, etc.) estão no mesmo código-fonte.

- **Modularizado**: Embora o sistema ainda seja monolítico, ele é dividido em módulos que se comunicam entre si. Isso facilita o desenvolvimento e a manutenção, mas ainda não resolve os desafios de escalabilidade.
  
  - **Exemplo**: Uma aplicação onde diferentes funcionalidades (autenticação, processamento de pagamentos, etc.) são implementadas em módulos distintos dentro do mesmo código.

- **Microserviços**: O sistema é dividido em pequenos serviços independentes que comunicam entre si, geralmente via rede. Cada microserviço pode ser desenvolvido, implantado e escalado independentemente.

  - **Exemplo**: Um e-commerce que possui um serviço para o carrinho de compras, outro para o processamento de pagamentos e outro para o gerenciamento de produtos, todos trabalhando juntos, mas de forma independente.

---

# 3. HTTP – Métodos e Status Codes

## Métodos HTTP:
Esses métodos definem o tipo de operação que o cliente quer realizar no servidor. Cada operação é mapeada para um tipo de método HTTP.

- **GET**: Recupera dados do servidor. Exemplo: visualizar um produto ou uma página de um blog.
- **POST**: Envia dados ao servidor para criar um novo recurso. Exemplo: enviar um formulário de cadastro.
- **PUT**: Substitui um recurso existente por novos dados completos. Exemplo: atualizar o perfil de um usuário.
- **PATCH**: Atualiza parcialmente um recurso. Exemplo: atualizar apenas a foto de perfil do usuário.
- **DELETE**: Remove um recurso. Exemplo: excluir uma conta de usuário.

## Status Codes:
Os status codes HTTP são números que indicam o resultado da requisição do cliente.

- **200** OK: A requisição foi bem-sucedida.
- **201** Created: Um novo recurso foi criado com sucesso.
- **400** Bad Request: A requisição foi malformada ou incompleta.
- **401** Unauthorized: O cliente não tem permissão para acessar o recurso.
- **404** Not Found: O recurso solicitado não foi encontrado.
- **500** Internal Server Error: Ocorreu um erro no servidor.

### 📌 Exemplo:
Se um cliente faz uma requisição para criar um produto com o método POST em `/produtos`, e o produto é criado com sucesso, o servidor responde com **201 Created**.

---

# 4. JWT (JSON Web Token)

O **JWT** é um formato compactado e seguro para transmitir informações entre partes. Ele é amplamente utilizado para autenticação em APIs.

- **Autenticação**: O cliente envia o token para cada requisição, garantindo que ele é quem diz ser, sem precisar fazer login em todas as requisições.
- **Codificado**: O token é codificado em Base64 e contém informações como o ID do usuário, data de expiração, entre outros.
- **Validação**: Cada requisição autenticada inclui um JWT, que o servidor valida para garantir que a requisição é legítima e não foi modificada.

### 📌 Exemplo:
Quando o cliente faz login, o servidor gera um JWT com informações do usuário. Esse token é enviado ao cliente, que o inclui em cada requisição subsequente (no cabeçalho HTTP), permitindo que o servidor valide a autenticidade da requisição.

---

# 5. Protocolos de Comunicação

Os protocolos de comunicação definem como os dados são trocados entre sistemas. Os mais comuns são:

- **TCP (Transmission Control Protocol)**: Confiável e orientado à conexão, garantindo que os dados sejam entregues corretamente. É utilizado em protocolos como HTTP e FTP.

  - **Exemplo**: Quando você acessa um site, os dados da página são transmitidos via TCP, garantindo que não haja perda de dados.

- **UDP (User Datagram Protocol)**: Protocolo não orientado à conexão, mais rápido, mas sem garantias de entrega. É usado quando a velocidade é mais importante que a confiabilidade.

  - **Exemplo**: Em transmissões de vídeo ao vivo ou jogos online, a perda de alguns pacotes de dados é aceitável.

- **HTTP**: Protocolo da web que funciona sobre TCP, sendo utilizado na comunicação entre clientes e servidores na web.

### 📌 Exemplo:
As chamadas de API REST usam o protocolo **HTTP** sobre **TCP** para garantir que os dados sejam transferidos corretamente entre cliente e servidor.

---

# 6. Gerenciadores de Dependência

Gerenciadores de dependência são ferramentas que automatizam o processo de baixar, configurar e manter as bibliotecas que um projeto necessita.

- **Maven**: Utiliza arquivos XML (pom.xml) para definir as dependências. É amplamente utilizado no ecossistema Java.
  
- **Gradle**: Usa uma linguagem de configuração baseada em Groovy ou Kotlin (build.gradle). É mais flexível que o Maven e é conhecido por ser mais rápido e fácil de configurar.

### 📌 Exemplo:
Ao trabalhar em um projeto Java, você pode adicionar o Spring Framework no arquivo `pom.xml` se estiver usando Maven, e ele automaticamente fará o download da versão correta do Spring junto com todas as dependências necessárias.

---

# 7. Princípios SOLID

O **SOLID** é um conjunto de princípios de design de software que visa melhorar a legibilidade, manutenção e escalabilidade do código.

- **S**: **Single Responsibility Principle (SRP)** - Cada classe deve ter uma única responsabilidade.
- **O**: **Open/Closed Principle (OCP)** - Entidades de software devem ser abertas para extensão, mas fechadas para modificação.
- **L**: **Liskov Substitution Principle (LSP)** - Objetos de uma classe derivada devem ser substituíveis por objetos da classe base.
- **I**: **Interface Segregation Principle (ISP)** - Muitas interfaces específicas são melhores que uma única interface geral.
- **D**: **Dependency Inversion Principle (DIP)** - Dependa de abstrações, não de implementações concretas.

**Objetivo**: Aplicar esses princípios ajuda a criar sistemas mais modulares, reutilizáveis e de fácil manutenção.

---

# 8. Escalabilidade: Horizontal e Vertical

A escalabilidade se refere à capacidade de um sistema em lidar com um aumento de carga. Existem duas abordagens principais:

- **Escalabilidade Vertical**: Envolve melhorar o poder de uma única máquina, como adicionar mais memória ou processadores. É mais simples, mas tem um limite físico.

  - **Exemplo**: Aumentar a capacidade de um servidor para lidar com mais requisições.

- **Escalabilidade Horizontal**: Envolve adicionar mais máquinas ao sistema. A carga é distribuída entre elas, o que permite escalar indefinidamente.

  - **Exemplo**: Adicionar mais servidores a uma aplicação web para distribuir o tráfego entre eles.

---

# 9. Exercício: Exercite o que aprendeu

Agora, para testar seus conhecimentos, tente o seguinte exercício:

1. **Crie um sistema simples de cadastro de usuários**:
   - Implemente um endpoint para **POST** que cria um novo usuário.
   - O usuário deve ter os campos `nome`, `email` e `senha`.
   - Use **JWT** para autenticação do usuário nas requisições subsequentes.
   - O sistema deve ser escalável. Considere o uso de **microserviços** para o gerenciamento de usuários e outra parte para o gerenciamento de autenticação.

2. **Desenhe a arquitetura do sistema** usando os princípios SOLID e considerando a escalabilidade horizontal.

3. **Teste a escalabilidade**:
   - Para escalabilidade **vertical**,
