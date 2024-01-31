---
layout: post
title: "Garantindo Segurança na Entrega de Funcionalidades"
date: 2024-01-31 16:00:00
image: '/assets/img/sre-prometheus-golang.jpg'
description: 'Entregando Funcionalidades com Segurança: A Importância de Métricas, Feature Flags e Rollbacks'
main-class: 'features'
color: '#2c0137'
tags:
- Segurança
- Métricas
- Feature Flags
categories:
- Desenvolvimento de Software
image: "/assets/img/deliver-features/deliver-features.png"
twitter_text: 'Garantindo Segurança na Entrega de Funcionalidades.'
introduction: 'Neste artigo, exploraremos como garantir a segurança na entrega de funcionalidades, destacando a importância de métricas, feature flags, logs e rollbacks.'
comments: 'true'
---

Olá, leitores!

Dentro da Globo, tenho mergulhado profundamente no dinâmico mundo do desenvolvimento de software seguro e eficiente. Uma prática que se destacou em minha rotina diária é garantir a entrega de funcionalidades com segurança, uma abordagem que se tornou essencial em nosso processo de desenvolvimento. 

Neste artigo, compartilharei insights e aprendizados provenientes dessa jornada, destacando a importância de métricas, feature flags, logs e rollbacks na garantia da segurança na entrega de funcionalidades.

## Introdução

Entregar funcionalidades com segurança é essencial para garantir a confiabilidade e integridade dos sistemas de software. Vamos explorar como algumas práticas e ferramentas podem contribuir significativamente para esse objetivo.

![Merge/Deliver Features](/assets/img/deliver-features/deliver-features.png)

## A Importância de Métricas

O uso de métricas é crucial para monitorar o desempenho e a saúde dos sistemas em tempo real. Ferramentas como Prometheus e Grafana permitem coletar, visualizar e analisar métricas importantes, como tempo de resposta, taxa de erro e uso de recursos. Isso possibilita a detecção precoce de problemas de segurança e desempenho, permitindo uma resposta proativa.

Como mencionado por Nicole Forsgren, Jez Humble e Gene Kim em [Accelerate: The Science of Lean Software and DevOps: Building and Scaling High Performing Technology Organizations](https://www.amazon.com.br/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339):

> "Métricas são a chave para melhorias. Se você não pode medir, você não pode melhorar."

## Utilização de Feature Flags

As feature flags são uma técnica poderosa para controlar o lançamento de novas funcionalidades. Elas permitem ativar ou desativar funcionalidades específicas em tempo real, o que é fundamental para lidar com situações de segurança inesperadas. Em caso de problemas, as feature flags possibilitam desativar rapidamente funcionalidades problemáticas sem impactar toda a aplicação.

![Merge/Feature Flag](/assets/img/deliver-features/feature-flag.png)

## Importância dos Logs

Logs são fundamentais para uma análise eficaz e diagnóstico de problemas em ambientes de produção. Eles permitem registrar informações de forma organizada e detalhada, facilitando a identificação e resposta a ameaças de segurança. Com logs, as equipes podem monitorar atividades suspeitas e tomar medidas corretivas rapidamente.

Como citado por Michael T. Nygard em [Release It! Design and Deploy Production-Ready Software](https://www.amazon.com/Release-Production-Ready-Software-Pragmatic-Programmers/dp/0978739213):

> "Logs são o espelho retrovisor do seu aplicativo. Quando tudo está indo bem, eles refletem a paisagem passada, permitindo que você se concentre na estrada à frente. Mas quando ocorre um acidente, eles se transformam em uma caixa preta de dados forenses."

## Alertas e Notificações

Além de monitorar métricas, features flags e logs, é crucial configurar alertas e notificações para garantir uma resposta rápida a eventos críticos. A configuração de alertas permite que a equipe seja notificada imediatamente sobre problemas de segurança, desempenho ou disponibilidade que exigem atenção.

![Merge/Slack Notification](/assets/img/deliver-features/slack-notification.png)

### Configuração de Alertas

Os alertas podem ser configurados para acionar notificações automáticas sempre que certos critérios forem atendidos. Isso pode incluir alta utilização de recursos, erros inesperados ou violações de segurança. Ao definir limiares e condições para os alertas, a equipe pode identificar e resolver problemas rapidamente.

### Integração com Ferramentas de Comunicação

A integração com ferramentas de comunicação, como o Slack, é essencial para garantir que os alertas sejam entregues rapidamente à equipe. A notificação proativa via Slack permite que os membros relevantes sejam informados em tempo real sobre eventos críticos, promovendo uma resposta rápida e colaboração eficaz.

Ao implementar alertas e notificações, as equipes fortalecem a segurança e a confiabilidade de seus sistemas, garantindo uma resposta ágil a situações adversas.

## Necessidade de Rollback

O rollback é uma prática essencial em situações de emergência ou falhas críticas. Ele permite reverter rapidamente para uma versão anterior do software em caso de problemas de segurança ou instabilidade. Ter a capacidade de realizar rollbacks de forma rápida e eficiente é fundamental para minimizar o impacto sobre os usuários finais e manter a integridade do sistema.

## Conclusão

Entregar funcionalidades com segurança é um desafio contínuo para equipes de desenvolvimento de software. A adoção de métricas com ferramentas como Prometheus e Grafana, o uso de feature flags, logs e a capacidade de rollback são aspectos essenciais para garantir a segurança na entrega de funcionalidades. Ao implementar essas práticas e ferramentas, as equipes podem fortalecer a segurança de seus sistemas e oferecer uma experiência confiável aos usuários finais.

Compartilhe suas experiências e ideias nos comentários!

Até breve,