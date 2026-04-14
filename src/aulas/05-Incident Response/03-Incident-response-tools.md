# Incident Response Tools and Detection Technologies

## 📌 Sobre

Este módulo aborda as principais ferramentas utilizadas na **detecção, documentação, monitoramento e resposta a incidentes de segurança**.

O conteúdo explora desde a importância da documentação até tecnologias essenciais como **IDS, IPS, EDR, SIEM e SOAR**, que são amplamente utilizadas por equipes de SOC e CSIRT.

---

## 🛠️ 01. Ferramentas de resposta a incidentes

As ferramentas de resposta a incidentes auxiliam as equipes de segurança a **identificar, investigar, registrar e responder rapidamente a ameaças**.

Entre as principais categorias estão:

- ferramentas de documentação
- sistemas de detecção
- plataformas de monitoramento
- ferramentas SIEM
- soluções SOAR
- EDR para endpoints

Essas tecnologias ajudam a reduzir o tempo de resposta e aumentam a capacidade de investigação.

---

## 📝 02. O valor da documentação

A documentação é um dos pilares mais importantes na resposta a incidentes.

Ela consiste em qualquer conteúdo registrado utilizado para orientar, instruir ou registrar um processo.

Exemplos:

- playbooks
- planos de resposta
- relatórios finais
- diários de incidentes
- políticas internas
- tickets

Uma documentação eficaz deve ser:

- clara
- objetiva
- consistente
- precisa

Durante um incidente, uma documentação bem feita reduz dúvidas e acelera a tomada de decisão.

### 📚 Exemplos de documentação

- **Playbooks:** passo a passo operacional
- **Relatórios:** resumo do incidente e ações tomadas
- **Tickets:** acompanhamento e histórico

### 🧰 Ferramentas de documentação

- Google Docs
- OneNote
- Evernote
- Notepad++
- Jira
- Google Sheets

---

## 🚨 03. Sistemas de detecção de intrusão (IDS)

O **IDS (Intrusion Detection System)** é uma ferramenta que monitora continuamente redes e sistemas em busca de atividades suspeitas.

Sua função é:

- detectar ameaças
- gerar alertas
- registrar eventos

O IDS **não bloqueia automaticamente** a ameaça.

Ele apenas avisa a equipe de segurança.

Exemplos:

- Snort
- Suricata
- Zeek
- Sagan

---

## 🔍 04. Visão geral das ferramentas de detecção

As principais ferramentas de detecção são:

### IDS

Detecta e alerta.

### IPS

Detecta, alerta e bloqueia.

### EDR

Monitora endpoints e responde automaticamente.

---

### 🛡️ IPS

O **IPS (Intrusion Prevention System)** funciona como o IDS, porém com capacidade de **interromper a ameaça automaticamente**.

Exemplo:

- bloquear IP
- alterar ACL
- impedir tráfego malicioso

---

### 💻 EDR

O **Endpoint Detection and Response** atua diretamente nos dispositivos finais.

Exemplo:

- notebook
- desktop
- celular corporativo

Além da detecção, ele usa:

- análise comportamental
- machine learning
- automação

Exemplos:

- Bitdefender EDR
- FortiEDR

---

## 📊 05. Gerenciamento de alertas e eventos com SIEM e SOAR

Essas ferramentas ajudam a centralizar e automatizar a resposta a incidentes.

### SIEM

Coleta, correlaciona e analisa logs.

### SOAR

Automatiza fluxos de resposta.

Exemplo:

- abrir ticket
- isolar endpoint
- bloquear IP automaticamente

---

## 🧠 06. Visão geral da tecnologia SIEM

O **SIEM (Security Information and Event Management)** é uma das ferramentas mais importantes para analistas SOC.

Sua função é:

- coletar logs
- agregar dados
- normalizar registros
- correlacionar eventos
- gerar alertas

---

### 🔄 Etapas do processamento SIEM

### 1. Coleta e agregação

![Coleta](../05-Incident%20Response/imagens/03SIEM.png)

Coleta logs de:

- firewalls
- servidores
- roteadores
- endpoints

Tudo é centralizado em um único local.

---

### 2. Normalização

![SIEM](../05-Incident%20Response/imagens/04.png)

Os dados são convertidos para um formato padrão.

Isso facilita buscas e correlação.

---

### 3. Análise

O sistema aplica regras para detectar padrões suspeitos.

Exemplo:

- múltiplos logins falhos
- acesso fora do horário
- IP desconhecido

---

### 📈 Vantagens do SIEM

- monitoramento em tempo real
- histórico de eventos
- alertas automáticos
- correlação de logs
- suporte a investigações

---

### 🧰 Exemplos de SIEM

- Splunk
- IBM QRadar
- Elastic
- Chronicle
- LogRhythm
- OSSIM

---

## 🎯 Objetivo do módulo

Compreender as principais ferramentas utilizadas por equipes de segurança para monitoramento, documentação, detecção e resposta a incidentes.
