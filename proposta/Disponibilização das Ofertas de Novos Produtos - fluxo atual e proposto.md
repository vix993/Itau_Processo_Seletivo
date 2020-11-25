# Processo de Disponibilização das Ofertas de Novos Produtos nos Diferentes Canais

## Fluxo Atual

```mermaid
sequenceDiagram
    participant Des as Área Desenvolvimento<br/> Mainframe
    participant A as Sistema A<br/>(Distribuida)
    participant B as Sistemas B <br/>(Mainframe)
    participant CW as Canal<br/>Web
    participant CS as Canal<br/>Client/Server
    participant DB2
    participant SQL
    Des->>B: Desenvolvimento de<br/>Novas Telas
    B->>DB2: Obtem dados produto<br/>e caracteristicas de negociação
    B->>CW: Disponibiliza Oferta<br/>de Novos Produtos
    A->>SQL: Obtem dados produto<br/>e caracteristicas de negociação
    A->>CS: Disponibiliza Oferta<br/>de Novos Produtos
```

## Desvantagens

- Necessidade de desenvolvimento de novas telas a cada produto, no Canal Web

- Informações dos produtos e suas características obtidos de fontes diferentes (Sistema B - Mainframe para Canal Web, e Sistema A - Distribuída para Canal Client/Server), podendo gerar inconsistências na oferta.

- Canal Mobile não é atendido por qualquer dos Sistemas (A ou B), devido à falta de integração sistêmica.

---

## Fluxo Proposto

```mermaid
sequenceDiagram
    participant C as Sistema C<br/>WebSphere<br/>(atualizado)
    participant A as Sistema A<br/>(Distribuída)
    participant CW as Canal<br/>Web
    participant CS as Canal<br/>Client<br/>Server
    participant MO as Canal<br/>Mobile
    participant SQL
    C->>A: Requisita dados<br/>de produtos<br/>e caracteristicas<br/>de negociação
    A->>SQL: Obtém dados<br/>de produtos<br/>e caracteristicas<br/>de negociação
    Note over C,MO: Disponibiliza Oferta<br/>de Novos Produtos
```

## Vantagens

- Obtenção das informações sobre Novos Produtos a partir de uma única fonte, consistênte e atualizada.

- A partir de uma única plataforma moderna, confiável e de alta disponibilidade implementando APIs baseadas em tecnologias atuais (RESTful API e JSON), obtém-se integração com todos os canais do banco, de forma automática e ágil.
