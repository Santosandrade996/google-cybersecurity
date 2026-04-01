# Módulo 2 - Segurança de Redes e Análise de Tráfego

Este módulo aprofunda os fundamentos de **segurança de redes**, com foco na identificação de ameaças, análise de ataques e interpretação de registros de tráfego.

Ao longo do conteúdo, foram abordados conceitos essenciais para a proteção de ambientes corporativos, leitura de logs e investigação de incidentes em redes de computadores.

---

## Segurança contra invasão de redes

A segurança contra invasões de rede tem como objetivo proteger sistemas, dispositivos e serviços contra acessos não autorizados e ações maliciosas.

Neste tópico, foram estudados os principais riscos que podem comprometer a infraestrutura de rede, como:

- acessos indevidos
- interceptação de dados
- exploração de vulnerabilidades
- indisponibilidade de serviços

Também foram reforçados os pilares da segurança da informação:

- **Confidencialidade**
- **Integridade**
- **Disponibilidade**

---

## Ataques de negação de serviço (DoS)

O ataque **DoS (Denial of Service)** consiste em sobrecarregar um sistema, servidor ou aplicação com múltiplas requisições, impedindo o acesso de usuários legítimos.

O objetivo principal é tornar o serviço indisponível.

Exemplos de impacto:

- lentidão no carregamento
- queda de site
- indisponibilidade de aplicações
- interrupção de serviços críticos

---

## Ler os registros do tcpdump

Neste tópico, foi estudada a leitura de logs gerados pela ferramenta `tcpdump`, muito utilizada na análise de tráfego de rede.

Os registros permitem identificar:

- endereço IP de origem
- endereço IP de destino
- protocolo utilizado
- portas de comunicação
- mensagens de erro
- horário do incidente

Essa análise é fundamental para identificar falhas de comunicação e possíveis incidentes de segurança.

---

## Ataque DDoS na vida real

O **DDoS (Distributed Denial of Service)** é uma evolução do ataque DoS.

Nesse caso, o ataque é realizado por múltiplos dispositivos simultaneamente, geralmente máquinas comprometidas em uma botnet.

Isso torna o ataque mais difícil de mitigar e aumenta significativamente o impacto no serviço.

Principais características:

- alto volume de tráfego
- múltiplas origens
- indisponibilidade do sistema
- degradação do desempenho da rede

---

## Atividade prática: Analisar a comunicação na camada de rede

Nesta atividade, foi realizada a análise de um incidente de segurança envolvendo tráfego de rede.

O cenário simulava a indisponibilidade de acesso a um site, em que usuários recebiam a mensagem:

`destination port unreachable`

Durante a investigação, foram analisados registros do `tcpdump`, identificando:

- uso do protocolo **UDP**
- tráfego relacionado ao **DNS**
- utilização da **porta 53**
- retorno de erro via **ICMP**

### Breve resumo da atividade

A atividade teve como objetivo identificar qual protocolo foi afetado durante o incidente e levantar uma possível causa raiz.

A análise indicou falha na comunicação com o servidor DNS, sugerindo indisponibilidade do serviço ou bloqueio na porta 53.

### Exemplo de atividade

**Analisar a comunicação na camada de rede - Módulo 2**

[📄 Acessar template da atividade em PDF](../Segurança-invasões-de-rede/template/Cybersecurity-incident-report-network-traffic-analysis.pdf)

---

## Aprendizado adquirido

Neste módulo, aprofundei conhecimentos em:

- segurança de redes
- análise de incidentes
- leitura de logs
- troubleshooting de DNS
- identificação de ataques DoS e DDoS
- investigação de tráfego de rede
