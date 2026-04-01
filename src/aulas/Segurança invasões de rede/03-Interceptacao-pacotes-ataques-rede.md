# Módulo 3 - Interceptação de Pacotes e Ataques à Rede

Este módulo aprofunda os conceitos de **ataques à rede de computadores**, com foco em interceptação maliciosa de tráfego, falsificação de endereços IP e identificação de comportamentos suspeitos na comunicação entre dispositivos.

Ao longo do conteúdo, foram estudadas técnicas utilizadas por invasores para capturar, manipular ou redirecionar pacotes dentro da rede.

---

## Interceptação maliciosa de pacotes

A interceptação maliciosa de pacotes ocorre quando um invasor captura dados que trafegam pela rede sem autorização.

O objetivo pode ser:

- roubo de credenciais
- captura de informações sensíveis
- espionagem de tráfego
- manipulação de dados em trânsito

Esse tipo de ataque compromete diretamente a **confidencialidade das informações**.

### Exemplo

Um invasor conectado à mesma rede pode utilizar ferramentas de captura para visualizar pacotes enviados entre cliente e servidor.

Isso pode expor:

- logins
- senhas
- cookies
- sessões de usuário
- dados bancários

---

## Falsificação de IPs (IP Spoofing)

A falsificação de IP, também conhecida como **IP Spoofing**, é uma técnica em que o atacante altera o endereço IP de origem do pacote para se passar por outro dispositivo.

O objetivo é mascarar a origem real do ataque ou ganhar confiança do sistema de destino.

### Principais riscos

- ocultação da origem do invasor
- ataques DDoS
- bypass de filtros simples
- redirecionamento de tráfego

Essa técnica é muito usada em ataques de rede e em tentativas de evasão de monitoramento.

---

## Visão geral das táticas de interceptação

Neste tópico, foram estudadas as principais técnicas de interceptação utilizadas em ataques à rede.

### Técnicas abordadas

- **Packet Sniffing**: captura de pacotes em trânsito
- **Man in the Middle (MITM)**: invasor entre cliente e servidor
- **ARP Spoofing**: falsificação de resolução ARP
- **IP Spoofing**: falsificação de IP
- **Session Hijacking**: sequestro de sessão

### Objetivo do invasor

O atacante busca obter acesso às comunicações da rede sem ser detectado.

---

## Atividade prática: Identificar ataques à rede de computadores

Nesta atividade prática da Coursera, foi realizada a identificação de comportamentos suspeitos em um cenário simulado de ataque à rede.

A atividade teve como foco a observação de padrões maliciosos relacionados à interceptação de pacotes e falsificação de identidade na rede.
![Prática na plataforma coursera](../Segurança%20invasões%20de%20rede/imagens/01.png)

### Breve resumo da atividade

Durante a atividade, foi feita a análise de um cenário em que foi necessário identificar sinais de ataque, como:

- alteração do tráfego
- comunicação suspeita
- falsificação de IP
- possíveis tentativas de interceptação

O objetivo foi desenvolver a capacidade de reconhecer táticas de ataque e compreender seus impactos na segurança da rede.

### Exemplo de atividade

**Analisar ataques à rede de computadores - Módulo 3**
[📄 Acessar template da atividade](../Segurança%20invasões%20de%20rede/template/Activity%20Exemplar:%20Analyze%20network%20attacks.pdf)

---

## Aprendizado adquirido

Neste módulo, aprofundei conhecimentos em:

- segurança de redes
- análise de tráfego malicioso
- identificação de spoofing
- interceptação de pacotes
- investigação de incidentes
- prevenção de ataques à rede
