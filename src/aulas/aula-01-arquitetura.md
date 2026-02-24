# 🌐 Introdução à Arquitetura de Redes

Este documento apresenta os fundamentos da Arquitetura de Redes, abordando conceitos essenciais como topologias, modelos OSI e TCP/IP, dispositivos de rede, protocolos e endereçamento IP.

---

## 📌 1. O que é Arquitetura de Rede?

Arquitetura de rede é o projeto estrutural de uma rede de comunicação.  
Ela define como dispositivos, protocolos e meios de transmissão são organizados para permitir a troca de dados.

Pode ser comparada à planta estrutural de um edifício — mas aplicada à comunicação entre sistemas computacionais.

---

## 🧩 2. Conceitos Fundamentais

### 🔹 Nó (Node)

Qualquer dispositivo conectado à rede:

- Computador
- Roteador
- Switch
- Smartphone
- Impressora

### 🔹 Link (Enlace)

Meio físico ou lógico que conecta dois nós.

**Físico:**

- Cabo Ethernet
- Fibra óptica
- Cabo coaxial

**Sem fio:**

- Wi-Fi
- Bluetooth
- 4G/5G

### 🔹 Protocolo

Conjunto de regras que define como os dispositivos se comunicam.

Sem protocolos, a comunicação seria impossível.

---

## 🔷 3. Topologias de Rede

A topologia define como os dispositivos estão conectados.

| Topologia | Descrição | Vantagem | Desvantagem |
|------------|------------|------------|------------|
| Barramento | Todos conectados ao mesmo cabo | Simples | Se o cabo falha, tudo para |
| Estrela | Conectados a um switch central | Fácil manutenção | Depende do dispositivo central |
| Anel | Conexão circular | Fluxo organizado | Uma falha pode afetar toda a rede |
| Malha (Mesh) | Múltiplas conexões entre nós | Alta redundância | Alto custo |
| Híbrida | Combinação de topologias | Flexível | Maior complexidade |

A topologia mais comum atualmente é a **Estrela**.

---

## 🌍 4. Classificação por Abrangência

- **PAN** – Rede pessoal (Bluetooth)
- **LAN** – Rede local (residência, empresa)
- **MAN** – Rede metropolitana
- **WAN** – Rede de longa distância (Internet)

---

## 🧠 5. Modelo OSI

O Modelo OSI divide a comunicação em 7 camadas:

### Funções principais

- Aplicação → Interface com o usuário (HTTP, FTP)
- Transporte → Controle de entrega (TCP, UDP)
- Rede → Endereçamento IP
- Enlace → Comunicação entre dispositivos vizinhos
- Física → Transmissão de bits

---

## 🌐 6. Modelo TCP/IP

Modelo prático usado na Internet.

| OSI | TCP/IP |
|------|---------|
| Aplicação, Apresentação, Sessão | Aplicação |
| Transporte | Transporte |
| Rede | Internet |
| Enlace + Física | Acesso à Rede |

Protocolos comuns:

- HTTP
- DNS
- TCP
- UDP
- IP

---

## 🖥 7. Componentes Físicos

- **Roteador** – Conecta redes diferentes
- **Switch** – Conecta dispositivos dentro da mesma LAN
- **Hub** – Dispositivo antigo que replica dados
- **Access Point** – Permite conexão Wi-Fi
- **Firewall** – Controla e filtra tráfego

---

## 🌐 8. Endereçamento IP

Todo dispositivo possui um endereço IP.

### IPv4

Formato: `192.168.0.1`

### IPv6

Formato: `2001:0db8:85a3::8a2e:0370:7334`

### Faixas de IP Privado

- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

---

## 🔄 9. TCP vs UDP

| Característica | TCP | UDP |
|----------------|------|------|
| Conexão | Orientado à conexão | Sem conexão |
| Confiabilidade | Garante entrega | Não garante |
| Velocidade | Mais lento | Mais rápido |
| Uso comum | Web, e-mail | Streaming, jogos |

---

## 🔁 10. Fluxo de Dados Simplificado

Ao acessar um site:

1. O navegador envia requisição HTTP
2. TCP organiza os pacotes
3. IP define o caminho
4. Ethernet ou Wi-Fi transmite os dados
5. O servidor responde pelo caminho inverso

---

## 🚀 Próximos Passos

- Sub-redes e CIDR
- Protocolos de roteamento (OSPF, BGP)
- Segurança de redes (Firewall, VPN, IDS/IPS)
- Redes Definidas por Software (SDN)
- Cloud Networking (AWS, Azure)

---

## 📌 Objetivo

Consolidar os fundamentos de Arquitetura de Redes como base para atuação em:

- Suporte Técnico
- Infraestrutura
- Segurança da Informação
- Cloud Computing

---

✍️ Documentação desenvolvida para fins educacionais.
