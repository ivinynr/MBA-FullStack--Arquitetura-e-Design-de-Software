
# Aula 2 - MBA FullStack Arquitetura e Designer de Software

## Frameworks
Framework é um facilitador no desenvolvimento de software. Ele fornece uma estrutura padrão que guia o desenvolvedor e oferece componentes prontos para tarefas comuns, aumentando a produtividade e a qualidade do software.

### Action-based Frameworks:
- **Exemplo:** Struts.
- **Funcionam** com base em ações. Cada ação do usuário (como clicar em um botão) gera uma requisição que é processada por uma ação específica no servidor.
- **Vantagem:** Estrutura mais simples para fluxos diretos.
- **Desvantagem:** Pode se tornar complexo para grandes aplicações com muitos componentes interdependentes.

### Component-based Frameworks:
- **Exemplo:** JSF (JavaServer Faces).
- **Baseiam-se** em componentes reutilizáveis (botões, tabelas, etc.) que possuem estado e comportamento próprios.
- **Vantagem:** Melhor modularização e reuso de componentes.
- **Desvantagem:** Mais difícil de entender e depurar em projetos complexos.

## Servidor vs Contêiner Web
- **Servidor de Aplicação:** Oferece uma infraestrutura completa para rodar aplicações empresariais. Fornece suporte a transações, segurança, persistência, mensageria etc.
- **Contêiner Web:** Um ambiente mais leve focado apenas em aplicações web (HTTP, Servlet, JSP). Gerencia o ciclo de vida dos servlets, mapeia URLs, gerencia sessões e muito mais.

## EJB (Enterprise Java Beans)
- É uma especificação Java para o desenvolvimento de aplicações distribuídas, transacionais e seguras.
- Utilizado principalmente em aplicações robustas para resolver problemas como gestão de transações, concorrência, segurança e escalabilidade.

## JBoss
- JBoss é um servidor de aplicações (hoje chamado de WildFly nas versões mais recentes).
- Ele implementa a especificação Java EE (Enterprise Edition) e oferece suporte tanto a componentes web (Servlets, JSPs) quanto a EJBs, transações distribuídas, e muito mais.

## Tomcat
- O Apache Tomcat é um contêiner web e não um servidor de aplicação completo.
- Foca na execução de aplicações baseadas em Servlets e JSPs.
- **Levantamento de páginas web:** Hospeda e gerencia o ciclo de vida de páginas dinâmicas Java.

## Spring Framework
- Inicialmente, o Spring utilizava arquivos XML extensivos para configuração de beans, dependências e propriedades.
- Hoje, grande parte da configuração é feita através de anotações (`@Component`, `@Service`, `@Repository`, `@Autowired` etc.), seguindo o princípio de "convenção sobre configuração".

### Servlets:
- São classes Java que processam requisições HTTP no servidor. Podem ser vistos como "pequenos servidores" escutando por requisições de clientes e respondendo dinamicamente.
- O Spring introduziu mecanismos de abstração para facilitar a manipulação de servlets, como os controladores REST (`@RestController`).

### Antes do Spring (AS) vs Depois do Spring (DS)
- **Antes do Spring:** Desenvolvimento Java EE exigia muita configuração manual, escrita de EJBs complexos, dificuldades em integração e pouca flexibilidade.
- **Depois do Spring:**
  - Redução da complexidade através de Inversão de Controle (IoC) e Injeção de Dependência (DI).
  - Desenvolvimento mais ágil, modular e com menos código cerimonial.
  - Popularização de práticas como Programação Orientada a Aspectos (AOP).

## Definição de Frameworks
- Composto por bibliotecas, convenções, ferramentas e componentes prontos que guiam o desenvolvimento de sistemas.
- Um framework define o fluxo de controle da aplicação (inversão de controle — "você chama a biblioteca; o framework chama seu código").

## Kotlin
- Criado pela JetBrains, surgiu para evoluir o Java, corrigindo limitações da linguagem:
  - Melhor suporte a paralelismo e concorrência (ex.: corrotinas).
  - Sintaxe mais concisa e segura (ex.: null safety nativo).
  - Interoperabilidade total com Java.

## GoLang
- Linguagem criada pelo Google com foco em:
  - Simplicidade, desempenho e concorrência.
  - Boa opção para sistemas distribuídos, servidores e microserviços.
  - Modelo de concorrência baseado em goroutines e channels, de maneira eficiente e escalável.

## Spring e Convenção
- Spring adota o princípio de convenção sobre configuração:
  - Se você seguir convenções predefinidas, precisa escrever menos configuração manual.
  - Exemplo: Ao criar uma classe com `@Service`, o Spring automaticamente reconhece que ela é um serviço de negócio.

## Anotações
- Anotações no Spring definem o comportamento das classes e objetos.
- São responsáveis por marcar componentes que o framework deve gerenciar e instanciar.
- Exemplo: `@Component`, `@Service`, `@Repository`, `@Controller`.

## Classes Anêmicas e Não Anêmicas
- **Classes Anêmicas (Domínio Pobre):**
  - Contêm apenas atributos e getters/setters.
  - Lógica de negócio fica dispersa em outras classes.
- **Classes Ricas (Domínio Rico):**
  - Encapsulam estado e comportamento juntos.
  - A lógica de negócio reside na própria entidade, aumentando coesão e reduzindo acoplamento.

## Modelos Estruturais no Spring
1. **Camada de Modelo (Entity/Model)** → Representa os dados.
2. **Camada de Repositório (Repository)** → Acesso a dados (banco de dados).
3. **Camada de Serviço (Service)** → Lógica de negócio.
4. **Camada de Controlador (Controller)** → Entrada de requisições HTTP e coordenação de respostas.

## Endpoint
- Um endpoint é o caminho exposto por um servidor para acessar um recurso via rede (geralmente HTTP).
- Em REST, cada endpoint representa uma operação sobre um recurso.
- **Exemplo:** `GET /api/products` → Recupera todos os produtos.
- ![Fluxo-Aula-2](https://github.com/user-attachments/assets/b5427bc4-28a6-438b-bf62-8ce1211e6028)
