
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

## 08 - Laboratório: Analisar seu primeiro pacote com Wireshark

![Imagem wieshark](../06-Monitoramento%20e%20Análise%20de%20Rede/imagens/wireshark.png)

Neste laboratório prático, foi realizada a análise de um arquivo de captura de pacotes utilizando o **Wireshark**, com o objetivo de entender como o tráfego de rede é apresentado e investigado.

### Objetivo do laboratório

- Abrir um arquivo `.pcap` no Wireshark  
- Explorar a interface da ferramenta  
- Analisar informações de pacotes de rede  
- Aplicar filtros para localizar dados específicos  
- Identificar protocolos e comunicações entre dispositivos  

---

### Cenário

Neste laboratório, o papel assumido foi de um **analista de segurança** investigando o tráfego de rede de um usuário acessando um site.

A análise teve como foco:

- identificar IP de origem e destino  
- entender os protocolos utilizados  
- inspecionar pacotes de dados  
- aplicar filtros para encontrar informações relevantes  

---

### Ferramentas utilizadas

- Wireshark  
- Máquina virtual Windows (Qwiklabs / Cloud Skills Boost)  

---

### Etapas realizadas

1. Inicialização do laboratório via Qwiklabs  
2. Abertura da máquina virtual Windows  
3. Execução do Wireshark  
4. Abertura do arquivo de captura (`.pcap`)  
5. Análise dos pacotes na interface gráfica  
6. Aplicação de filtros como:
   - `ip.addr`
   - `dns`
   - `tcp`
   - `udp`
7. Inspeção de detalhes dos pacotes (camadas e payload)  

---

### Análises realizadas

Durante a análise, foi possível:

- identificar comunicação entre cliente e servidor  
- observar tráfego DNS e HTTP/HTTPS  
- visualizar IPs de origem e destino  
- analisar protocolos utilizados na comunicação  
- filtrar pacotes para investigação específica  

---

### Evidências do laboratório

Para manter o repositório organizado, todas as capturas de tela e análises detalhadas estão disponíveis na pasta abaixo:

📁 **Ver evidências do laboratório:**  

👉 [acessar o laboratorio](../06-Monitoramento%20e%20Análise%20de%20Rede/labs/01-analyze-your-first-Wireshark-package.md) 🧪

---

### Observações

- O uso de filtros no Wireshark é essencial para análise eficiente  
- A interpretação de pacotes é uma habilidade fundamental para atuação em SOC  
- A prática com arquivos `.pcap` permite simular investigações reais  

---

### Conclusão

![Demonstração do Wireshark](../06-Monitoramento%20e%20Análise%20de%20Rede/imagens/wireshark-.gif)

Este laboratório permitiu compreender como o tráfego de rede pode ser analisado na prática utilizando o Wireshark, reforçando conceitos como:

- análise de pacotes  
- protocolos de rede  
- filtragem de tráfego  
- investigação de comunicações  

Essa atividade é essencial para o desenvolvimento de habilidades em **cibersegurança e análise de redes**.

---

## 🧾 Conclusão do Módulo

Ao longo deste módulo, foram construídas as bases essenciais para o entendimento do monitoramento e da análise de redes no contexto da cibersegurança.

Inicialmente, foram apresentados os conceitos de **tráfego de rede e fluxos de comunicação**, destacando a importância de compreender como os dados circulam entre dispositivos. A partir disso, foi introduzido o conceito de **monitoramento de rede**, fundamental para manter a visibilidade e identificar atividades suspeitas.

Outro ponto importante foi a criação de uma **linha de base (baseline)**, que permite definir o comportamento normal da rede e facilita a detecção de anomalias, como picos de tráfego fora do horário padrão ou uso incomum de protocolos e portas.

Em seguida, o foco foi direcionado para os **pacotes de dados**, que são a unidade fundamental da comunicação em rede. Foram explorados seus componentes principais — cabeçalho, carga útil e rodapé — e como essas informações são utilizadas em investigações.

Também foram apresentados os **analisadores de protocolo de rede**, com destaque para o Wireshark, ferramenta essencial para capturar, visualizar e interpretar o tráfego de rede. Através dela, foi possível compreender como analisar pacotes em detalhes e aplicar filtros para encontrar informações relevantes.

Além disso, foram estudados os protocolos **IPv4 e IPv6**, incluindo seus campos de cabeçalho, que fornecem dados críticos como endereços IP, tempo de vida do pacote e protocolo utilizado.

Na parte prática, o laboratório permitiu aplicar todos esses conceitos em um cenário realista, onde foi possível:

- identificar IPs de origem e destino  
- analisar protocolos como DNS, TCP e HTTP/HTTPS  
- aplicar filtros no Wireshark  
- interpretar comunicações entre sistemas  

Por fim, o módulo demonstrou que a **análise de pacotes e o monitoramento de rede** são habilidades fundamentais para profissionais de segurança, permitindo detectar comportamentos anormais, investigar incidentes e proteger ambientes contra ameaças.

Este conjunto de conhecimentos é essencial para atuação em áreas como **SOC (Security Operations Center)** e análise de tráfego de rede.
