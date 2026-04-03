# 📡 Introdução às Operações de Rede

## 📘 Módulo 1

---

## 🧾 Sobre o Projeto

Este projeto apresenta os conceitos fundamentais das operações de rede, abordando protocolos, comunicação entre dispositivos e segurança em redes, incluindo ambientes sem fio.

---

## 🧠 Operações de Rede

As operações de rede garantem que a comunicação entre dispositivos ocorra de forma eficiente, segura e contínua.

### 🔧 Principais atividades:

* Comunicação entre dispositivos
* Envio e recebimento de dados
* Monitoramento da rede
* Gerenciamento e segurança

---

## 🌐 Protocolos de Rede

Protocolos são conjuntos de regras que permitem a comunicação entre dispositivos em uma rede.

### ⚙️ Funções principais:

* Endereçamento de dispositivos
* Controle de transmissão de dados
* Detecção e correção de erros
* Garantia de entrega
* Segurança na comunicação

---

## 📊 Protocolos de Rede Comuns

### 🌍 HTTP e HTTPS

| Protocolo | Descrição                           |
| --------- | ----------------------------------- |
| HTTP      | Comunicação web sem segurança       |
| HTTPS     | Comunicação segura com criptografia |

```bash
# Testar conexão HTTP
curl http://google.com

# Testar conexão HTTPS
curl https://google.com
```

---

### 📡 TCP vs UDP

| Protocolo | Características                        |
| --------- | -------------------------------------- |
| TCP       | Confiável, garante entrega, mais lento |
| UDP       | Rápido, sem garantia de entrega        |

```bash
# Teste TCP
telnet google.com 80

# Teste UDP
nc -u google.com 53
```

---

### 📧 Protocolos de E-mail

| Protocolo | Função              |
| --------- | ------------------- |
| SMTP      | Envio de e-mails    |
| POP3      | Download de e-mails |
| IMAP      | Acesso ao servidor  |

```bash
# Testar servidor SMTP
telnet smtp.gmail.com 587
```

---

### 📁 FTP

```bash
# Conectar a um servidor FTP
ftp ftp.example.com
```

---

## 🧩 Protocolos de Suporte à Rede

### 🔹 DNS

```bash
# Descobrir IP de um domínio
nslookup google.com

# Alternativa
dig google.com
```

---

### 🔹 DHCP

```bash
# Renovar IP (Linux)
sudo dhclient

# Ver IP atual
ip a
```

---

### 🔹 ICMP

```bash
# Testar conectividade
ping google.com
```

---

## 📶 Protocolos de Segurança Wi-Fi

| Protocolo | Segurança  | Situação        |
| --------- | ---------- | --------------- |
| WEP       | Baixa      | Obsoleto        |
| WPA       | Média      | Pouco utilizado |
| WPA2      | Alta       | Muito utilizado |
| WPA3      | Muito alta | Atual           |

```bash
# Listar redes Wi-Fi (Linux)
nmcli dev wifi list

# Informações da rede
iwconfig
```

---

## 🚀 Aplicação Prática

Este conteúdo é aplicado em:

* Suporte técnico
* Administração de redes
* Diagnóstico de problemas
* Segurança da informação

---

## ⭐ Observação

Este material faz parte de uma trilha de estudos em redes e será atualizado com novos módulos.
