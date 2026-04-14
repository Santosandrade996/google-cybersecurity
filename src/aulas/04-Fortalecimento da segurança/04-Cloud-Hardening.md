# Fortalecimento da Segurança na Nuvem

## 📌 Sobre

Este módulo aborda as principais práticas de segurança aplicadas a ambientes em nuvem, com foco na proteção de dados, controle de acesso, segurança de rede e uso de criptografia.

A segurança na nuvem é essencial para proteger informações, aplicações e serviços hospedados em provedores cloud, reduzindo riscos de acessos indevidos e vazamento de dados.

---

## ☁️ Endurecimento da nuvem

O endurecimento da nuvem, também conhecido como **cloud hardening**, consiste na aplicação de medidas que tornam o ambiente em nuvem mais seguro.

O objetivo é reduzir vulnerabilidades e minimizar a superfície de ataque.

Entre as principais práticas estão:

- autenticação multifator (MFA)
- revisão de permissões de acesso
- princípio do menor privilégio
- atualização de sistemas
- monitoramento de atividades suspeitas
- backups regulares

Essas ações ajudam a proteger contas, servidores, aplicações e arquivos armazenados na nuvem.

---

## 🌐 Segurança de rede na nuvem

A segurança de rede na nuvem tem como objetivo proteger a comunicação entre usuários, dispositivos e serviços.

As principais medidas incluem:

- configuração de firewalls
- regras de tráfego de entrada e saída
- grupos de segurança
- segmentação de sub-redes
- uso de VPN
- restrição de acesso por endereço IP

Essas práticas evitam acessos não autorizados e ajudam a proteger o tráfego de dados.

---

## 🔐 Segurança na nuvem

A segurança na nuvem envolve a proteção geral dos recursos armazenados ou executados no ambiente cloud.

Isso inclui:

- arquivos
- bancos de dados
- aplicações
- máquinas virtuais

Também é importante o uso de **IAM (Identity and Access Management)** para controlar quem pode acessar cada recurso.

Além disso, este tópico aborda algumas considerações importantes:

- **configuração correta dos serviços**, evitando falhas e permissões indevidas
- **superfície de ataque**, já que cada serviço ativo pode representar um novo ponto de entrada
- **ataques de dia zero**, relacionados a vulnerabilidades ainda não conhecidas
- **visibilidade e rastreamento**, por meio de logs e ferramentas de monitoramento
- **auditorias e conformidade**, realizadas pelo provedor de nuvem

Outro conceito essencial é o **modelo de responsabilidade compartilhada**, no qual:

- o provedor de nuvem é responsável pela infraestrutura
- a organização cliente é responsável pelos dados, acessos e configurações

Boas práticas:

- perfis de acesso por função
- logs de atividades
- auditorias
- políticas de segurança
- monitoramento de login

---

## 🔒 Criptografia e segurança na nuvem

A criptografia é fundamental para proteger informações sensíveis.

Ela pode ser aplicada em:

- **dados em repouso** → armazenados
- **dados em trânsito** → transferidos
- **dados em processamento** → em uso

Isso garante que, mesmo que os dados sejam interceptados, não possam ser lidos sem a chave correta.

Exemplos de informações protegidas:

- dados pessoais
- documentos corporativos
- senhas
- informações financeiras

Este tópico também inclui:

- **gerenciamento de chaves criptográficas**
- uso de **TPM (Trusted Platform Module)**
- uso de **CloudHSM**
- **eliminação criptográfica**, que destrói as chaves e torna os dados inacessíveis

A criptografia é uma das principais formas de garantir a confidencialidade e integridade dos dados na nuvem.

---

## 🎯 Objetivo do módulo

Compreender como fortalecer a segurança em ambientes de nuvem por meio de controle de acesso, proteção de rede, monitoramento e criptografia.
