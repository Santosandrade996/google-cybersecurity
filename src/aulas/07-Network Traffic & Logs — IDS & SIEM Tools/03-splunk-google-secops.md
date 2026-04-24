# 03 — Ferramentas SIEM: Splunk e Google SecOps

## 📚 Índice

| # | Tópico | Tipo |
|---|--------|------|
| 01 | Reexaminar as ferramentas SIEM
| 02 | Fontes de registro e ingestão de registros
| 03 | Consulta de eventos com o Splunk
| 04 | Consulta de eventos com o Google SecOps
| 05 | Métodos de pesquisa com ferramentas SIEM

---

## 📥 Ingestão de Registros no SIEM

O processo SIEM funciona em três etapas:

| Etapa | Descrição |
|-------|-----------|
| **1. Coletar e agregar** | Coleta dados de eventos de várias fontes |
| **2. Normalizar** | Converte os dados para um formato padrão e estruturado |
| **3. Analisar** | Correlaciona dados para identificar padrões e atividades suspeitas |

### Como os dados chegam ao SIEM

- O SIEM cria uma **cópia** dos dados recebidos — nunca modifica o log original
- A coleta pode ser feita **manualmente** (ineficiente para grandes redes) ou via **encaminhadores de log**

### Encaminhadores de Log (Log Forwarders)

Software que **automatiza** a coleta e o envio de dados de log ao SIEM.

> 💡 Alguns SOs já têm encaminhadores nativos. Se não, é necessário instalar um de terceiros e configurar quais logs enviar e para onde.

---

## 🔍 Métodos de Pesquisa — Splunk vs Google SecOps

### Splunk — SPL (Search Processing Language)

Linguagem de consulta própria do Splunk usada no app **Search & Reporting**.

#### Sintaxe básica

```spl
index=main fail
```

- `index=main` → busca no índice chamado `main`
- `fail` → retorna todos os eventos que contenham o termo

#### Pipe `|` — encadeamento de comandos

```spl
index=main fail | chart count by host
```

- O `|` passa a saída do primeiro comando como entrada do próximo
- `chart count by host` → transforma os resultados em gráfico agrupado por dispositivo

#### Curinga `*`

```spl
index=main fail*
```

- O `*` substitui qualquer caractere — retorna `fail`, `failed`, `failure`, etc.

> 💡 **Pro tip:** Use aspas duplas para busca de frase exata: `"login failure"` — só retorna eventos com essa frase completa.

---

### Google SecOps (Chronicle) — UDM e Raw Log Search

#### 1. Pesquisa UDM (Unified Data Model) — padrão

Pesquisa em dados já **ingeridos, normalizados e indexados**. Mais rápida.

```
metadata.event_type = "USER_LOGIN"
```

Campos UDM comuns:

| Campo | Descrição |
|-------|-----------|
| **Entidades** | Contexto do dispositivo, usuário ou processo envolvido |
| **Metadados do evento** | Tipo de evento, timestamps |
| **Metadados da rede** | Info sobre protocolos e eventos de rede |
| **Resultados de segurança** | Outcome do evento (ex: vírus detectado e colocado em quarentena) |

#### 2. Raw Log Search — logs brutos

Pesquisa nos logs **brutos e não analisados**. Mais lenta, mas útil quando os dados normalizados não têm o que você precisa.

- Suporta **expressões regulares** para refinar padrões
- Busca por: nomes de usuário, arquivos, hashes, etc.

---

## ⚖️ Splunk vs Google SecOps — Comparativo rápido

| | Splunk | Google SecOps |
|---|--------|--------------|
| Linguagem | SPL | UDM / Raw Log Search |
| Pesquisa padrão | SPL livre | UDM estruturado |
| Busca em logs brutos | Sim | Sim (Raw Log Search) |
| Suporte a regex | Sim | Sim (Raw Log) |
| Piping | Sim (`\|`) | Não aplicável |
| Curinga | `*` | Depende do campo |

---

## ✅ Conclusão

As ferramentas SIEM são o centro das operações de segurança — sem elas, correlacionar eventos de centenas de fontes diferentes seria inviável. Entender como os dados chegam até o SIEM (ingestão e encaminhadores) e como pesquisá-los de forma eficiente (SPL no Splunk ou UDM no Chronicle) é uma habilidade essencial para qualquer analista de SOC. Quanto mais precisa a consulta, mais rápida a resposta a incidentes.

---

## 🔗 Recursos

- [Referência de pesquisa do Splunk (SPL)](https://docs.splunk.com/Documentation/Splunk/latest/SearchReference/WhatsInThisManual)
- [Manual de pesquisa do Splunk](https://docs.splunk.com/Documentation/Splunk/latest/Search/GetstartedwithSearch)
- [Campos UDM do Google Security Operations](https://cloud.google.com/chronicle/docs/reference/udm-field-list)
- [Guia de início rápido do Google Security Operations](https://cloud.google.com/chronicle/docs/review-security-alert)
- [Guia de ingestão de dados no Splunk](https://docs.splunk.com/Documentation/Splunk/latest/Data/Howdoyouwanttoadddata)
- [Guia de ingestão no Google Security Operations](https://cloud.google.com/chronicle/docs/data-ingestion-flow)