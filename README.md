# Angular 9 JWT Login Authentication Example

[Angular 9 JWT Login Authentication Example](https://loizenai.com/angular-9-jwt-login-authentication-example/)

![Angular 9 JWT Login Authentication Example](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-SpringBoot-Jwt-Login-Authentication.png)

Tutorial: Angular 9 Login Authentication Example – Angular 9 + SpringBoot + MySQL/PostgreSQL JWT token Authentication
JWT Role Based Authorization with Spring Boot and Angular 9 (Spring Boot Login Example)

JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. So in tutorial ‘JWT Role Based Authorization with Spring Boot and Angular 9 (Spring Boot Login Example)’, I guide you very clearly how to implement full stack example to demonstrade an jwt token based authentication flow from frontend Angular 9 to backend: SpringBoot and MySQL.

– I give you an Epic of the application, a fullstack excutive flow from frontend – Angular 9 to backend – SpringBoot with overall architecture diagram.
– I give you an architecture diagram of SpringBoot security backend.
– I give you a working flow diagram of Angular 9 JWT Application.
– I guide you step by step how to develop a Backend SpringBoot secured RestAPIs with JWT token.
– I guide you step by step how to develop an Angular 9 JWT Token Authentication application.
– Finally, I do an integrative testing from Angular 9 JWT Authentication application to SpringBoot Backend Security RestAPIs.

## Angular Spring Boot JWT Authentication example

We will build an application, from frontend (Angular) to backend (Spring Boot), which allows users to register, login account. This application is secured with JWT (JSON Web Token) authentication and Spring Security. Then, depending on the role of current User (user, pm or admin), this system accepts what he can access:

![Angular-9-Login-Form](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Login-Form.png)

![Angular 9 Register Form](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Register-Form.png)

![Angular 9 Home Page of a User with USER_ROLE](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Home-Page-of-a-User-with-USER_ROLE.png)

![Angular 9 Content Page of a User with USER_ROLE](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Content-Page-of-a-User-with-USER_ROLE.png)

The diagram below show how our system handles User Registration and User Login processes:

![Angular 9 Spring Boot Security Jwt Token Authentication Work Process Diagram](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Spring-Boot-Security-Jwt-Token-Authentication-Work-Process-Diagram.png)

## SPRING BOOT BACK-END WITH SPRING SECURITY

This is diagram for SpringBoot Token based authentication Security/JWT classes that are separated into 3 layers:
– HTTP
– Spring Security
– REST API

![Spring Boot Security Jwt Token Authentication Architecture Diagram Back End Server
](https://loizenai.com/wp-content/uploads/2020/11/Spring-Boot-Security-Jwt-Token-Authentication-Architecture-Diagram-Back-End-Server-1.png)

– SecurityContextHolder provides access to the SecurityContext.
– SecurityContext holds the Authentication and possibly request-specific security information.
– Authentication represents the principal which includes GrantedAuthority that reflects the application-wide permissions granted to a principal.
– UserDetails contains necessary information to build an Authentication object from DAOs or other source of security data.
– UserDetailsService helps to create a UserDetails from a String-based username and is usually used by AuthenticationProvider.
– JwtAuthTokenFilter (extends OncePerRequestFilter) pre-processes HTTP request, from Token, create Authentication and populate it to SecurityContext.
– JwtProvider validates, parses token String or generates token String from UserDetails.
– UsernamePasswordAuthenticationToken gets username/password from login Request and combines into an instance of Authentication interface.
– AuthenticationManager uses DaoAuthenticationProvider (with help of UserDetailsService & PasswordEncoder) to validate instance of UsernamePasswordAuthenticationToken, then returns a fully populated Authentication instance on successful authentication.
– SecurityContext is established by calling SecurityContextHolder.getContext().setAuthentication(…​) with returned authentication object above.
– AuthenticationEntryPoint handles AuthenticationException.
– Access to Restful API is protected by HTTPSecurity and authorized with Method Security Expressions.

## ANGULAR FRONT-END WITH INTERCEPTOR

In the tutorial, “Angular 9 + Spring Boot JWT Token Based Authentication Example”, we need the Angular HTTP Interceptor to add JWT Token Based for Security authentication:

![Angular 9 Jwt Token Workflow Diagram](https://loizenai.com/wp-content/uploads/2020/11/Angular-9-Jwt-Token-Workflow-Diagram.png)

– app.component is the parent component that contains routerLink and router-outlet for routing. It also has an authority variable as the condition for displaying items on navigation bar.
– user.component, pm.component, admin.component correspond to Angular Components for User Board, PM Board, Admin Board. Each Board uses user.service to access authority data.
– register.component contains User Registration form, submission of the form will call auth.service.
– login.component contains User Login form, submission of the form will call auth.service and token-storage.service.

– user.service gets access to authority data from Server using Angular HttpClient ($http service).
– auth.service handles authentication and signup actions with Server using Angular HttpClient ($http service).
– every HTTP request by $http service will be inspected and transformed before being sent to the Server by auth-interceptor (implements HttpInterceptor).
– auth-interceptor check and get Token from token-storage.service to add the Token to Authorization Header of the HTTP Requests.

– token-storage.service manages Token inside Browser’s sessionStorage.

## Video Guide

https://youtu.be/7ZfInOvFsz0

## Tutorial Link

[Angular 9 JWT Login Authentication Example](https://loizenai.com/angular-9-jwt-login-authentication-example/)

## related posts:

- [Angular CRUD Application with SpringBoot and MySQL/PostgreSQL RestAPIs – Fullstack Angular 9-9-10 HttpClient Post/Get/Put/Delete](https://loizenai.com/angular-crud-application-with-springboot-and-mysql-postgresql-restapis-fullstack-angular-httpclient-post-get-put-delete/)
- [Build SpringBoot CRUD Application – FullStack: Frontend (Bootstrap and Ajax) to Backend (SpringBoot and MySQL/PostgreSQL database)](https://loizenai.com/build-springboot-crud-application-fullstack-frontend-bootstrap-and-ajax-to-backend-springboot-and-mysql-postgresql-database/)
- [Angular Nodejs Fullstack CRUD Application with MySQL/PostgreSQL – Angular 9-9-10 HttpClient + Nodejs Express, Sequelize ORM](https://loizenai.com/angular-nodejs-fullstack-crud-application-with-mysql-postgresql-angular-8-9-8-httpclient-client-nodejs-express-sequelize-orm/)
