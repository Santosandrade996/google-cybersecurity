# Monitoramento e Análise de Redes em Cibersegurança

## 01 - Introdução ao monitoramento e análise de redes

O monitoramento de rede é um dos pilares da cibersegurança. Ele consiste em acompanhar continuamente o tráfego de dados que circula entre dispositivos conectados a uma rede, como computadores, servidores, roteadores e sistemas em nuvem.

Sempre que um usuário envia um e-mail, acessa um site, faz download de um arquivo ou assiste a um vídeo, ocorre comunicação de rede. Essa comunicação gera tráfego, que representa o fluxo de dados trafegando entre origem e destino.

O objetivo do monitoramento é identificar comportamentos normais e detectar atividades suspeitas ou maliciosas o mais rápido possível.

### Conceitos principais

**Tráfego de rede:** quantidade e tipo de dados que circulam na rede.

**Dados de rede:** informações transmitidas entre dispositivos.

**Monitoramento:** processo de observação e análise contínua da atividade da rede.

### Importância do monitoramento

O monitoramento permite:

* detectar acessos suspeitos
* identificar tentativas de invasão
* analisar comportamento incomum
* prevenir vazamento de dados
* manter a disponibilidade da rede

Em ambientes corporativos, isso é essencial para manter a segurança dos sistemas e a integridade das informações.

---

## 02 - A importância dos fluxos de tráfego de rede

O fluxo de tráfego representa o movimento das comunicações dentro da rede.

Esse fluxo inclui informações como:

* endereço IP de origem
* endereço IP de destino
* protocolo utilizado
* porta de comunicação
* quantidade de dados transferidos
* data e hora

Essas informações ajudam o analista de segurança a entender o comportamento normal do ambiente.

### Linha de base (Baseline)

A linha de base é um padrão de comportamento considerado normal para a rede.

Por exemplo, em uma empresa que opera das 9h às 17h, espera-se maior volume de tráfego nesse horário.

Se houver um pico de transferência de dados às 3h da manhã, isso foge do comportamento esperado e deve ser investigado.

A baseline é essencial para identificar desvios e possíveis ameaças.

### Fluxo, protocolos e portas

Os protocolos utilizam portas específicas para comunicação.

Exemplos:

* HTTP → porta 80
* HTTPS → porta 443
* SSH → porta 22
* DNS → porta 53

Quando há incompatibilidade entre protocolo e porta, isso pode indicar atividade maliciosa.

Exemplo:

HTTPS usando porta 8088 em vez da 443 pode ser uma tentativa de comunicação indevida.

---

## 03 - Manter a conscientização com o monitoramento de rede

A conscientização situacional é a capacidade de entender o que está acontecendo na rede em tempo real.

O monitoramento contínuo ajuda a detectar rapidamente:

* tráfego fora do padrão
* acessos não autorizados
* transferências incomuns
* comunicação com IPs suspeitos
* vazamento de dados

### Componentes monitorados

### Análise de fluxo

A análise de fluxo examina o movimento dos pacotes, protocolos e portas.

Isso ajuda a identificar padrões suspeitos, como comunicação entre máquinas internas e servidores externos desconhecidos.

### Carga útil do pacote (Payload)

A carga útil é o conteúdo real transportado pelo pacote.

Ela pode conter:

* arquivos
* mensagens
* credenciais
* dados sensíveis

A análise do payload ajuda a detectar malware, phishing e exfiltração.

### Padrões temporais

O horário do tráfego é um indicador importante.

Exemplo:

grande volume de dados fora do horário comercial pode indicar incidente.

---

## SOC e NOC

### SOC - Security Operations Center

O SOC é responsável por:

* monitorar ameaças
* detectar incidentes
* investigar eventos
* responder ataques

É a equipe focada em segurança.

### NOC - Network Operations Center

O NOC é responsável por:

* desempenho da rede
* disponibilidade
* tempo de atividade
* falhas técnicas

Enquanto o SOC cuida da segurança, o NOC cuida da operação da rede.

---

## Indicadores de Comprometimento (IoC)

Os IoCs são sinais que indicam possível invasão ou comprometimento.

Exemplos:

* IP malicioso
* hash de malware
* tráfego anormal
* acesso em horário incomum
* conexões C2

Esses indicadores ajudam na resposta rápida a incidentes.

---

## Ferramentas de monitoramento de rede

### IDS - Sistema de Detecção de Intrusão

O IDS monitora a atividade da rede e gera alertas quando detecta comportamento suspeito.

Exemplo:

* assinatura de malware
* tentativa de phishing
* tráfego anômalo

### Wireshark

Ferramenta utilizada para captura e análise de pacotes.

Permite visualizar detalhadamente:

* origem
* destino
* protocolos
* payload
* portas

### tcpdump

Ferramenta de linha de comando para captura de pacotes.

Muito utilizada em ambientes Linux.

---

## Recursos complementares para monitoramento de rede

Para aprofundar o estudo sobre os componentes de rede monitorados e técnicas utilizadas por atacantes, seguem os recursos citados no material:

* **MITRE ATT&CK – Network Traffic:** [https://attack.mitre.org/techniques/T1040/](https://attack.mitre.org/techniques/T1040/)
* **MITRE ATT&CK – Exfiltration:** [https://attack.mitre.org/tactics/TA0010/](https://attack.mitre.org/tactics/TA0010/)

Esses links são ótimos para consulta posterior e ajudam a entender como as técnicas são classificadas no contexto de ameaças reais.

---

## 04 - Ataques de exfiltração de dados

Exfiltração é a saída não autorizada de dados sensíveis da rede.

É uma das ameaças mais críticas em cibersegurança.

### O que pode ser exfiltrado

* dados de clientes
* documentos internos
* senhas
* planilhas
* bancos de dados
* arquivos confidenciais

### Como ocorre

Após comprometer um sistema, o atacante envia os dados para um servidor externo.

Isso pode acontecer por:

* HTTPS
* FTP
* e-mail
* DNS tunneling
* armazenamento em nuvem
* dispositivos USB

### Sinais de alerta

* grande volume de upload
* tráfego externo incomum
* horário suspeito
* IPs desconhecidos
* transferências repetitivas

### Importância da detecção

A exfiltração pode causar:

* vazamento de dados pessoais
* prejuízo financeiro
* danos à reputação da empresa
* não conformidade com LGPD

---

## Conclusão

O monitoramento e a análise de redes são essenciais para a proteção de ambientes corporativos.

Com o uso de linha de base, análise de tráfego, IoCs e ferramentas como IDS, Wireshark e tcpdump, os profissionais de segurança conseguem identificar ameaças, investigar incidentes e prevenir ataques, especialmente exfiltração de dados.

Esse processo é fundamental para a atuação em SOC, Blue Team e áreas de defesa cibernética.
