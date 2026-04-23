# 📁 Network Traffic & Logs — IDS & SIEM Tools

![Blue Team](https://img.shields.io/badge/Blue%20Team-185FA5?style=flat-square) 
![SOC](https://img.shields.io/badge/SOC-3C3489?style=flat-square) 
![Log Management](https://img.shields.io/badge/Log%20Management-3B6D11?style=flat-square) 
![IDS/SIEM](https://img.shields.io/badge/IDS%2FSIEM-854F0B?style=flat-square)

---

## 📚 Índice

| # | Tópico | Tipo |
|---|--------|------|
| 1 | Introdução ao tráfego de rede e registros com IDS e SIEM 
| 2 | A importância dos registros
| 3 | Práticas recomendadas para coleta e gerenciamento de registros 
| 4 | Variações de logs 
| 5 | Visão geral dos formatos de arquivos de registro

---

## 📋 O que são registros (logs)?

Um **registro** é um documento de eventos que ocorrem nos sistemas de uma organização. Cada entrada detalha um único evento em um dispositivo ou sistema.

As equipes de segurança acessam os logs via receptores de logs (como ferramentas **SIEM**), que consolidam os registros em um repositório central. Os profissionais de segurança usam esses registros para realizar a **análise de registros** — o processamento de examinar logs para identificar eventos de interesse.

> 💡 Os logs respondem às **5 perguntas** de uma investigação de incidente: **quem, o quê, quando, onde e por quê** ocorreu o incidente.

---

## 🗂️ Tipos de registros

| Tipo | Origem | Exemplos |
|------|--------|---------|
| **Rede** | Dispositivos de rede | Firewalls, roteadores, switches |
| **Sistema** | Sistema operacional | Windows, Linux, macOS, ChromeOS |
| **Aplicativo** | Softwares e apps | Apps mobile, sistemas web |
| **Segurança** | Ferramentas de segurança | Antivírus, IDS |
| **Autenticação** | Eventos de login | Tentativas bem-sucedidas ou falhas de acesso |

---

## ⚙️ Práticas recomendadas — Gerenciamento de registros

### O que registrar

- Configure as fontes de registro para **reduzir verbosidade excessiva**
- Foque nas fontes com maior probabilidade de conter informações úteis para o evento de interesse
- Evite registrar **PII** (informações de identificação pessoal) sem necessidade — pode ser proibido em algumas jurisdições

> ⚠️ **Erro comum:** registrar tudo. Excesso de logs aumenta custo de armazenamento, sobrecarrega sistemas e dificulta encontrar eventos importantes.

### Retenção de registros

Organizações em setores regulados devem atender a requisitos específicos:

| Setor | Regulação |
|-------|-----------|
| Setor público | FISMA |
| Saúde | HIPAA |
| Financeiro | PCI DSS, SOX, GLBA |

### Proteção dos registros

- Armazene logs em um **servidor de logs centralizado** — cria uma barreira entre o atacante e os registros
- Isso dificulta que agentes mal-intencionados modifiquem ou apaguem evidências

---

## 📄 Formatos de arquivos de registro

### JSON — JavaScript Object Notation

> Usado em: ambientes cloud, tecnologias web

Leve, legível, baseado em **pares chave-valor**.

```json
"User": {
  "id": "1234",
  "name": "user",
  "role": "engineer"
}
```

Componentes principais: pares chave-valor, vírgulas, aspas duplas, objetos `{}`, arrays `[]`

---

### Syslog

> Usado em: sistemas Unix/Linux

Padrão para geração e transmissão de logs. Porta `514` (texto simples) ou `6514` (criptografado).

```
<236>1 2022-03-21T01:11:11.003Z virtual.machine.com evntslog - ID01
[user@32473 iut="1" eventSource="Application" eventID="9999"]
This is a log entry!
```

Componentes:

- **Cabeçalho** — timestamp, hostname, aplicativo, message ID
- **Dados estruturados** — pares chave-valor entre `[ ]`
- **Mensagem** — descrição detalhada do evento
- **PRI (prioridade)** — urgência do evento entre `< >` (quanto menor, mais urgente)

---

### XML — eXtensible Markup Language

> Usado em: sistemas Windows

Formato nativo Windows. Usa **tags**, **elementos** e **atributos**.

```xml
<Event>
  <EventID>4688</EventID>
  <Version>5</Version>
</Event>
```

```xml
<EventData>
  <Data Name='SubjectUserName'>JSMITH</Data>
  <Data Name='SubjectDomainName'>ADCOMP</Data>
  <Data Name='NewProcessId'>0x1404</Data>
</EventData>
```

---

### CSV — Comma Separated Values

> Usado em: exportações gerais, firewalls, IPS, scanners

Valores separados por vírgula. A **posição** dos dados corresponde ao nome do campo (que pode não estar no registro).

```
2009-11-24T21:27:09.534255,ALERT,192.168.2.7,1041,x.x.250.50,80,TCP,ALLOWED,1:2001999:9,"ET MALWARE BTGrab.com Spyware Downloading Ads",1
```

---

### CEF — Common Event Format

> Usado em: SIEM, IDS/IPS

Pares chave-valor separados por `|`. Frequentemente transportado via Syslog.

**Sintaxe:**

```
CEF:Version|Device Vendor|Device Product|Device Version|Signature ID|Name|Severity|Extension
```

**Exemplo real:**

```
Sep 29 08:26:10 host CEF:1|Security|threatmanager|1.0|100|worm successfully stopped|10|src=10.0.0.2 dst=2.1.2.2 spt=1232
```

| Campo | Valor |
|-------|-------|
| Syslog Timestamp | Sep 29 08:26:10 |
| Hostname | host |
| Versão CEF | 1 |
| Vendor | Security |
| Product | threatmanager |
| Severidade | 10 |
| Extensão | src=10.0.0.2 dst=2.1.2.2 spt=1232 |

---

## 🔗 Recursos

- [RFC 5424 — Protocolo Syslog](https://www.rfc-editor.org/rfc/rfc5424)
- [generatedata.com — Gerador de logs de teste](https://generatedata.com/)
- [RFC 3339 — Formatos de data e hora (Timestamps)](https://www.rfc-editor.org/rfc/rfc3339)
