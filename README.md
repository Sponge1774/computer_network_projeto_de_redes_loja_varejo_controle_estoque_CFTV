# 🖧 Projeto de Redes — Loja de Varejo, Estoque e CFTV

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?logo=cisco\&logoColor=white)
![Networking](https://img.shields.io/badge/Networking-TCP%2FIP-0078D4)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)

🇧🇷 **Português** | 🇺🇸 **English**

---

## 🇧🇷 Português

### 🎯 Sobre o projeto

Projeto acadêmico de **infraestrutura e redes de computadores**, desenvolvido para simular a infraestrutura de rede de uma loja de varejo.

O projeto utiliza **Cisco Packet Tracer** para representar equipamentos, endereçamento IP, conectividade, dispositivos de rede, CFTV e comunicação entre os diferentes componentes da infraestrutura.

### 🏢 Cenário

A infraestrutura contempla:

* 3 caixas registradoras;
* 4 câmeras de CFTV;
* 1 servidor;
* 1 impressora;
* 2 tablets;
* 1 maquininha de cartão;
* rede Wi-Fi;
* conexão com a Internet/WAN.

### 🌐 Endereçamento IP

Rede principal:

```text
192.168.1.0/24
```

| Dispositivo  | Endereço            |
| ------------ | ------------------- |
| Roteador     | `192.168.1.1`       |
| Servidor     | `192.168.1.2`       |
| Caixas       | `192.168.1.10–12`   |
| Câmeras      | `192.168.1.20–23`   |
| Impressora   | `192.168.1.30`      |
| Access Point | `192.168.1.51`      |
| Tablets      | `192.168.1.100–101` |
| Maquininha   | `192.168.1.102`     |

### 🏗️ Topologia simplificada

```text
                 Internet / WAN
                       │
                       ▼
                Roteador Cisco
                       │
                       ▼
                 Switch 2960
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       Servidor      Caixas       CFTV
                                     
                       │
                       ▼
                  Access Point
                   /         \
                  ▼           ▼
              Tablets     Maquininha
```

### 🔒 Segurança

O projeto considera mecanismos e conceitos relacionados à segurança da infraestrutura:

* WPA2-PSK/AES;
* TLS;
* VPN;
* segmentação de dispositivos;
* controle de acesso;
* análise de protocolos TCP/UDP.

A VPN foi tratada como proposta arquitetural, considerando as limitações do ambiente de simulação utilizado.

### 🧪 Validação

Foram realizados testes de conectividade no ambiente simulado.

**Resultado:** 0% de perda de pacotes nos testes documentados.

### 📁 Principais arquivos

* Arquivo de simulação do Cisco Packet Tracer;
* Relatório teórico;
* Documentação prática;
* Roteiro de apresentação;
* `README.md`.

### 🛠️ Tecnologias e conceitos

* Cisco Packet Tracer;
* TCP/IP;
* IPv4;
* DHCP;
* DNS;
* Wi-Fi;
* WPA2;
* TLS;
* VPN;
* CFTV;
* Cabeamento estruturado;
* Redes LAN/WAN/WLAN.

### 🎓 Contexto acadêmico

Projeto desenvolvido durante a formação em **Análise e Desenvolvimento de Sistemas — UniFECAF**.

**Autor:** Eduardo Souza Mattos
**R.A.:** 35984
**Ano:** 2026

---

## 🇺🇸 English

### 🎯 About the project

Academic **computer networking and infrastructure** project designed to simulate the network infrastructure of a retail store.

The project uses **Cisco Packet Tracer** to model network devices, IP addressing, connectivity, CCTV, Wi-Fi, and communication between infrastructure components.

### 🏢 Scenario

The infrastructure includes:

* 3 cash registers;
* 4 CCTV cameras;
* 1 server;
* 1 printer;
* 2 tablets;
* 1 payment terminal;
* Wi-Fi;
* Internet/WAN connectivity.

### 🌐 Network

```text
192.168.1.0/24
```

### 🔒 Security

The project covers WPA2-PSK/AES, TLS, VPN concepts, device segmentation, access control, and TCP/UDP protocol analysis.

### 🧪 Validation

Connectivity tests were performed in the simulated environment.

**Result:** 0% packet loss in the documented tests.

### 🛠️ Technologies

Cisco Packet Tracer, TCP/IP, IPv4, DHCP, DNS, Wi-Fi, WPA2, TLS, VPN, CCTV, structured cabling, LAN/WAN/WLAN.

### 🎓 Academic context

Developed during the **Systems Analysis and Development** program at UniFECAF.

**Author:** Eduardo Souza Mattos
**Student ID:** 35984
**Year:** 2026
