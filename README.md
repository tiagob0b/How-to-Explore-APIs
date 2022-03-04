# How to Explore APIs 🎯
The idea of this repository is to assist in studies and ways of exploring the API environment.

Before we start with the API exploration phase, it is necessary to have a knowledge base, so I followed in my line of thought, some steps that we should follow to strengthen this base.

## Level One {Start} :books:
The idea here is to spend as much time as you can sharpening the axe, so that the blow is accurate.
It's no use having the best tools in our favor, if we don't have a base, it's necessary to understand how HTTP methods work, error messages, what types of APIs are and how each one of them works.

### Links to Study Articles: 📘<br>
> https://rhinosecuritylabs.com/application-security/simplifying-api-pentesting-swagger-files/<br>
https://medium.com/@ghostlulzhacks/swagger-api-c07eca05441e<br>
https://book.hacktricks.xyz/pentesting/pentesting-web/web-api-pentesting<br>
https://pentestbook.six2dez.com/enumeration/webservices/apis<br>
https://blog.securelayer7.net/api-penetration-testing-with-owasp-2017-test-cases/<br>
https://securityboulevard.com/2021/01/manual-penetration-testing-leaves-apis-exposed/<br>
https://www.danielyan.com/penetration-testing<br>
https://workbook.securityboat.in/resources/api-pentest<br>
https://graphql.org/learn/queries/<br>
https://apisecurity.io/encyclopedia/content/owasp/owasp-api-security-top-10.htm<br>
https://labs.detectify.com/2021/08/10/how-to-hack-apis-in-2021/<br>
https://github.com/OAI/OpenAPI-Specification/blob/main/versions/2.0.md#parameter-object<br>
https://assertible.com/blog/7-http-methods-every-web-developer-should-know-and-how-to-test-them<br>

### Links to videos/classes for study: 📽️<br>
>https://www.youtube.com/watch?v=fvcKwUS4PTE (Recon APIs) <br>
https://www.youtube.com/watch?v=aQGbYfalRTA (Owasp Top 10 API Bugs)<br>
https://www.youtube.com/watch?v=AsGSCWCraS8 (Explore Method PUT)<br>
https://youtu.be/jyjGneKJynk (Finding Your Next Bug: GraphQL)<br>

### Links to HTTP Status Code and Methods:<br>
>https://www.devmedia.com.br/http-status-code/41222#3-9<br>
>https://assertible.com/blog/7-http-methods-every-web-developer-should-know-and-how-to-test-them <br>
>https://betterprogramming.pub/9-http-methods-you-want-to-know-88e45a28d106<br>

### Laboratory Links for Studies: 💻 <br>
> https://github.com/InsiderPhD/Generic-University (Lab OWASP Top 10 API) <br>
> https://application.security/free/owasp-top-10-API (Lab OWASP Top 10 API) <br>
> https://github.com/dolevf/Damn-Vulnerable-GraphQL-Application (Lab API GraphQL) <br>
> https://github.com/CarveSystems/vulnerable-graphql-api (Lab API GraphQL Vuln) <br>
> https://github.com/h-a-c/jwt-lab (LAB JSON Web Token) <br>
> https://github.com/roottusk/vapi (vAPI is Vulnerable API OWAP Top 10 API) <br>

### Suggestions for courses Hacking: 🕸️
>https://sec4us.com.br/treinamentos/web-api-exploitation/

### Suggestions for courses on Udemy, to help you understand the structure of some APIs. 👍
https://www.udemy.com/course/automacao-de-testes-de-api-com-postman-projeto-de-testes/ <br>
https://www.udemy.com/course/aprenda-postman-em-1-hora-iniciante/ <br>
https://www.udemy.com/course/springboot-essencial/ <br>
https://www.udemy.com/course/crie-apis-rest-com-spring-boot-do-iniciante-ao-especialista/ <br>
https://www.udemy.com/course/webapi-entityframework-mysql/ <br>
https://www.udemy.com/course/graphql-criando-apis-profissionais-e-flexiveis/ <br>
https://www.udemy.com/course/microsservicos-java-spring-cloud/ <br>
https://www.udemy.com/course/curso-de-graphql-e-apollo-server-client/ <br>


## Level Two {Recon} ℹ️
The first phase of a pentesting is the famous Recon "Information Collection" here is the moment where we must understand about the API infrastructure that we are analyzing.

Here I will provide a "Recon Mindmap" that will help you with some tools and methodologies in the API Recon phase, this mindmap was not created by me.

>https://dsopas.github.io/MindAPI/play/

During my study journey, I made a survey of the most found and exploited vulnerabilities when we talk about APIs:

- API Exposure
- Misconfigured Caching
- Exposed Tokens
- JWT Weaknesses
- Authorization Issues
- Undocumented Endpoints
- Different Versions
- Rate Limiting (BF Allowed)
- Race Conditions
- XXE Injection
- Switching Content Type
- HTTP Methods
- Injection Vulnerabilities


## Level three {Exploration} ⚠️


### Inspect Baseline APIs:
>https://inspector.swagger.io/builder <br>
https://apitools.dev/swagger-parser/online/

### Convert version Open API:
>https://www.apimatic.io/transformer/


### API Security Checklist
Checklist of the most important security countermeasures when designing, testing, and releasing your API. <br>

#### Authentication 
 ✔️ Don't use Basic Auth. Use standard authentication instead (e.g. JWT, OAuth). <br>
 ✔️ Don't reinvent the wheel in Authentication, token generation, password storage. Use the standards. <br>
 ✔️ Use Max Retry and jail features in Login. <br>
 ✔️ Use encryption on all sensitive data. <br>
 
#### JWT (JSON Web Token)
 ✔️ Use a random complicated key (JWT Secret) to make brute forcing the token very hard. <br>
 ✔️ Don't extract the algorithm from the header. Force the algorithm in the backend (HS256 or RS256). <br>
 ✔️ Make token expiration (TTL, RTTL) as short as possible. <br>
 ✔️ Don't store sensitive data in the JWT payload, it can be decoded easily.
#### OAuth
 ✔️ Always validate redirect_uri server-side to allow only whitelisted URLs. <br>
 ✔️ Always try to exchange for code and not tokens (don't allow response_type=token). <br>
 ✔️ Use state parameter with a random hash to prevent CSRF on the OAuth authentication process. <br>
 ✔️ Define the default scope, and validate scope parameters for each application. <br>
#### Access
 ✔️ Limit requests (Throttling) to avoid DDoS / brute-force attacks. <br>
 ✔️ Use HTTPS on server side to avoid MITM (Man in the Middle Attack). <br>
 ✔️ Use HSTS header with SSL to avoid SSL Strip attack. <br>
 ✔️ For private APIs, only allow access from whitelisted IPs/hosts. <br>
#### Input
 ✔️ Use the proper HTTP method according to the operation: GET (read), POST (create), PUT/PATCH (replace/update), and DELETE (to delete a record), and respond with 405 Method Not Allowed if the requested method isn't appropriate for the requested resource.<br>
 ✔️ Validate content-type on request Accept header (Content Negotiation) to allow only your supported format (e.g. application/xml, application/json, etc.) and respond with 406 Not Acceptable response if not matched. <br>
 ✔️ Validate content-type of posted data as you accept (e.g. application/x-www-form-urlencoded, multipart/form-data, application/json, etc.). <br>
 ✔️ Validate user input to avoid common vulnerabilities (e.g. XSS, SQL-Injection, Remote Code Execution, etc.). <br>
 ✔️ Don't use any sensitive data (credentials, Passwords, security tokens, or API keys) in the URL, but use standard Authorization header. <br>
 ✔️ Use an API Gateway service to enable caching, Rate Limit policies (e.g. Quota, Spike Arrest, or Concurrent Rate Limit) and deploy APIs resources dynamically. 
#### Processing
 ✔️ Check if all the endpoints are protected behind authentication to avoid broken authentication process. <br>
 ✔️ User own resource ID should be avoided. Use /me/orders instead of /user/654321/orders. <br>
 ✔️ Don't auto-increment IDs. Use UUID instead. <br>
 ✔️ If you are parsing XML files, make sure entity parsing is not enabled to avoid XXE (XML external entity attack). <br>
 ✔️ If you are parsing XML files, make sure entity expansion is not enabled to avoid Billion Laughs/XML bomb via exponential entity expansion attack. <br>
 ✔️ Use a CDN for file uploads. <br>
 ✔️ If you are dealing with huge amount of data, use Workers and Queues to process as much as possible in background and return response fast to avoid HTTP Blocking. <br>
 ✔️ Do not forget to turn the DEBUG mode OFF.
#### Output
 ✔️ Send X-Content-Type-Options: nosniff header. <br>
 ✔️ Send X-Frame-Options: deny header. <br>
 ✔️ Send Content-Security-Policy: default-src 'none' header. <br>
 ✔️ Remove fingerprinting headers - X-Powered-By, Server, X-AspNet-Version, etc. <br>
 ✔️ Force content-type for your response. If you return application/json, then your content-type response is application/json. <br>
 ✔️ Don't return sensitive data like credentials, Passwords, or security tokens. <br>
 ✔️ Return the proper status code according to the operation completed. (e.g. 200 OK, 400 Bad Request, 401 Unauthorized, 405 Method Not Allowed, etc.).
#### CI & CD
 ✔️ Audit your design and implementation with unit/integration tests coverage. <br>
 ✔️ Use a code review process and disregard self-approval. <br>
 ✔️ Ensure that all components of your services are statically scanned by AV software before pushing to production, including vendor libraries and other dependencies.<br> 
 ✔️ Design a rollback solution for deployments. <br> 
 <h6 align="center"> Font: https://github.com/shieldfy/API-Security-Checklist </h6>

### Tools:
>https://github.com/Fuzzapi/fuzzapi <br>
https://github.com/Fuzzapi/API-fuzzer <br>
https://github.com/flipkart-incubator/Astra <br>
https://github.com/BBVA/apicheck/ <br>
https://github.com/ngalongc/openapi_security_scanner <br>
https://github.com/assetnote/kiterunner <br>
https://github.com/s0md3v/dump/tree/master/json2paths <br>
https://github.com/imperva/automatic-api-attack-tool <br>
https://github.com/microsoft/restler-fuzzer <br>
https://github.com/RhinoSecurityLabs/Swagger-EZ <br>

### Tools GraphQL:
>https://github.com/dolevf/graphw00f <br>
https://github.com/nikitastupin/clairvoyance <br>
https://github.com/assetnote/batchql <br>
https://github.com/doyensec/inql <br>
https://github.com/swisskyrepo/GraphQLmap <br>
https://apis.guru/graphql-voyager/ <br>
https://gitlab.com/dee-see/graphql-path-enum <br>
https://github.com/andev-software/graphql-ide <br>



