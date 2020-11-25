# Itau_Processo_Seletivo

1. [Motivação](#Motivação) 
2. [Objetivos](#Objetivos)
3. [Diagramas](#Diagramas)
    - [Fluxo Inicial](#FluxoInicial)
    - [Fluxo Provisório](#FluxoProvisório)
4. [Estudos](#Estudos)
    - [Pontos Negativos](#PontosNegativos)
    - [Mainframe](#Mainframe)
    - [IBM WebSphere](#IBM WebSphere)
    - [Power BI](#Power BI)
    - [Control-M](#ControlM)
10. [Solução](#Solução)

## Motivação

Qual foi a nossa motivação para realizar esse projeto?

Esse projeto faz parte do Processo Seletivo da Itaú em parceiria com o a École 42 São Paulo.

## Objetivos

Quais foram os nossos objetivos?

- Apresentar um relatório indicando os atuais problemas descritos no seguinte documento: [Requisitos](https://github.com/vix993/Itau_Processo_Seletivo/blob/main/Case%20-%20Escape%20Apresentac%CC%A7a%CC%83o.pdf)
- Desenho técnico de uma proposta de melhoria e evolução, considerando todo o contexto descrito, fluxos atuais, tecnologias e ferramentas disponíveis no mercado.
- Sugestão de tecnologias e ferramentas que podem ser aplicadas no contexto.

## Diagramas

### FluxoInicial

#### Iniciamos o processo com o seguinte fluxo.

<image alt="flow diagram" src="Fluxos atuais.png" />

### FluxoProvisório

#### Sugestão provisória de fluxo

[Edite o diagrama](https://whimsical.com/EaB7kKFpsiKaiRdWUTSwtM)

<image alt="flow-provisorio" src="untitled@1.25x (1).png" />

## Estudos

### ControlM

- Desenvolvido pela BMC Software, e permite a execução de scripts de automação em diferentes tipos de servidores (Windows, Linux, Mainframes, etc), monitorados por um único ponto. Permite, por exemplo, a execução de grupos de scripts ("jobs") em uma região/horário ou tipo de servidor antes de outras, coordenando processos complexos de automação.

- Pode levar em consideração processos cíclicos ou não, e também ser configurado com relação à dependências (sucesso ou não de processos anteriores, e como foi o resultado da execução dos processos).

- Projetado para ser fácil para configuração de jobs, independente da plataforma, usando o mesmo tipo de interface para diferentes tipos de jobs, e também para monitorar e gerenciar jobs (verificar logs de execução, re-execução, etc).

- Usa PostgreSQL como database, e não necessita de licenças separadas.

- Apresenta alta disponibilidade através de clusterização

- Permite análise predictiva do resultados de jobs, facilitando o trabalho de recuperação em casos de falhas, o que também resulta em menores custos de operação.

## Solução

Qual foi a nossa solução?
