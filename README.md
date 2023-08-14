# parking-control-api

Projeto desenvolvido no vídeo [Spring Security | Curso 2022](https://youtu.be/t6prPki7daU), onde vamos implementar na prática autenticação e controle de acesso com Spring Security em uma aplicação Spring Boot. 

Vamos focar detalhadamente na configuração do Spring Security para implementar Basic Auth utilizando a sua configuração default a princípio, e posteriormente uma autenticação via base de dados com JPA. Também vamos inserir o controle de acesso via Roles tanto a nível global quanto a nível de métodos nos controllers, utilizando .antMatchers e @PreAuthorize respectivamente.

## Introdução

A API de Controle de Estacionamento foi desenvolvida para simplificar e aprimorar a gestão de vagas de estacionamento em um ambiente de condomínio. Ela oferece recursos para criar, visualizar, atualizar e excluir registros de vagas de estacionamento, garantindo uma experiência eficiente e organizada para administradores e usuários.

## Endpoints

O Controlador de Vagas de Estacionamento expõe os seguintes endpoints:

- **POST** /parking-spot: Crie uma nova vaga de estacionamento. Requer autorização ROLE_ADMIN.
- **GET** /parking-spot: Recupere uma lista paginada de todas as vagas de estacionamento. Requer autorização ROLE_ADMIN ou ROLE_USER.
- **GET** /parking-spot/{id}: Recupere detalhes de uma vaga de estacionamento específica por ID. Requer autorização ROLE_ADMIN ou ROLE_USER.
- **DELETE** /parking-spot/{id}: Exclua uma vaga de estacionamento por ID. Requer autorização ROLE_ADMIN.
- **PUT** /parking-spot/{id}: Atualize os detalhes de uma vaga de estacionamento por ID. Requer autorização ROLE_ADMIN.

## Autenticação e Autorização

A API utiliza o Spring Security para autenticação e autorização. Os seguintes papéis são definidos:

- ROLE_ADMIN: Permite acesso completo a todos os endpoints.
- ROLE_USER: Permite acesso aos endpoints somente leitura (operações GET).

Para testar os endpoints da API, você pode usar ferramentas como **cURL** ou **Postman**. Certifique-se de incluir os cabeçalhos de autorização apropriados com base no papel que deseja testar.

## Referências:

Spring Security sem WebSecurityConfigurerAdapter: https://spring.io/blog/2022/02/21/spring-security-without-the-websecurityconfigureradapter

CSRF Protection: https://docs.spring.io/spring-security/site/docs/5.0.x/reference/html/csrf.html#when-to-use-csrf-protection

Interceptor Postman: https://learning.postman.com/docs/sending-requests/capturing-request-data/interceptor/#installing-interceptor

UUID Generator: https://www.uuidgenerator.net/