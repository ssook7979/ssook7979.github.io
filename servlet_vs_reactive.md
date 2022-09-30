[https://www.infoq.com/news/2017/12/servlet-reactive-stack/](https://www.infoq.com/news/2017/12/servlet-reactive-stack/)

| mvc | webflux |
| --- | --- |
| based on thread pools | based on event loop |
|  | supoorts both servlet container(Tomcat, Jetty) and non-servlet runtimes(Netty, Undertow) |
| reactive client를 지원하기 위해 servlet api에 async 지원 |  |
| Spring-mvc supports a reactive client but once the processes reach servlet api, they work in blocking mode. | WebFilter and WebHandler are non-blocking, and return a Mono<void> which is a promise type in Reactor |
| If the application has blocking dependencies | require ease of streaming up or down |
| writing reactive clients in spring-mvc controller to make remote service calls | where scalability and high efficiency are major considerations |
|  | According to Stoyanchev, spring-webflux is not necessarily faster but it is better in dealing with the issues of scalability and efficient use of hardware resources. It is also better at dealing with the issues of latency. |