# 02 — Monitoramento de Segurança com IDS e Ferramentas de Detecção

## 📚 Índice

| # | Tópico | Tipo |
|---|--------|------|
| 01 | Monitoramento de segurança com ferramentas de detecção
| 02 | Ferramentas e técnicas de detecção
| 03 | Componentes de uma assinatura de detecção
| 04 | Examinar assinaturas com o Suricata 
| 05 | Examinar os registros de Suricata
| 06 | Visão geral da Suricata
| 07 | Recursos para a realização dos laboratórios
| 08 | Atividade: Explorar assinaturas e registros com o Suricata | 📁[Laboratório](./labs/lab-01-suricata-assinaturas-logs.md) |

---

## 🔍 Tipos de IDS

### HIDS — Host-based Intrusion Detection System

- Instalado como **agente diretamente no endpoint** (computador ou servidor)
- Monitora atividade **interna** do host: sistema de arquivos, uso de recursos, atividade do usuário
- Detecta comportamentos anormais locais, como instalação de aplicativo não autorizado
- Gera log e envia alerta quando algo suspeito é detectado

### NIDS — Network-based Intrusion Detection System

- Instalado em dispositivos estratégicos da rede
- Monitora o **tráfego de rede** de diferentes dispositivos
- Gera log e alerta quando tráfego malicioso é detectado

> 💡 Usar **HIDS + NIDS** juntos oferece uma abordagem em múltiplas camadas — visão completa do ambiente.

---

## ⚙️ Técnicas de Detecção

### Análise baseada em Assinatura

Detecta eventos comparando o tráfego com **padrões conhecidos de atividade maliciosa** (assinaturas).

| | |
|---|---|
| ✅ Vantagem | Baixa taxa de falsos positivos para ameaças conhecidas |
| ❌ Desvantagem | Não detecta ameaças desconhecidas (zero-day) |
| ❌ Desvantagem | Assinaturas podem ser contornadas por atacantes |
| ❌ Desvantagem | Banco de dados de assinaturas precisa de atualização constante |

### Análise baseada em Anomalia

Detecta **comportamentos fora do padrão** comparando com uma linha de base (baseline).

| Fase | Descrição |
|------|-----------|
| Treinamento | Coleta dados do comportamento normal para estabelecer a baseline |
| Detecção | Atividade atual é comparada com a baseline — desvios geram alertas |

| | |
|---|---|
| ✅ Vantagem | Capaz de detectar ameaças novas e desconhecidas |
| ❌ Desvantagem | Alta taxa de falsos positivos |
| ❌ Desvantagem | Se houver ataque durante o treinamento, ele vira parte da baseline |

---

## 🛡️ Suricata

Ferramenta open source que pode atuar como:

| Modo | Função |
|------|--------|
| **IDS** | Monitora tráfego e gera alertas (baseado em rede ou host) |
| **IPS** | Detecta **e bloqueia** tráfego malicioso (requer configuração extra) |
| **NSM** | Produz e salva logs de rede para análise forense e resposta a incidentes |

### Estrutura de uma Regra Suricata

```
alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)
```

| Componente | Descrição | Exemplo |
|------------|-----------|---------|
| **Ação** | O que fazer quando a regra é ativada | `alert`, `drop`, `pass`, `reject` |
| **Cabeçalho** | Protocolo, IPs e portas de origem/destino, direção | `http $HOME_NET any -> $EXTERNAL_NET any` |
| **Opções de regra** | Parâmetros de personalização entre `( )` | `msg`, `flow`, `content`, `sid`, `rev` |

#### Opções de regra comuns

| Opção | Função |
|-------|--------|
| `msg:` | Texto do alerta exibido quando a regra é acionada |
| `flow:` | Define a direção do fluxo (ex: `established,to_server`) |
| `content:` | Conteúdo específico a ser buscado no pacote |
| `sid:` | ID único da assinatura |
| `rev:` | Versão/revisão da regra |

> ⚠️ A **ordem das opções de regra importa** — alterar a ordem muda o significado da regra.
> A Suricata processa as ações nesta ordem padrão: `pass → drop → reject → alert`

### Arquivo de configuração

- Arquivo: `suricata.yaml` (formato YAML)
- Define como o Suricata interage com o ambiente

### Arquivos de log gerados

| Arquivo | Descrição | Uso |
|---------|-----------|-----|
| `eve.json` | Log padrão e principal. Detalhado, formato JSON. Contém `flow_id` para correlação | Análise forense, SIEM, resposta a incidentes |
| `fast.log` | Log mínimo com info básica de IP e porta | Verificações rápidas — formato legado, não recomendado para IR |

---

## ✅ Conclusão

O monitoramento de segurança com IDS é uma camada essencial na defesa de redes e sistemas. Combinar **HIDS e NIDS** garante visibilidade tanto nos endpoints quanto no tráfego de rede. Saber distinguir entre detecção por **assinatura** (eficaz contra ameaças conhecidas) e por **anomalia** (capaz de pegar o desconhecido) ajuda a entender as limitações de cada abordagem e como usá-las de forma complementar.

O **Suricata** centraliza essas capacidades em uma única ferramenta — podendo atuar como IDS, IPS ou NSM — e o domínio da escrita de regras personalizadas e da leitura dos logs (`eve.json`) é uma habilidade fundamental para qualquer analista de SOC.

---

## 🔗 Recursos

- [Guia do usuário da Suricata](https://suricata.readthedocs.io/en/suricata-6.0.0/index.html)
- [Recursos da Suricata](https://suricata.io/features/)
- [Gerenciamento de regras](https://suricata.readthedocs.io/en/suricata-6.0.0/rule-management/suricata-update.html)
- [Análise de desempenho de regras](https://suricata.readthedocs.io/en/suricata-6.0.0/configuration/suricata-yaml.html)
- [Introdução à criação de regras do Suricata](https://suricata.readthedocs.io/en/latest/rules/intro.html)
- [Exemplos de Eve.json com jq](https://suricata.readthedocs.io/en/latest/output/eve/eve-json-examplesjq.html)
