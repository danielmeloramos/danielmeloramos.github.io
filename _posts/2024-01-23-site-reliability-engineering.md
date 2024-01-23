---
layout: post
title: "Site Reliability Engineering com Prometheus, Grafana e Golang: Uma Abordagem Dinâmica e Eficaz"
date: 2024-01-23 00:00:00
image: '/assets/img/sre-prometheus-golang.jpg'
description: 'Explorando a implementação prática do framework SRE'
main-class: 'sre'
color: '#0d9178'
tags:
- SRE
- Prometheus
- Golang
categories:
- Site Reliability Engineering
image: "/assets/img/sre.png"
twitter_text: 'Explorando a implementação prática do framework SRE, utilizando Prometheus, Grafana e Golang. #SRE #Prometheus #Grafana'
introduction: 'Neste artigo, embarcaremos em uma jornada para implementar a Engenharia de Confiabilidade de Sites (SRE) utilizando Prometheus, Grafana e Golang. Uma abordagem dinâmica e eficaz, para garantir confiabilidade e desempenho em sistemas complexos.'
comments: 'true'
---

Olá, leitores!

Recentemente, tenho me dedicado e trabalhado bastante com SRE. Achei interessante compartilhar um pouco do conhecimento que adquiri no mundo da Engenharia de Confiabilidade de Sites (SRE). Para isso, trago um artigo no qual podemos explorar a implementação prática do framework SRE, utilizando Prometheus, Grafana e Golang para garantir confiabilidade e desempenho em sistemas complexos. Para facilitar o entendimento, dividi o conteúdo em 5 tópicos centrais. Nada muito extenso, mas prometo que será simples e direto. Vamos lá!

![SRE](/assets/img/sre.png)

### Entendendo a Abordagem SRE

A Engenharia de Confiabilidade de Sites (SRE) desafia as barreiras tradicionais entre desenvolvedores e operadores para garantir a estabilidade e eficiência operacional de sistemas. Originada no Google em 2003, a SRE tornou-se referência para manter a confiabilidade em ambientes dinâmicos.

### Indicadores Essenciais - Golden Signals

No livro de [SRE do Google](https://sre.google/sre-book/monitoring-distributed-systems/#xref_monitoring_golden-signals), é relatado que se você tiver que priorizar apenas 4 métricas para monitorar que elas sejam: `Latência`, `Tráfego`, `Erros` e `Saturação`.
Os quatro sinais, são cruciais para medir o desempenho e a confiabilidade de um sistema.

* Latência: Avalia o tempo de processamento das transações, prevenindo frustrações dos usuários;
* Tráfego: Identifica o volume de transações em intervalos de tempo, permitindo a detecção de picos de tráfego;
* Erros: Mede a porcentagem de erros em um período, crucial para manter a confiança do usuário;
* Saturação: Determina a disponibilidade de recursos antes da degradação do sistema.

### Ferramentas-Chave para Implementação

* [Prometheus](https://prometheus.io/): Solução open-source e nativa para a nuvem, desenvolvida pelos engenheiros do Google;
* [Grafana](https://grafana.com/): Plataforma open-source para visualização de métricas de sistemas;
* [Golang](https://go.dev/): Alternativa dinâmica para expor métricas, proporcionando uma implementação eficaz.

![Golang e Grafana](/assets/img/golang-grafana.png)

### Calculando Métricas com PromQL

A [PromQL](https://prometheus.io/docs/prometheus/latest/querying/basics/), a linguagem de consulta do Prometheus, oferece a capacidade de realizar transformações e agregações nas métricas. Isso possibilita extrair informações que não foram diretamente relatadas pela aplicação, mas que podem ser inferidas a partir dos dados disponíveis.

1. **Volume:**
   - *Definição:* O volume refere-se à quantidade total de requisições que a aplicação recebe em um determinado período, neste caso, em um intervalo de 24 horas.
   - *Expressão PromQL:* 
    ```
    sum(increase(golang_server_requests_total[1d]))
    ```
   - *Interpretação:* Essa expressão calcula o total de requisições recebidas pela aplicação, considerando o aumento acumulado ao longo de um dia (24 horas).

2. **Disponibilidade:**
   - *Definição:* A disponibilidade representa a porcentagem de requisições entregues com sucesso em relação ao total, excluindo aquelas que resultaram em códigos de erro do tipo 5xx (erro do servidor).
   - *Expressão PromQL:* 
   ```
   sum(rate(golang_server_requests_total{code!~"5xx"}[1d])) / sum(rate(golang_server_requests_total[1d]))
   ```
   - *Interpretação:* Esta expressão calcula a taxa de requisições bem-sucedidas (sem códigos de erro 5xx) em relação ao total de requisições, proporcionando uma medida de disponibilidade.

3. **Latência:**
   - *Definição:* A latência refere-se ao tempo que a aplicação leva para processar uma requisição. Utilizando percentis, podemos analisar diferentes aspectos da distribuição dos tempos de resposta.
     - *Mediana:* Representa o valor que divide o conjunto de dados ao meio, indicando o ponto onde 50% das requisições são processadas mais rapidamente e 50% mais lentamente.
     - *Percentil 90:* Indica o tempo abaixo do qual 90% das requisições são processadas.
     - *Percentil 99:* Indica o tempo abaixo do qual 99% das requisições são processadas.
   - *Expressões PromQL:*
     - Mediana: 
        ```
        histogram_quantile(0.5, sum(rate(golang_server_request_duration_seconds_bucket[1d])) by (le))
        ```
     - Percentil 90: 
        ```
        histogram_quantile(0.9, sum(rate(golang_server_request_duration_seconds_bucket[1d])) by (le))
        ```
     - Percentil 99: 
        ```
        histogram_quantile(0.99, sum(rate(golang_server_request_duration_seconds_bucket[1d])) by (le))
        ```
   - *Interpretação:* Essas expressões calculam os percentis da distribuição dos tempos de resposta, oferecendo insights sobre a latência em diferentes cenários.

### Experimentando com Docker Compose e Golang

Utilize um repositório com Golang, disponível em [Repositório SRE-ARTIGO](https://github.com/danielmeloramos/sre-artigo).
* Clone o projeto: git clone [https://github.com/danielmeloramos/sre-artigo.git];
* Inicie os serviços: `make build` e `make run`;
* Acesse as ferramentas:
    * Acesse as métricas (Golang): http://localhost:8000/metrics;
    * Acesse o data source Prometheus: http://localhost:9090;
    * Acesse o Grafana: http://localhost:3000 (usuário: admin, senha: admin);
    * Importe datasource no grafana apontando para o prometheus;
    * Monte gráfico básico, com o seguinte PromQL: `sum(increase(myapp_requests_total[1m]))`.

No final terá o seguinte resultado:

![Grafana dashboard](/assets/img/grafana-dashboard-exemplo.png)

### Conclusão

Ao implementar o framework SRE, alcançamos eficiência e confiabilidade utilizando o poder do Prometheus, Grafana e Golang. Os indicadores oferecem uma visão abrangente do desempenho do sistema, permitindo ajustes personalizados. Experimente essa abordagem dinâmica para elevar a confiabilidade do seu sistema e proporcionar uma experiência positiva aos usuários.

Fique à vontade para compartilhar suas ideias e experiências nos comentários.

Até breve,