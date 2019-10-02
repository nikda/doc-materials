# Полезные материалы и ссылки
---

## Архитектура

### CQRS
* [CQRS. Факты и заблуждения](https://habr.com/ru/post/347908/)
* [Event Sourcing и CQRS](https://habr.com/ru/company/nixsolutions/blog/321686/)
* [Быстрорастворимое проектирование](https://habr.com/ru/company/jugru/blog/447308/)
* [Глобальное кеширование результатов Query в ASP.NET CORE](https://habr.com/ru/post/449744/)
* [Поваренная книга разработчика: DDD-рецепты (5-я часть, Процессы)](https://habr.com/ru/post/454668/)

### REST
 * [Описание и пример + стравнение JSON API, ODATA, GraphQL](https://habr.com/ru/company/oleg-bunin/blog/433322/)

### Кэширование
 * [Кэши для «чайников»](https://habr.com/ru/company/google/blog/316344/)

### Паттерны
#### Репозиторий
#### Сага
  * [Реализация паттерна saga на C#](https://jira.moex.com/secure/attachment/85345/swagger%20accounts%20by%20contract%20id.yaml)
  * [Compensating Transaction pattern](https://docs.microsoft.com/en-us/azure/architecture/patterns/compensating-transaction)

---
## TOOLS

 * dotnet pack --configuration Debug
 * dotnet nuget push *.nupkg -s http://172.20.192.93:8081/repository/nuget-hosted/ -k ${NEXUS_API_KEY}


---
## Ссылки
### .Net + .Net Core
 * [Awesome .NET Core](https://github.com/thangchung/awesome-dotnet-core)
 * [JWT-токены](https://metanit.com/sharp/aspnet5/23.7.php)
 * [Авторизация на основе Claims (Policy)](https://metanit.com/sharp/aspnet5/15.6.php)
 * [Аутентификация asp .net core через IdentityServer4](https://habr.com/ru/post/426289/)
 * [Get started with NSwag and ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/tutorials/getting-started-with-nswag?view=aspnetcore-2.2&tabs=visual-studio)
 * [Secure a backend web API](https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/web-api)
 * [Cache access tokens](https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/token-cache)
 * [.NET: Инструменты для работы с многопоточностью и асинхронностью. Часть 1](https://habr.com/ru/post/452094/)
 * [.NET: Инструменты для работы с многопоточностью и асинхронностью. Часть 2](https://habr.com/ru/post/459514/)
 * [Валидация WebApi](http://anthonygiretti.com/2018/11/18/common-features-in-asp-net-core-2-1-webapi-validation/)
 * **[Примеры](https://github.com/aspnet/Entropy/tree/master/samples)**
 * [Тестирование контроллеров](https://docs.microsoft.com/ru-ru/aspnet/core/mvc/controllers/testing?view=aspnetcore-3.0)
 
### Микросервисы примера eShopOnContainers
 * [Designing and implementing API Gateways with Ocelot in .NET Core containers and microservices architectures](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/)
 * [The Http communication is as follows:Client app --> API Gateway --> (Optional) HttpAggregator --> Internal Microservices](https://github.com/dotnet-architecture/eShopOnContainers/issues/637)
 * [Implementing event-based communication between microservices (integration events)](https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications)
 * [Identity Propagation with .NET Core 2](https://jeroenhildering.com/2018/07/23/identity-propagation-with-net-core-2/)
 * [Make secure .NET Microservices and Web Applications](https://docs.microsoft.com/ru-ru/dotnet/standard/microservices-architecture/secure-net-microservices-web-applications/)
 

## IIS Express
 * c:\Users\NikitinDA\Documents\IISExpress\
 * https://gyorgybalassy.wordpress.com/2013/12/02/cleaning-up-iis-express-configuration/
 * Renamed WebSite + path: https://stackoverflow.com/questions/39591197/a-renamed-website-web-config-log4net-using-iis-express-using-git-version-con

### Книги
 * [Книга «Конкурентность и параллелизм на платформе .NET. Паттерны эффективного проектирования»](https://habr.com/ru/company/piter/blog/453804/)
 
 
### Примеры
Send-MailMessage -To "Dmitry.Nikitin@moex.com" -From "Dmitry.Nikitin@moex.com" -Subject "Test mail" -SmtpServer "osmtp.micex.com"

Send-MailMessage -To "Dmitry.Nikitin@moex.com" -From "do-not-reply@moex.com" -Subject "Test mail" -SmtpServer "osmtp.moex.com" -Credential web
password: mstr3k,3d
 
### Блоги
 * https://www.zpqrtbnk.net/


.Net Core Linux
https://dotnet.microsoft.com/download/dotnet-core/2.1
https://github.com/abergs/fido2-net-lib

https://github.com/abergs/fido2-net-lib

### ELK
 * https://elk-docker.readthedocs.io/
 * https://www.elastic.co/downloads/logstash
 * https://www.elastic.co/guide/en/logstash/5.2/first-event.html

	
	logstash-simple.conf

cd bin
.\logstash.bat -f logstash-simple.conf

input {
  stdin { }
  http {
    host => "127.0.0.1" # default: 0.0.0.0
    port => 9610 # default: 8080
  }
}

output {
  elasticsearch { hosts => ["localhost:9200"] }
  stdout { codec => rubydebug }
}


### Docker
* Images https://docs.microsoft.com/ru-ru/dotnet/standard/microservices-architecture/net-core-net-framework-containers/net-container-os-targets
* Create https://docs.microsoft.com/ru-ru/dotnet/standard/microservices-architecture/docker-application-development-process/docker-app-development-workflow
* https://docs.microsoft.com/ru-ru/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker?view=aspnetcore-2.2
* https://docs.microsoft.com/ru-ru/dotnet/core/docker/intro-net-docker
* [VS + Hello world](https://docs.microsoft.com/ru-ru/dotnet/core/docker/build-container)
* https://docs.docker.com/engine/examples/dotnetcore/#create-a-dockerfile-for-an-aspnet-core-application

docker create --name hw2_2 helloworld2

docker - не может запуститься VS debugger - Reset Credentials для Shared Drivers in docker
    * https://docs.microsoft.com/en-us/visualstudio/containers/troubleshooting-docker-errors?view=vs-2019
	
/health/ready
/health/live
https://docs.microsoft.com/ru-ru/aspnet/core/host-and-deploy/health-checks?view=aspnetcore-2.2
https://github.com/xabaril/AspNetCore.Diagnostics.HealthChecks


JWT
https://andrey.moveax.ru/post/asp-net-core-web-api-authentication-part-1-jwt
https://andrey.moveax.ru/post/asp-net-core-web-api-authentication-part-2-jwt-based-on-jws
https://metanit.com/sharp/aspnet5/23.7.php
https://docs.microsoft.com/ru-ru/aspnet/core/security/authorization/limitingidentitybyscheme?view=aspnetcore-2.2&tabs=aspnetcore2x

JMeter
https://habr.com/ru/post/456928/


Microsoft Visual Studio and .NET Framework Log Collection Tool https://www.microsoft.com/en-us/download/details.aspx?id=12493


### GIT

Password: https://stackoverflow.com/questions/31782090/remove-saved-credentials-from-tortoisegit/31782500
rundll32.exe keymgr.dll,KRShowKeyMgr

Обновление submudule git submodule update --remote --merge

### Swagger
 * Mock server
   * [Prism](https://stoplight.io/p/docs/gh/stoplightio/prism/docs/guides/cli.md)
   * [Prism](https://help.stoplight.io/prism/getting-started/prism-introduction)


### Vue

https://github.com/vuejs/vue-hackernews-2.0

### БД
https://habr.com/ru/company/yandex/blog/435880/
http://rsdn.org/forum/design/7488563.1

### NPM
  [A lightweight private npm proxy registry](https://verdaccio.org)
  
### Разное
 * [OpenAPM - Application Performance Management tools](https://openapm.io/)
 * [Elastic APM](https://github.com/elastic/apm)
 
	

