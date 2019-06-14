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

###
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
