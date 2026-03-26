# 🧠 Introdução à Comunicação em Rede

## 📌 O que é comunicação em rede?
![Redes](../Arquitetura%20de%20Rede/imagens/18.jpg)

É o processo de troca de dados entre dispositivos.

Exemplo simples:

* Você abre um site

* Seu computador envia uma requisição

* O servidor responde com os dados

 Isso acontece em forma de pacotes de dados

---

### 📦 O que são pacotes de dados?

Pacotes são unidades de informação que trafegam na rede contendo:

* Endereço de origem
* Endereço de destino
* Conteúdo da mensagem

---

## 🌐 Modelo TCP/IP

O modelo TCP/IP é o padrão utilizado na internet para comunicação entre dispositivos. Ele define como os dados devem ser transmitidos e organizados.

---

## 🧩 As 4 Camadas do Modelo TCP/IP

### 1️⃣ Aplicação

Responsável pela interação com o usuário.

**Exemplos de protocolos:**

* HTTP / HTTPS
* FTP
* SMTP

---

### 2️⃣ Transporte

Responsável pela entrega dos dados.

**Protocolos principais:**

* TCP (Transmission Control Protocol) → confiável
* UDP (User Datagram Protocol) → rápido

---

### 3️⃣ Internet

Responsável pelo endereçamento e roteamento dos dados.

**Protocolo principal:**

* IP (Internet Protocol)

---

### 4️⃣ Acesso à Rede

Responsável pela transmissão física dos dados.

**Inclui:**

* Cabos
* Wi-Fi
* Placas de rede

---

## ⚙️ Funcionamento na Prática

Ao acessar um site:

1. A camada de Aplicação envia a requisição (HTTP)
2. A camada de Transporte divide os dados (TCP/UDP)
3. A camada de Internet define o caminho (IP)
4. A camada de Acesso realiza a transmissão física

---

## 📚 Sobre o Modelo TCP/IP

* É o modelo utilizado na prática
* Possui 4 camadas
* Base da comunicação na internet

---

## 🧠 Modelo OSI

O modelo OSI (Open Systems Interconnection) é um modelo teórico utilizado para entender melhor o funcionamento das redes.

---

## 🧩 As 7 Camadas do Modelo OSI

1. **Física** → transmissão de bits (cabos, sinais)
2. **Enlace de Dados** → comunicação entre dispositivos da mesma rede
3. **Rede** → roteamento (IP)
4. **Transporte** → entrega dos dados (TCP/UDP)
5. **Sessão** → controle da comunicação
6. **Apresentação** → formatação e criptografia
7. **Aplicação** → interface com o usuário

---

## ⚔️ Diferença entre TCP/IP e OSI

![Modelo OSi e TCP/IP](../Arquitetura%20de%20Rede/imagens/17.png)

| TCP/IP            | OSI               |
| ----------------- | ----------------- |
| 4 camadas         | 7 camadas         |
| Modelo prático    | Modelo teórico    |
| Usado na internet | Usado para estudo |

---

## 🎯 Objetivo

Consolidar o conhecimento sobre comunicação em redes e os principais modelos utilizados, com foco em aplicações práticas na área de suporte técnico.

---

## 🚀 Observação

Este material faz parte dos estudos contínuos em redes de computadores, com foco em desenvolvimento profissional na área de tecnologia da informação.

---
