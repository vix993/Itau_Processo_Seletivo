# Itau Processo Seletivo

1. [Motivação](#Motivação) 
2. [Objetivos](#Objetivos)
3. [Diagramas](#Diagramas)
    - [Cadastro de Novos Produtos](#CadastroDeNovos)
    - [Fluxo Inicial](#FluxoInicial)
    - [Fluxo Novo](#FluxoNovo)
4. [Estudos](#Estudos)
    - [Pontos Negativos](#PontosNegativos)
    - [Mainframe](#Mainframe)
    - [IBM WebSphere](#IBMWebSphere)
    - [IBM Infosphere Data Replication](#IBMInfosphereDataReplication)
    - [Power BI](#PowerBI)
    - [JAX-RS](#JAX-RS)
    - [Control-M](#ControlM)
10. [Solução](#Solução)

## Motivação

Esse projeto faz parte do Processo Seletivo da Itaú em parceria com a École 42 São Paulo.

## Objetivos

- Apresentar um relatório indicando os atuais problemas descritos no seguinte documento: [Requisitos](https://github.com/vix993/Itau_Processo_Seletivo/blob/main/Case%20-%20Escape%20Apresentac%CC%A7a%CC%83o.pdf)
- Desenho técnico de uma proposta de melhoria e evolução, considerando todo o contexto descrito, fluxos atuais, tecnologias e ferramentas disponíveis no mercado.
- Sugestão de tecnologias e ferramentas que podem ser aplicadas no contexto.

## Diagramas

### CadastroDeProdutosNovos

<image alt="New Products" src="proposta/Cadastro de Novos Produtos.png" />

### FluxoInicial

#### Iniciamos o processo com o seguinte fluxo.

<image alt="flow diagram" src="imgs/Fluxos atuais.png" />

### FluxoNovo

#### Sugestão de Fluxo novo do sistema

[Edite o diagrama](https://whimsical.com/EaB7kKFpsiKaiRdWUTSwtM)

[Veja maior](https://github.com/vix993/Itau_Processo_Seletivo/blob/main/imgs/untitled%401.25x%20(1).png)

<image alt="flow-provisorio" src="imgs/untitled@1.25x (1).png" />

## Estudos

### PontosNegativos

- Como a rotina de contratação/cancelamento de produtos é hosteada pelo mainframe dificulta a integração com canais adicionais como por exemplo o mobile;
- O cadastro de produtos em dois sistemas diferentes permite a inconsistência de informações duplicadas e diminui a flexibilidade com relação aos parametros de novos produtos;
- Canal Mobile não tem acesso à oferta de novos produtos;
- Como o Sistema A (Distribuído) tem uma rotina de atualização diária dos dados de contratação/cancelamento dos produtos em sua base de dados, havera momentos que a informação ficara defasada, o que pode impactar nas validações e nas geração de relatorios gerenciais/analiticos;
- As telas do cliente/server são criadas com campos fixos, isso impede maior parametrização, dinamismo e agilidade na oferta de produtos;
- (O prazo máximo disponibilização da oferta ao cliente, a partir da idealização/cadastro do produto, é muito longo.)
- O Sistema C (WebSphere) trabalha em back-level (significando que ele é desatualizado, e provavelmente não conta mais com suporte oficial da IBM). Isso causa um risco enorme aos dados do banco e seus clientes no evento de uma ameaça ([caso](https://www.agenor.co.uk/was-upgrade-case-study)).

### Mainframe

#### Definição

Um mainframe (também chamado de big iron), é um computador usado principalmente por grandes organizações para aplicações críticas, tratamento de dados massivos (estatísticas de consumidores e clientes, planejamento empresarial, cálculos decimais precisos e em grande volume, procesamento de transacṍes, etc). Em geral, possuem maior capacidade de processamento que computadores similares (workstations, desktops, etc).

#### Características

Mainframes não são normalmente caracterizados pelo poder computacional puro, mas sim pela redundância (que permite alta disponibilidade e segurança), alta capacidade de tráfego de dados, estrita compatibilidade com softwares mais antigos, alto nível de utilização de hardware (através de virtualização), e possibildade de troca e atualização de hardware sem necessidade de desligamento (incluindo processadores, discos e memórias).

Isto permite alta estabilidade e confiabilidade, o que permite que funcionem por longos períodos de tempo, com tempo médio entre falhas (MTBF) na ordem de décadas.

As principais características que mantém mainframes em uso são:

- **Confiabilidade:** Mainframes são capazes de funcionar em consoância com as especificações de software e hardware, permitindo que não errem. Por exemplo, bancos precisam realizar cálculos decimais com 100% de precisão, mantendo registro de milhões de transações por segundo, em nível global.

- **Disponibilidade:** Bancos não podem ter seus sitemas não-funcionando. Um cliente que não consegue verificar seu saldo, provavelmente mudará de banco. Embora outras tecnologias tenham surgido, nenhuma tem sido tão bem sucedida em replicar sua arquitetura de alta disponibilidade.

- **Segurança:** Bancos lidam com muitas informações sensíveis e confidenciais. A segurança é um ítem não negociável, e mainframes são construídos com a segurança como foco desde sua base, através de hardwares de aceleração criptográfica e sistemas operacionais seguros.

- **Velocidade de análise de dados:** Bancos lidam com operações de caixas eletrônicos, cartões de crédito e débito, investimentos de capital, etc. Cada uma dessas operações requer respostas instantâneas. Considerando a quantidade destes tipos de transações e o volume de dados trafegado, mainframes são ideais (se não únicos) no atendimento a este requisito.

- **Compatibilidade:** Mainframes são compatíveis com múltiplas linguagems de desenvolvimento, como COBOL, Java, C/C++, Fortran, etc.

- **Escalabilidade:** O negócio bancário envolve milhões de clientes e transações. Mainframes oferecem quantidades enormes de poder de processameto, permitindo suportar cenários de uso dinâmicos.

- **Integração:** Mainframes são arquitetados de maneira a trabalhar com partes independentes e interligadas. Qualquer problema em uma delas permite sua substituição sem afetar o restante do sistema, sem desligamento.

### IBMWebsphere

O WAS é uma plataforma baseada em Java, desenvolvida pela IBM para genrenciar e criar websites. É normalente usada para criar aplicações web interativas que suportam funções de negócios necessárias para e-commerce, e integra todos os dados através de diferentes sistemas operacionais e aplicações, usando maquinas virtuais Java, containers, serviços de mensageria (MQ - message / queue), web-service, etc.

#### Características

- Alta disponibilidade

- Escalabilidade

- Suporte a aplicações que necessitam volume alto de memória

- Focado em conectividade, integração e serviços web. Tem melhor performance, melhor implementação do padrão J2EE, e gerenciamento de transações do que o Oracle Weblogic

#### Principais componentes

- WebSphere Application Server (WAS): conecta usuários web aos Java (Jakarta) servlets.

- Data-Server: para persistência de dados

- Web-Server: provê serviços HTTP

#### Conceitos

> Jakarta Servlet (antigo Java Servlet) é um componente de software que estende a capacidade de um servidor. Embora servlets possam responder a muitos tipos de requisições, normalmente implementam web containers para conter aplicações web em servidores web, e por isso qualificam-se como uma API de servidor web. São o equivalente, em tecnologia web, ao PHP e ASP.NET.
> 
> "Células" são grupos de nodes (hosts) em um único domínio administrativo, e gerenciadas por um console adminstrativo.

#### Funcionalidades

- Suporta aos containers de servlets/JSP que rodam em cima do HTTP

- Suporta servidores HTTP como IBM HTTP server, Netscape iPlanet, e MS IIS

- Suporta páginas HTML, Java Server, Servlets e XML

- Suporte o modelo de componentes EJB (componente de software que encapsula a lógica de negócio de uma aplicação, como segurança, processamento de transações, etc; é um sub-tópico da especificação Java EE), e gerenciamento de workload.

- Trabalha em clusters (roteia requisições web para outros servidores de aplicações quando há indisponibildade do original).

- Aplicações são deployed usando arquivos, enviados pelo gerenciamento central para os servidores de aplicações do cluster, em diversos hosts diferentes. Isso é realizado pelo Deployment Manager (Dmgr)

- Permite clusterização assimétrica, onde o particionamento do cluster é feito de maneira a determinar um cluster específico para tarefas que, nele, seriam melhor executadas, por questão de segurança ou desempenho, por exemplo.

### IBMInfosphere Data Replication

#### Replicação de dados

Replicação de dados é o processo de armazenar dados em mais de um local. Copiar os mesmos dados de um banco de dados de um servidor para outro servidor possibilita o acesso aos dados sem incosistência, resultando em uma base de dados distribuída que proporciona maior confiabilidade e disponibilidade das informações.

Para evitar inconsistências, sempre que há alguma alteração no BD Source o BD Target será atualizado com as respectivas alterações.

- Pontos Positivos
Disponibilidade
Confiabilidade
Suporta muitos usuários
Execução de queries de forma mais rápida

- Pontos Negativos
Demanda maior espaço de armazenamento, cópias em diferentes localidades exigem mais espaço.
Torna-se uma tarefa custosa quando grande quantidade de cópias devem ser atualizadas


#### IBMInfosphereDataReplication

O IBM InfoSphere Data Replication também pode fornecer disponibilidade contínua para manter réplicas de banco de dados em locais remotos para que seja possível alternar uma carga de trabalho para essas réplicas em segundos, não em horas.

'Sources' e 'Targets' aceitos:
•	https://www.ibm.com/support/knowledgecenter/SSTRGZ_11.4.0/com.ibm.swg.im.iis.db.repl.intro.doc/topics/iiyrcintsourcestargets.html

Página do produto:
•	https://www.ibm.com/br-pt/products/infosphere-data-replication

### PowerBI

O Microsoft Power BI é a ferramenta de Business Intelligence da Microsoft. Com ela é possível consolidar, tornar coerentes e visuais as informações que se encontram em diversas fontes, desde uma simples pasta de trabalho do Microsoft Excel, a arquivos localizados na nuvem. 
Essa ferramenta é uma coleção de serviços de software, aplicativos e conectores que trabalham juntos para transformar suas fontes de dados não relacionadas em informações coerentes, visualmente envolventes e interativas.
Além disso, ela também possibilita o fácil acesso e compartilhamento dessas informações.
O Power BI pode ser usado de forma simples para pequenos trabalhos no Excel e banco de dados local, ou até mesmo para grandes e robustos trabalhos a nível empresarial.
Com esta ferramenta é possível gerar uma visão de 360 graus com suas métricas mais importantes em um só lugar, atualizadas em tempo real.

#### Principais Pontos Positivos 
- Power BI é muito barato ou até mesmo grátis;
- Existem comunidades de Power BI, em que qualquer um pode se cadastrar, criar um tópico e/ou votar num tópico existente tirando dúvidas;
- Nessa ferramenta, é possível criar relatórios interativos e painéis personalizados;
- Os relatórios criados no Power BI podem ser exportados para o PowerPoint, o que facilita bastante se você gosta de usar essa ferramenta para apresentações em reuniões ou eventos semelhantes;
- Com o Power BI você consegue se conectar a uma página da Web através do seu link de acesso, importar os dados tabulados e criar indicadores mostrando os dados de forma muito mais prática.

#### Planos do Power BI
- Power BI Free (versão gratuita)
    - O programa realiza todas as análises, porém não permite o compartilhamento de relatórios. Assim, essa modalidade não é recomendada para as organizações, atendendo melhor a estudantes, usuários individuais ou micro e pequenas empresas.
- Power BI Pro
    - Essa modalidade permite que os usuários construam e publiquem conteúdo e compartilhem dashboards e relatórios. A licença possibilita também o acesso ao Power BI por dispositivos mobile, como smartphones e tablets.
- Power BI Premium
    - A contratação do serviço não ocorre por usuário, e sim pelo servidor. Por causa disso, o contratante não paga pelo acesso, mas dimensiona a capacidade da instalação conforme o volume de dados e colaboradores que utilizam a ferramenta.
    - A versão Premium, portanto, permite a distribuição de conteúdo entre membros da equipe sem precisar adquirir a licença para cada um dos usuários; por isso, é bastante utilizada para grandes equipes.


#### Pergunta e Respostas Relevantes

##### *QUAIS SÃO OS COMPONENTES PRINCIPAIS DO POWER BI?*
R: O Power BI é formado por um conjunto de componentes que permite ao usuário a análise das informações. Confira os principais:
serviço na nuvem: possibilita que o usuário consulte e analise dados com velocidade e eficiência a partir de qualquer dispositivo;
desktop: ferramenta de desenvolvimento do Power BI ou para análise sob demanda. Permite criar relatórios e construir análises avançadas, conecta dados locais ou na nuvem;
aplicativo: desenvolvido para iOS, Android e Windows, o app dá acesso ao Power BI em tablets e smartphones;
gateway: realiza a comunicação entre os dados do Power BI na nuvem e as fontes de informações nos servidores locais. Assim, quando o usuário solicita uma atualização de informações, o Power BI ativa o gateway, que acessa os dados da empresa e os carrega para a nuvem, por meio de uma conexão criptografada.

##### *QUAIS SÃO AS FONTES DE DADOS QUE O POWER BI PODE ACESSAR?*
R: O Power BI pode acessar fontes de dados locais, Big Data, planilhas de Excel, arquivos de texto e serviços em nuvem. Nessa ampla gama de fontes, estão incluídos os principais bancos de dados do mercado: SQL, Oracle, Teradata, DB2, MySQL e Postgre.
Também há uma série de serviços online que já têm conexões ao Power BI, como Dynamics 365, Google Analytics, Salesforce, GitHub, MailChimp, Facebook, Zendesk, entre outros. Existe, além disso, a possibilidade de desenvolver um conector personalizado, sem custos adicionais.

##### *HÁ LIMITE PARA O TAMANHO DA BASE DE DADOS?*
R: Existem duas possibilidades. Na primeira, a empresa carrega o banco de dados para o Power BI. Nesse caso, há um limite, conforme demonstrado na tabela presente no início deste post.
Já na segunda, o Power BI acessa as informações diretamente do banco de dados da empresa, sem copiá-las para a nuvem. Nessa situação, o limite de armazenamento é o do próprio servidor da empresa.

##### *QUAIS NAVEGADORES DÃO SUPORTE AO POWER BI?*
R: O Power BI é compatível com estes navegadores em todas as plataformas em que estão disponíveis:

**Microsoft Edge*

**Internet Explorer 11. Não há suporte para alguns recursos avançados, como exibição de linhagem, no Internet Explorer. Confira o tópico Linhagem de dados (versão prévia) para ver detalhes.*

**Versão mais recente do Chrome para desktop*

**Versão mais recente do Safari para Mac*

**Última versão do Firefox para desktop. O Firefox pode alterar as fontes usadas no Power BI*


##### Links IMPORTANTES sobre Power:
VIDEO SOBRE O QUE É POWER BI:
•	https://www.youtube.com/watch?v=NP0PJgcIDkY&ab_channel=HashtagTreinamentos

INFORMAÇÕES SOBRE SEGURANÇA DO POWER BI:
•	https://docs.microsoft.com/pt-br/power-bi/guidance/whitepaper-powerbi-security

### JAX-RS

De acordo com o alinhamento da equipe, decidimos manter uma estrutura simplista do projeto. Utilizando tecnologias que já fazem parte da stack atual. Com a criação de API's com a arquitetura RESTful, podemos mapear os recursos necesários para cada operação. Isso nos providencia uma flexibilidade em relação ao desenvolvimento do nosso frontend.

Nesse caso, seguimos a recomendação que está na [documentação](https://www.ibm.com/support/knowledgecenter/SSEQTP_8.5.5/com.ibm.websphere.base.iseries.doc/ae/twbs_jaxrs_getstarted.html) da WebSphere. No caso as API's seriam desenvolvidas utilizando o padrão JAX-RS, que facilita a criação de serviços web usando esse modelo. Poderiamos utilizar a JAX-RS API ou frameworks que o implementam como [Dropwizard](https://github.com/dropwizard/dropwizard), [Jersey](https://github.com/eclipse-ee4j/jersey) ou [RESTEasy Spring Boot](https://github.com/resteasy/resteasy-spring-boot). No caso Spring Boot seria a opção mais convincente considerando a popularidade do framework, que é utilizado por empresas como MercadoLivre, MIT, TransferWise e Deutsche Kreditbank.

Com essa estrutura pronta podemos utilizar frameworks como React e React-Native para desenvolver o frontend dos aplicativos. Frameworks escolhidos pelo potencial de crescimento devido ao suporte que tem da communidade open-source e também disponibilidade de desenvolvedores no mercado.

### ControlM

- Desenvolvido pela BMC Software, e permite a execução de scripts de automação em diferentes tipos de servidores (Windows, Linux, Mainframes, etc), monitorados por um único ponto. Permite, por exemplo, a execução de grupos de scripts ("jobs") em uma região/horário ou tipo de servidor antes de outras, coordenando processos complexos de automação.

- Pode levar em consideração processos cíclicos ou não, e também ser configurado com relação à dependências (sucesso ou não de processos anteriores, e como foi o resultado da execução dos processos).

- Projetado para ser fácil para configuração de jobs, independente da plataforma, usando o mesmo tipo de interface para diferentes tipos de jobs, e também para monitorar e gerenciar jobs (verificar logs de execução, re-execução, etc).

- Usa PostgreSQL como database, e não necessita de licenças separadas.

- Apresenta alta disponibilidade através de clusterização

- Permite análise predictiva do resultados de jobs, facilitando o trabalho de recuperação em casos de falhas, o que também resulta em menores custos de operação.

## Solução

Qual foi a nossa solução?
