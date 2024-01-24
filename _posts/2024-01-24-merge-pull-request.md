---
layout: post
title: "Pull/Merge Requests: Melhorias, Benefícios e Boas Práticas"
date: 2024-01-24 00:00:00
image: '/assets/img/sre-prometheus-golang.jpg'
description: 'Desvendando os Segredos dos Pull/Merge Requests'
main-class: 'dev'
color: '#637a91'
tags:
- Boas Práticas
- Code review
- Pull/Merge Requests
categories:
- Pull/Merge Requests
image: "/assets/img/merge-pull-request/pull-merge-request.png"
twitter_text: 'Desvendando os Segredos dos Pull/Merge Requests.'
introduction: 'Neste artigo, embarcaremos em uma jornada para desvendandar os Segredos dos Pull/Merge Requests'
comments: 'true'
---

Olá, leitores!

Nos últimos tempos, tenho me envolvido cada vez mais no mundo dinâmico do desenvolvimento de software colaborativo, e uma prática que tem se destacado em minha rotina são os Pull/Merge Requests (PRs/MRs). 

Essa é uma ferramenta essencial para aprimorar a colaboração e garantir a qualidade do código em equipes de desenvolvimento. Neste artigo, compartilharei um exemplo prático de MR, destacando as melhorias, benefícios e boas práticas associadas a essa abordagem.

Ao longo do meu trabalho na Globo, tenho percebido o impacto positivo que a implementação cuidadosa de PRs/MRs pode ter no fluxo de trabalho da equipe.

## Introdução

Os Pull/Merge Requests (PRs/MRs) são um componente vital em qualquer ambiente de desenvolvimento colaborativo, e a aplicação de boas práticas nesse processo não apenas aprimora a qualidade do código, mas também fortalece a dinâmica da equipe. Neste artigo, exploraremos um exemplo prático de MR e destacaremos os benefícios para a equipe, colaboradores novos e a importância geral do que foi realizado.

![Merge/Pull Request](/assets/img/merge-pull-request/pull-merge-request.png)

## O que é um Pull/Merge Request?

Antes de mergulharmos nas melhorias específicas, é fundamental entender o que é um Pull/Merge Request. Em essência, um PR/MR é uma proposta de alteração de código. É a maneira pela qual os desenvolvedores sugerem modificações ao código-fonte, solicitando que essas alterações sejam "puxadas" ou "mescladas" para o ramo principal do projeto.

## Benefícios para a Equipe

1. **Colaboração Eficiente:** PRs/MRs facilitam a colaboração entre membros da equipe, permitindo revisões e discussões antes da fusão.
2. **Melhoria da Qualidade do Código:** A revisão por pares e o feedback contribuem para um código mais robusto e de alta qualidade.
3. **Visibilidade das Mudanças:** Todos na equipe podem acompanhar as alterações propostas, mantendo a transparência no desenvolvimento.

![Codereview](/assets/img/merge-pull-request/codereview.png)

## Benefícios para Colaboradores Novos

1. **Aprendizado Contínuo:** Colaboradores novos podem aprender com o código existente ao revisar PRs/MRs, acelerando seu processo de integração.
2. **Entendimento do Fluxo de Trabalho:** Ao participar de revisões, novos membros ganham compreensão sobre o processo de desenvolvimento da equipe.

## Importância do MR/PR Destacado

O exemplo de MR destacado nesta postagem foi crucial para testar gradualmente o uso do Google Cloud Storage (GCS) em um servico interno da Globo. Essa implementação estruturada permitiu:

1. **Título do MR/PR:** O título não é apenas uma descrição superficial, mas uma peça fundamental que comunica claramente o propósito e o escopo das alterações propostas.
![Titulo Mr](/assets/img/merge-pull-request/title-mr.png)
2. **Objetivo do MR/PR:** O objetivo é como uma bússola para os revisores e membros da equipe. Ele define claramente o propósito das alterações propostas, fornecendo uma visão rápida do que está sendo abordado. Um objetivo bem definido, muitas vezes vinculado a uma tarefa específica, promove uma compreensão comum entre os membros da equipe, alinhando todos na direção certa. No exemplo, o MR/PR está vinculado a uma tarefa específica no Jira, os revisores entenderão imediatamente o escopo e a intenção por trás das mudanças.
![Objetivo Mr](/assets/img/merge-pull-request/objetivo-mr.png)
3. **Como Foi Resolvido Tecnicamente:** Esta seção detalha as decisões técnicas tomadas durante a implementação. Explicar como os problemas foram abordados proporciona clareza e transparência sobre as escolhas feitas. Isso não apenas ajuda os revisores a entender o raciocínio por trás das mudanças, mas também facilita futuras colaborações e manutenções.
![Tech Mr](/assets/img/merge-pull-request/tech-mr.png)
4. **Testes (Como Testar):** A inclusão de instruções claras sobre como testar as alterações é crucial. Isso permite que os revisores e outros membros da equipe validem as mudanças de maneira eficaz. Destacar os testes realizados, fornecer ambientes para possíveis testes, tanto local ou ambiente específico para teste, colocar exemplos de chamadas, requests, logs é importante.
![Tech Mr](/assets/img/merge-pull-request/test-mr.png)
5. **Métricas/Monitoramento/Logs:** Adicionar métricas ou logs específicos em pontos críticos do código oferece uma visão valiosa do comportamento do sistema em produção. Ao integrar esses componentes em um MR/PR, não apenas construímos uma base sólida para revisões e integrações, mas também estabelecemos práticas que promovem a qualidade, a testabilidade e a observabilidade contínua em nossos projetos.
![Observabilidade Mr](/assets/img/merge-pull-request/observabilidade-mr.png)

## Conclusão

Ao seguir as boas práticas delineadas neste exemplo de MR, a equipe não apenas aprimorou a qualidade do código, mas também criou uma base sólida para a colaboração futura. A transparência, o aprendizado contínuo e a eficiência no processo de desenvolvimento são alguns dos muitos benefícios que emanam da implementação cuidadosa de Pull/Merge Requests.

Ao integrar essas práticas em seu fluxo de trabalho, as equipes podem garantir uma entrega mais suave, melhorar a qualidade do código e fortalecer a colaboração entre os membros da equipe. Em última análise, os PRs/MRs são mais do que simples solicitações de fusão; são ferramentas poderosas para impulsionar o desenvolvimento de software colaborativo e eficiente.

Fique à vontade para compartilhar suas ideias e experiências nos comentários.

Até breve,