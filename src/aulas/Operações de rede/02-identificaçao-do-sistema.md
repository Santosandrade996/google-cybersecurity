# 🔐 Operações de Rede

## 📘 Módulo 2

---

## 🧾 Sobre o Projeto

Este módulo aborda conceitos de segurança em redes, incluindo firewalls, VPNs, segmentação, proxies e virtualização.

---

## 🔥 Firewalls e Segurança de Rede

![Firewall](../Operações%20de%20rede/imagens/01.png)

Firewalls controlam o tráfego de rede, permitindo ou bloqueando conexões com base em regras de segurança.

### 🛡️ Tipos

* Firewall de rede
* Firewall de host
* Firewall de aplicação

```bash id="f1"
sudo ufw enable
sudo ufw allow 80
sudo ufw deny 23
sudo ufw status
```

---

## 🌐 VPN (Virtual Private Network)

![VPN](../Operações%20de%20rede/imagens/02.avif)

VPNs criam conexões seguras e criptografadas pela internet.

### 🔒 Benefícios

* Privacidade
* Segurança
* Acesso remoto

---

## 🧩 Zonas de Segurança

![DMZ](../Operações%20de%20rede/imagens/03.png)

Divisão da rede em áreas com diferentes níveis de segurança:

* LAN
* WAN
* DMZ

---

## 🧮 Subredes e CIDR

![Subnetting](../Operações%20de%20rede/imagens/04.png)

CIDR define o tamanho da rede:

```
192.168.1.0/24
```

```bash id="f2"
ip a
ip route
```

---

## 🌍 Servidores Proxy

![Proxy](../Operações%20de%20rede/imagens/05.png)

Proxy atua como intermediário entre usuário e internet.

### 🎯 Funções

* Controle de acesso
* Cache
* Anonimato

```bash id="f3"
export http_proxy=http://proxy:porta
export https_proxy=http://proxy:porta
```

---

## 🖥️ Virtualização de Redes

![Virtualização](../Operações%20de%20rede/imagens/06.jpg)

Permite criar redes virtuais independentes.

### 💡 Vantagens

* Isolamento
* Redução de custos
* Flexibilidade

---

## 🔐 Protocolos VPN

### ⚡ WireGuard

* Rápido
* Moderno
* Simples

### 🔒 IPsec

* Muito seguro
* Amplamente usado

```bash id="f4"
sudo apt install wireguard
wg genkey | tee privatekey | wg pubkey > publickey
```

---
---

## ⭐ Observação

Este módulo complementa os conhecimentos do Módulo 1 e faz parte da trilha de redes.
