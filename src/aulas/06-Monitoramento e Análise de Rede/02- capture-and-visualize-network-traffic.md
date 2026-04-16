
# 01-Pacotes e capturas de pacotes

Pacotes são a unidade básica de dados transmitida em uma rede. Sempre que um dispositivo envia uma informação, como acessar um site, fazer login em um sistema ou enviar uma imagem, essa informação é dividida em pequenos blocos chamados **pacotes**.

Cada pacote contém informações suficientes para sair do dispositivo de origem, atravessar a rede e chegar corretamente ao destino.

## Estrutura do pacote

Um pacote é composto por três partes principais:

### Cabeçalho (Header)

Contém informações de controle e roteamento:

- IP de origem
- IP de destino
- protocolo
- porta
- tamanho
- TTL
- identificação

### Carga útil (Payload)

É o conteúdo real do pacote, como:

- texto
- imagem
- credenciais
- arquivos
- consultas DNS

### Rodapé (Trailer)

Usado principalmente para:

- verificação de erros
- integridade dos dados

---

## 02 - Saiba mais sobre capturas de pacotes

A captura de pacotes permite interceptar e analisar o tráfego da rede em detalhes. Isso ajuda a identificar atividades suspeitas, vazamento de dados, lentidão da rede e possíveis tentativas de invasão.

Ferramentas principais:

- Wireshark
- tcpdump
- TShark

Os arquivos de captura normalmente usam os formatos:

- PCAP
- PCAPng
- libpcap
- Npcap

---

## 03 - Interpretar comunicações de rede com pacotes

Interpretar pacotes significa entender a comunicação entre dispositivos.

Exemplo de fluxo:

1. consulta DNS
2. conexão TCP
3. requisição HTTP/HTTPS
4. resposta do servidor

Durante a análise, observamos:

- IP origem
- IP destino
- protocolo
- porta
- horário
- payload

---

## 04 - Reexaminar os campos do cabeçalho

### IPv4

Campos principais:

- Version
- Total Length
- TTL
- Protocol
- Source Address
- Destination Address

### IPv6

Campos principais:

- Version
- Traffic Class
- Flow Label
- Payload Length
- Hop Limit
- Source Address
- Destination Address

---

## 05 - Investigar os detalhes do pacote

### Filtros no Wireshark

Por protocolo:

```text
http
ssh
dns
icmp
```

Por IP:

```text
ip.addr == 172.21.224.
```

Por IP de origem:

```text
ip.src == 10.10.10.10
```

Por IP de destino:

```text
ip.dst == 4.4.4.4
```

Por porta:

```text
udp.port == 53
tcp.port == 25
```

Por MAC:

```text
eth.addr == 00:70:f4:23:18:c4
```

O recurso Follow Stream permite reconstruir a conversa entre dois dispositivos.

Recurso oficial: [Wireshrark.docs](https://www.wireshark.org/docs/) 🔗

---

## 06 - Recursos para a realização dos laboratórios

Este tópico apresenta como funcionam os laboratórios práticos na plataforma Qwiklabs / Cloud Skills Boost.

⚠️ Importante: este tópico é apenas explicativo. O laboratório real começa no tópico 8.

Como funciona

Ao acessar um laboratório real, normalmente o processo é:

---
1- clicar em Launch App ![launch app](../06-Monitoramento%20e%20Análise%20de%20Rede/imagens/01-launch-app.png)

---
2- abrir nova aba (**O Proprio navegador vai abrir a nova aba**)

---
3-clicar em Start Lab 

![Start lab](../06-Monitoramento%20e%20Análise%20de%20Rede/imagens/02start-lab.png)

---
04-utilizar o terminal Linux temporário

05-validar com Check my progress

06-finalizar em End Lab...

**A plataforma fornece um ambiente temporário para praticar:**

comandos Linux
análise de pacotes
Wireshark
atividades de cibersegurança

Link oficial: [Activity: Analyze your first packet with Wireshark](https://www.skills.google/focuses/47244697?parent=lti_session)

---

## 07 - Dicas de laboratório e solução de problemas

Antes de iniciar os laboratórios, é importante seguir algumas boas práticas.

Navegadores recomendados
Google Chrome
Firefox
Microsoft Edge
Safari

O navegador mais recomendado é o Google Chrome.

Solução de problemas!

**Se o laboratório não abrir corretamente:**

1- atualizar o navegador

2- limpar cache e cookies

3- usar modo anônimo

4- verificar a conexão com a internet

5- reiniciar o navegador

6- testar outro dispositivo

---
