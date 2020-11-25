# Processo de Contratação de Produtos nos Canais Web e Client/Server

## Fluxo Atual

```mermaid
sequenceDiagram
    participant A as Sistema A<br/>(Distribuida)
    participant C as Sistema C<br/>(WebSphere<br/>(back-level)) 
    participant B as Sistema B<br/>(Mainframe)
    participant CA as Canais<br/>Web e<br/>Client/Server
    participant OR as Órgãos Regulatórios
    Note over B,CA: Contratação/<br/>Cancelamento<br/>da Contratação
    B->>C: Solicita<br/>Validação<br/>Dados Cliente
    C->>A: Valida Dados Cliente
    A->>C: Retorna Dados<br/>Cliente Validados
    C->>B: Dados Cliente Validados
    Note over B: Valida Dados Cliente<br/>e da contratação<br/>cancelamento da contr.
    Note over B: Grava Contratação/<br/>Cancelamento da contr.
    Note over A: Rotina Control-M
    B->>A:Busca Contratação/<br/>Cancelamento
    Note over A: Atualiza dados<br/>Contratação/Cancel.
    Note over B: Gera Arquivo<br/>Contratação/<br/>Cancelamento
    B->>OR: Envio de arquivo<br/>Contratação<br/>Cancelamento
    Note over OR: Registra Contratação/<br/>Cancelamento
```

## Desvantagens

- Canal Mobile não é atendido por falta de integração sistêmica

- Sistema C (Websphere, em back-level) realiza somente função de integração entre outros dois sistemas (subutlizado)

- Dados de contratação/cancelamento são atualizados somente 1 vez ao dia no Sistema A (Distribuída), diminuindo a agilidade na análise e geração de estatísticas.

---

## Fluxo Proposto

```mermaid
sequenceDiagram
    participant A as Sistema A<br/>(Distribuida)
    participant C as Sistema C<br/>(WebSphere<br/>(Atualizada))
    participant CA as Canais<br/>Web<br/>Client/Server<br/>Mobile
    participant OR as Órgãos Regulatórios
    participant B as Sistema B<br/>(Mainframe)
    Note over C,CA: Contratação/<br/>Cancelamento<br/>da Contratação
    C->>A: Solicita<br/>Validação<br/>Dados Cliente
    A->>C: Retorna Dados<br/>Cliente Validados
    C->>B: Dados Cliente Validados<br/>e da Contratação/Cancelamento
    Note over B: Valida Dados Cliente<br/>e da contratação<br/>cancelamento da contr.
    Note over B: Grava Contratação/<br/>Cancelamento da contr.
    Note over C: Replicação SQL<br/>InfoSphere ou<br/>DB2 Connect
    B->>A:Replicação Dados<br/>Contratação/<br/>Cancelamento
    Note over A: Atualiza dados<br/>Contratação/Cancel.
    Note over A: Geração de estudos<br/>analíticos para subsidiar<br/>Área de Inteligência<br/>de Mercado
    Note over B: Gera Arquivo<br/>Contratação/<br/>Cancelamento
    B->>OR: Envio de arquivo<br/>Contratação<br/>Cancelamento
    Note over OR: Registra Contratação/<br/>Cancelamento
```

## Vantagens

- A partir de uma única plataforma moderna, confiável e de alta disponibilidade implementando APIs baseadas em tecnologias atuais (RESTful API e JSON), obtém-se integração com todos os canais do banco, de forma automática e ágil.

- Possibilidade de geração de relatórios estatísticos e de análise do comportamento dos clientes de maneira imediata e online

- Geração de estudos analíticos, com dados atualizados e precisos, para subsidiar a Área de Inteligência de Mercado, a partir de plataforma Power BI
