# 📡 1-Captura de Pacotes com tcpdump

📌 Sobre

O tcpdump é uma ferramenta de linha de comando usada em sistemas Linux para capturar e visualizar pacotes de rede em tempo real.
Na prática, ele permite enxergar o tráfego que está passando pela rede, sendo muito útil para diagnóstico, análise e troubleshooting.

---

## ⚙️ Pré-requisitos

Sistema Linux (Ubuntu, Linux Mint, etc.)

Acesso ao terminal

Permissão de administrador (sudo)

Instalação:

```text
sudo apt install tcpdump
```

---

## 🔎 Identificando a interface de rede

Antes de iniciar a captura, é necessário identificar a interface ativa:

```text
ip a
```

Exemplos:

**eth0** → rede cabeada

**wlan0** → rede Wi-Fi

---

## ▶️ Captura básica

Para iniciar a captura de pacotes:

```text
sudo tcpdump -i wlan0
```

Esse comando exibe todos os pacotes da interface.

Para parar utilize o comando:

```text
Ctrl + C
```

---

## 🎯 Filtros de captura

Filtros são essenciais para analisar apenas o tráfego relevante.

Filtrar por IP:

```text
sudo tcpdump host 8.8.8.8
```

Filtrar por porta:

```text
sudo tcpdump port 80
```

Filtrar por protocolo (ICMP / ping):

```text
sudo tcpdump icmp
```

Combinar filtros:

```text
sudo tcpdump host 8.8.8.8 and port 80
```

---

## 💾 Salvando a captura

Para salvar os pacotes em um arquivo:

```text
sudo tcpdump -i wlan0 -w captura.pcap
```

Esse arquivo pode ser analisado posteriormente com o:
**👉 Wireshark**

---

## 👀 Melhorando a visualização

```text
sudo tcpdump -i wlan0 -nn
```

Evita resolução de nomes

Torna a saída mais rápida e direta

---

## 🔢 Limitando a captura

```text
sudo tcpdump -c 10
```

Captura apenas 10 pacotes e encerra automaticamente.

---

## 🧪 Teste prático

Abra dois terminais:

Terminal 1:

```sudo tcpdump icmp```

Terminal 2:

```ping google.com```

Resultado: visualização dos pacotes ICMP em tempo real.

---

## 🛠️ Aplicações práticas

Diagnóstico de conectividade

Monitoramento de tráfego

Identificação de problemas de rede

Análise de protocolos

Apoio em investigações de segurança

## ⚠️ Boas práticas

Utilizar filtros para evitar excesso de dados

Sempre executar com ```sudo```

Encerrar corretamente com ```Ctrl + C```

Evitar arquivos .pcap muito grandes

## 🚀Habilidades trabalhadas

Captura de pacotes em rede

Uso de filtros (IP, porta, protocolo)

Geração de arquivos .pcap

Análise básica de tráfego

---

## 📡 2-Visão Geral do tcpdump

## 📌 Sobre a análise de rede

Na área de redes e segurança, é comum utilizar ferramentas chamadas analisadores de protocolo de rede (ou sniffers).

Essas ferramentas permitem:

* Capturar o tráfego de rede
* Analisar os dados transmitidos
* Investigar problemas ou atividades suspeitas

Esse processo é conhecido como captura de pacotes.

### 🧠 O que é o tcpdump?

O tcpdump é uma ferramenta de linha de comando usada para capturar e analisar tráfego de rede em tempo real.
Ele funciona diretamente no terminal (CLI), permitindo que você visualize os pacotes que estão passando pela rede.

É muito utilizado em:

* Suporte técnico
* Administração de redes
* Segurança da informação

### 📦 Arquivos de captura (.pcap)

Ao capturar pacotes, você pode salvar os dados em um arquivo com extensão:

👉 .pcap (packet capture)

Esse arquivo armazena:

Os pacotes capturados
Informações da comunicação de rede

Depois, ele pode ser analisado com ferramentas como o Wireshark

### 🔐 Sobre tráfego criptografado

Nem todo tráfego pode ser interpretado diretamente.

Atualmente, muitos dados trafegam de forma criptografada, o que significa:

* O conteúdo está protegido
* Não é possível ler facilmente apenas com a captura

Para análise completa, seriam necessárias chaves de descriptografia

### ⚙️ Permissões necessárias

Para capturar pacotes, é necessário ter privilégios elevados no sistema.

Por isso, usamos:

```text
sudo tcpdump
```

```sudo``` → executa com permissões de administrador

### 🧩 Estrutura do comando

A sintaxe básica do tcpdump é:

```text
sudo tcpdump [-i interface] [opções] [filtros]
```

#### 📌 Componentes

* ```-i``` → define a interface de rede (ex: wlan0, eth0, any)
* opções → modificam o comportamento do comando
* filtros → limitam o tráfego capturado

### 🔎 Identificando interfaces

Antes de capturar, você precisa identificar a interface de rede:

```text
ip a
```

Ou:

```text
tcpdump -D
```

### 🧰 Principais opções

#### 💾 Salvar captura (```-w```)

```text
sudo tcpdump -i any -w captura.pcap
```

### 📂 Ler arquivo (```-r```)

```text
sudo tcpdump -r captura.pcap
```

### 📊 Nível de detalhes (```-v```)

```text
sudo tcpdump -v
```

```-v``` → detalhado

```-vv``` → mais detalhado

```-vvv``` → máximo

### 🔢 Limitar pacotes (```-c```)

```text
sudo tcpdump -i any -c 5
```

🚫 Desativar resolução de nomes (-n / -nn)

```text
sudo tcpdump -nn
```

Evita:

* Conversão de IP para nomes
* Conversão de portas para serviços

### 🎯 Filtros (expressões)

Filtros ajudam a capturar apenas o tráfego relevante.

Exemplos:

```text
tcpdump ip
```

* → apenas IPv4

```text
tcpdump ip6
```

* → apenas IPv6

```text
tcpdump port 80
```

→ tráfego da porta 80

### 🔗 Combinações

```text
tcpdump 'ip and port 80'
```

```text
tcpdump 'port 80 or port 443'
```

```text
tcpdump 'ip and (port 80 or port 443)'
```

### 📊 Interpretando a saída

Cada linha exibida representa um pacote capturado.

Ela contém informações como:

Data e hora

IP de origem

Porta de origem

IP de destino

Porta de destino

Dependendo das opções usadas, mais detalhes podem aparecer (como flags TCP e sequência de pacotes).

## 🛠️ Aplicação prática

O tcpdump pode ser utilizado para:

Diagnosticar problemas de rede

Monitorar tráfego

Verificar comunicação entre sistemas

Identificar atividades suspeitas

### 📚 Recursos para aprofundamento

Se quiser se aprofundar mais no uso do tcpdump, vale explorar materiais complementares:

📖 Tutoriais e guias oficiais do [tcpdump 📡📦](https://www.tcpdump.org/)

→ Conteúdos completos com exemplos e explicações detalhadas

🧠 Tutorial de expressões de filtro por [Daniel Miessler 📡📦](https://danielmiessler.com/blog/tcpdump)

→ Focado em como criar filtros mais avançados para análise de tráfego

---
# 🧪 3-Laboratório: Capturando seu primeiro pacote

## 📌 Sobre o laboratório

Neste laboratório, você vai colocar em prática o uso do tcpdump para capturar e analisar tráfego de rede em tempo real.

A proposta aqui é sair da teoria e realmente ver os pacotes acontecendo.

### 🎯 Objetivo

Durante o laboratório, você irá:

Identificar as interfaces de rede disponíveis
Capturar tráfego de rede ao vivo
Salvar pacotes em um arquivo .pcap
Aplicar filtros para analisar o tráfego

## ▶️ Acessar o laboratório

👉 [Qwiklabs📡📦](https://www.skills.google/focuses/47322891?parent=lti_session)

👉 [Laboratorio detalhado](../06-Monitoramento%20e%20Análise%20de%20Rede/labs/02-Packet-Capture-tcpdump.md)

O laboratório é realizado em um ambiente online (Qwiklabs/Coursera), onde você terá acesso a um terminal Linux configurado para prática.

---

## 4-📊 Atividade: Comparação de Analisadores de Rede

### 📌 Objetivo

Nesta atividade, foi realizada uma pesquisa sobre dois analisadores de protocolos de rede:

* Wireshark
* tcpdump

O objetivo foi identificar semelhanças e diferenças entre as ferramentas, entendendo onde cada uma se encaixa melhor no uso prático.

### 🔍 Semelhanças

* Ambos capturam pacotes de rede em tempo real
* Permitem análise de tráfego para diagnóstico e segurança
* Suportam filtros para isolar informações específicas
* Podem trabalhar com arquivos ```.pcap```

---

### ⚖️ Diferenças

| Característica      | Wireshark              | tcpdump                        |
| ------------------- | ---------------------- | ------------------------------ |
| Interface           | Gráfica (GUI)          | Linha de comando (CLI)         |
| Facilidade de uso   | Mais intuitivo         | Mais técnico                   |
| Visualização        | Detalhada e organizada | Texto bruto                    |
| Uso comum           | Análise aprofundada    | Captura rápida e automatização |
| Consumo de recursos | Maior                  | Menor                          |

---

## 🧩 Diagrama comparativo

![Diagrama](../06-Monitoramento%20e%20Análise%20de%20Rede/imagens/diagrama.png)

| 🔵 Wireshark | ⚫ tcpdump |
|-------------|-----------|
| Interface gráfica | Linha de comando |
| ✔ Visual detalhado | ✔ Leve e rápido |
| ✔ Fácil de usar | ✔ Ideal para scripts |
| ✔ Interface GUI | ✔ Baixo consumo |
| ❌ Mais pesado | ❌ Menos intuitivo |
| ❌ Requer GUI | ❌ Saída em texto |

---
### 🧠 Interpretação

O Wireshark é mais indicado quando você precisa visualizar e explorar os dados com profundidade

O tcpdump é mais usado quando você precisa de agilidade, automação ou trabalhar direto no terminal

# 🎯 Conclusão

Ao longo deste projeto, foram explorados conceitos fundamentais de análise de rede utilizando o tcpdump, desde a compreensão teórica até a aplicação prática em laboratório.

Durante o desenvolvimento, foram trabalhados pontos importantes como:

* Captura de pacotes em tempo real
* Uso de filtros para análise de tráfego
* Exportação e leitura de arquivos .pcap
* Interpretação de dados de rede

Além disso, a comparação com o Wireshark permitiu entender melhor o papel de cada ferramenta, destacando como elas se complementam no dia a dia de redes e segurança.

A realização do laboratório trouxe uma visão mais prática, permitindo observar o comportamento real do tráfego de rede e reforçando o aprendizado adquirido.