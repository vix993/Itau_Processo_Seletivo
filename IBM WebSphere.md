# IBM WebSphere

O WAS é uma plataforma baseada em Java, desenvolvida pela IBM para genrenciar e criar websites. É normalente usada para criar aplicações web interativas que suportam funções de negócios necessárias para e-commerce, e integra todos os dados através de diferentes sistemas operacionais e aplicações, usando maquinas virtuais Java, containers, serviços de mensageria (MQ - message / queue), web-service, etc.

## Características

- Alta disponibilidade

- Escalabilidade

- Suporte a aplicações que necessitam volume alto de memória

- Focado em conectividade, integração e serviços web. Tem melhor performance, melhor implementação do padrão J2EE, e gerenciamento de transações do que o Oracle Weblogic

## Principais componentes

- WebSphere Application Server (WAS): conecta usuários web aos Java (Jakarta) servlets.

- Data-Server: para persistência de dados

- Web-Server: provê serviços HTTP

## Conceitos

> Jakarta Servlet (antigo Java Servlet) é um componente de software que estende a capacidade de um servidor. Embora servlets possam responder a muitos tipos de requisições, normalmente implementam web containers para conter aplicações web em servidores web, e por isso qualificam-se como uma API de servidor web. São o equivalente, em tecnologia web, ao PHP e ASP.NET.
> 
> "Células" são grupos de nodes (hosts) em um único domínio administrativo, e gerenciadas por um console adminstrativo.

## Funcionalidades

- Suporta aos containers de servlets/JSP que rodam em cima do HTTP

- Suporta servidores HTTP como IBM HTTP server, Netscape iPlanet, e MS IIS

- Suporta páginas HTML, Java Server, Servlets e XML

- Suporte o modelo de componentes EJB (componente de software que encapsula a lógica de negócio de uma aplicação, como segurança, processamento de transações, etc; é um sub-tópico da especificação Java EE), e gerenciamento de workload.

- Trabalha em clusters (roteia requisições web para outros servidores de aplicações quando há indisponibildade do original).

- Aplicações são deployed usando arquivos, enviados pelo gerenciamento central para os servidores de aplicações do cluster, em diversos hosts diferentes. Isso é realizado pelo Deployment Manager (Dmgr)

- Permite clusterização assimétrica, onde o particionamento do cluster é feito de maneira a determinar um cluster específico para tarefas que, nele, seriam melhor executadas, por questão de segurança ou desempenho, por exemplo.


