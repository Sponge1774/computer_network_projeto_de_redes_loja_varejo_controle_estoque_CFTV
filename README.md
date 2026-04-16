<div align="center">

<img src="https://img.shields.io/badge/Cisco_Packet_Tracer-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/PDF-FF0000?style=for-the-badge&logo=adobe-acrobat-reader&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Nota-Máxima_⭐-gold?style=for-the-badge"/>

# 🖧 Projeto de Redes — Loja de Varejo
### Controle de Estoque e CFTV

**Computer Network · UniFECAF · 2026**

[🇧🇷 Português](#-português) · [🇺🇸 English](#-english)

</div>

---

## 🇧🇷 Português

### 📋 Sobre o Projeto

Projeto acadêmico da disciplina **Computer Network** (UniFECAF — Análise e Desenvolvimento de Sistemas), consistindo no planejamento, documentação e simulação de uma rede de computadores completa para uma loja de varejo de roupas fictícia — a **Loja da Ana**.

O projeto integra os conceitos das quatro unidades da disciplina: tipos de redes, protocolos TCP/IP, endereçamento IPv4, cabeamento estruturado (ABNT NBR 14565) e segurança com WPA2, TLS e VPN. A simulação foi desenvolvida no **Cisco Packet Tracer** com 14 dispositivos e validada com testes de ping com **0% de perda de pacotes**.

> 🏆 **Resultado: Nota máxima na disciplina.**

---

### 🎯 Cenário

A cliente Ana, proprietária de uma loja de roupas, necessita de uma rede capaz de suportar simultaneamente:

- 🖥️ **3 caixas registradoras** acessando o sistema de controle de estoque
- 📹 **4 câmeras CFTV** com gravações armazenadas em servidor local
- 🖨️ **1 impressora** para recibos e relatórios
- 📱 **2 tablets** para atendimento ao cliente
- 💳 **1 maquininha de cartão** para pagamentos

---

### 🏗️ Arquitetura da Rede

```
Internet (WAN)
     │
     ▼
┌─────────────────┐
│  Roteador 1941  │  192.168.1.1  (GigabitEthernet)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Switch 2960-24TT│  192.168.1.254 (IP gerenciamento)
└──┬──┬──┬──┬────┘
   │  │  │  │
   ▼  ▼  ▼  ▼
Servidor  Caixas  Câmeras  Impressora  AP Wi-Fi
  .2    .10-.12  .20-.23     .30        .51
                                         │
                              ┌──────────┼──────────┐
                              ▼          ▼           ▼
                           Tablet-1   Tablet-2  Maquininha
                            .100       .101       .102
```

**Rede:** `192.168.1.0/24` — Todos os dispositivos com IPs estáticos

---

### 📡 Dispositivos e Endereçamento IP

| Dispositivo | Endereço IP | Conexão | Protocolo |
|---|---|---|---|
| Roteador Cisco 1941 | 192.168.1.1 | WAN/LAN | — |
| Switch 2960-24TT | 192.168.1.254 | Cabeada | — |
| Servidor Local | 192.168.1.2 | Cabeada | DHCP / DNS |
| Caixa 1 | 192.168.1.10 | Cabeada | **TCP** |
| Caixa 2 | 192.168.1.11 | Cabeada | **TCP** |
| Caixa 3 | 192.168.1.12 | Cabeada | **TCP** |
| Câmera CFTV 1 | 192.168.1.20 | Cabeada | **UDP** |
| Câmera CFTV 2 | 192.168.1.21 | Cabeada | **UDP** |
| Câmera CFTV 3 | 192.168.1.22 | Cabeada | **UDP** |
| Câmera CFTV 4 | 192.168.1.23 | Cabeada | **UDP** |
| Impressora | 192.168.1.30 | Cabeada | TCP/IP |
| Access Point | 192.168.1.51 | Cabeada | Wi-Fi WPA2 |
| Tablet 1 | 192.168.1.100 | **Wi-Fi** | TCP |
| Tablet 2 | 192.168.1.101 | **Wi-Fi** | TCP |
| Maquininha | 192.168.1.102 | **Wi-Fi** | TLS |

---

### 🔒 Segurança

| Mecanismo | Tecnologia | Aplicação |
|---|---|---|
| Wi-Fi | WPA2-PSK + AES (simétrico) | Protege o tráfego sem fio |
| Pagamentos | TLS (RSA handshake + AES) | Maquininha de cartão — PCI-DSS |
| Acesso remoto | VPN OpenVPN + AES-256 | Proposta arquitetural¹ |

> ¹ A VPN foi proposta como solução arquitetural. Não foi implementada na simulação devido à limitação do Cisco Packet Tracer, que não oferece suporte nativo ao protocolo OpenVPN. A solução é válida para o ambiente real de produção.

---

### 🧪 Conceitos Aplicados

| Unidade | Conteúdo | Aplicação no Projeto |
|---|---|---|
| I | LAN, WAN, WLAN, Topologias | Topologia estrela, segmentação cabeado/Wi-Fi |
| II | IPv4, DHCP, DNS, Infraestrutura | Endereçamento /24, servidor local |
| III | Cabeamento — ABNT NBR 14565 | UTP Cat5e no subsistema horizontal |
| IV | TCP, UDP, TLS, VPN, Criptografia | Protocolos por dispositivo, segurança em camadas |

---

### 📁 Estrutura do Repositório

```
computer_network_projeto_de_redes_loja_varejo_controle_estoque_CFTV/
│
├── 📄 relatorio_teorico_unifecaf_cn_final.pdf   # Relatório teórico completo (11 páginas)
├── 📄 parte_pratica.pdf                          # Diagrama, IPs e prints dos pings (8 páginas)
├── 📄 roteiro_video.pdf                          # Roteiro do vídeo pitch (5 páginas)
├── 🖧  computer-network-unifecaf.pkt             # Simulação no Cisco Packet Tracer
└── 📖 README.md                                  # Este arquivo
```

---

### ✅ Resultados da Simulação

Todos os testes de ping realizados com **0% de perda de pacotes**:

```
Caixa-1    → Servidor   (192.168.1.2)  ✓ 0% loss — TCP (estoque)
Câmera-1   → Servidor   (192.168.1.2)  ✓ 0% loss — UDP (CFTV)
Tablet-1   → Servidor   (192.168.1.2)  ✓ 0% loss — Wi-Fi WPA2
Caixas 2/3 → Todos      (192.168.1.x)  ✓ 0% loss
```

---

### ⚠️ Limitações Técnicas Identificadas

- **Laptop-PT vs Wi-Fi:** o dispositivo Laptop-PT não aceita módulos wireless (WPC300N, PT-LAPTOP-NM-1W) no Cisco Packet Tracer — retorna erro *"This module is not compatible"*. **Solução:** uso do TabletPC-PT, que possui Wi-Fi nativo integrado.
- **VPN:** o Cisco Packet Tracer não suporta OpenVPN nativamente. A VPN foi documentada como proposta arquitetural.
- **Roteador 1941:** utiliza interfaces **GigabitEthernet** (não FastEthernet como modelos mais antigos) — detalhe importante na configuração via CLI.

---

### 🛠️ Tecnologias Utilizadas

- **Cisco Packet Tracer** — Simulação e validação da rede
- **Python + ReportLab** — Geração dos relatórios em PDF
- **OBS Studio** — Gravação do vídeo pitch

---

### 👤 Autor

**Eduardo Souza Mattos**
R.A.: 35984 · Análise e Desenvolvimento de Sistemas · UniFECAF · 2026

---
---

## 🇺🇸 English

### 📋 About the Project

Academic project for the **Computer Network** course (UniFECAF — Systems Analysis and Development), consisting of the planning, documentation, and simulation of a complete computer network for a fictional retail clothing store — **Ana's Store**.

The project integrates concepts from all four course units: network types, TCP/IP protocols, IPv4 addressing, structured cabling (ABNT NBR 14565), and security with WPA2, TLS, and VPN. The simulation was built in **Cisco Packet Tracer** with 14 devices and validated with ping tests achieving **0% packet loss**.

> 🏆 **Result: Maximum grade in the course.**

---

### 🎯 Scenario

The client Ana, owner of a clothing store, needs a network capable of simultaneously supporting:

- 🖥️ **3 cash registers** accessing the inventory control system
- 📹 **4 CCTV cameras** with recordings stored on a local server
- 🖨️ **1 printer** for receipts and reports
- 📱 **2 tablets** for customer service
- 💳 **1 card payment terminal** for transactions

---

### 🏗️ Network Architecture

```
Internet (WAN)
     │
     ▼
┌─────────────────┐
│  Router 1941    │  192.168.1.1  (GigabitEthernet)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Switch 2960-24TT│  192.168.1.254 (management IP)
└──┬──┬──┬──┬────┘
   │  │  │  │
   ▼  ▼  ▼  ▼
Server  Registers  Cameras  Printer   AP Wi-Fi
  .2    .10-.12   .20-.23    .30        .51
                                         │
                              ┌──────────┼──────────┐
                              ▼          ▼           ▼
                           Tablet-1   Tablet-2  Card Terminal
                            .100       .101        .102
```

**Network:** `192.168.1.0/24` — All devices with static IPs

---

### 📡 Devices and IP Addressing

| Device | IP Address | Connection | Protocol |
|---|---|---|---|
| Cisco Router 1941 | 192.168.1.1 | WAN/LAN | — |
| Switch 2960-24TT | 192.168.1.254 | Wired | — |
| Local Server | 192.168.1.2 | Wired | DHCP / DNS |
| Register 1 | 192.168.1.10 | Wired | **TCP** |
| Register 2 | 192.168.1.11 | Wired | **TCP** |
| Register 3 | 192.168.1.12 | Wired | **TCP** |
| CCTV Camera 1 | 192.168.1.20 | Wired | **UDP** |
| CCTV Camera 2 | 192.168.1.21 | Wired | **UDP** |
| CCTV Camera 3 | 192.168.1.22 | Wired | **UDP** |
| CCTV Camera 4 | 192.168.1.23 | Wired | **UDP** |
| Printer | 192.168.1.30 | Wired | TCP/IP |
| Access Point | 192.168.1.51 | Wired | Wi-Fi WPA2 |
| Tablet 1 | 192.168.1.100 | **Wi-Fi** | TCP |
| Tablet 2 | 192.168.1.101 | **Wi-Fi** | TCP |
| Card Terminal | 192.168.1.102 | **Wi-Fi** | TLS |

---

### 🔒 Security

| Mechanism | Technology | Application |
|---|---|---|
| Wi-Fi | WPA2-PSK + AES (symmetric) | Protects wireless traffic |
| Payments | TLS (RSA handshake + AES) | Card terminal — PCI-DSS compliant |
| Remote Access | VPN OpenVPN + AES-256 | Architectural proposal¹ |

> ¹ The VPN was proposed as an architectural solution. It was not implemented in the simulation due to a limitation of Cisco Packet Tracer, which does not natively support the OpenVPN protocol. The solution is valid for a real production environment.

---

### 🧪 Concepts Applied

| Unit | Content | Project Application |
|---|---|---|
| I | LAN, WAN, WLAN, Topologies | Star topology, wired/wireless segmentation |
| II | IPv4, DHCP, DNS, Infrastructure | /24 addressing, local server services |
| III | Structured cabling — ABNT NBR 14565 | UTP Cat5e horizontal subsystem |
| IV | TCP, UDP, TLS, VPN, Cryptography | Per-device protocols, layered security |

---

### 📁 Repository Structure

```
computer_network_projeto_de_redes_loja_varejo_controle_estoque_CFTV/
│
├── 📄 relatorio_teorico_unifecaf_cn_final.pdf   # Full theoretical report (11 pages)
├── 📄 parte_pratica.pdf                          # Diagram, IPs and ping screenshots (8 pages)
├── 📄 roteiro_video.pdf                          # Video pitch script (5 pages)
├── 🖧  computer-network-unifecaf.pkt             # Cisco Packet Tracer simulation
└── 📖 README.md                                  # This file
```

---

### ✅ Simulation Results

All ping tests completed with **0% packet loss**:

```
Register-1  → Server   (192.168.1.2)  ✓ 0% loss — TCP (inventory)
Camera-1    → Server   (192.168.1.2)  ✓ 0% loss — UDP (CCTV)
Tablet-1    → Server   (192.168.1.2)  ✓ 0% loss — Wi-Fi WPA2
Registers 2/3 → All   (192.168.1.x)  ✓ 0% loss
```

---

### ⚠️ Technical Limitations Identified

- **Laptop-PT vs Wi-Fi:** the Laptop-PT device does not accept wireless modules (WPC300N, PT-LAPTOP-NM-1W) in Cisco Packet Tracer — returns *"This module is not compatible"* error. **Solution:** TabletPC-PT was used instead, as it has built-in native Wi-Fi.
- **VPN:** Cisco Packet Tracer does not natively support OpenVPN. The VPN was documented as an architectural proposal.
- **Router 1941:** uses **GigabitEthernet** interfaces (not FastEthernet like older models) — an important detail during CLI configuration.

---

### 🛠️ Technologies Used

- **Cisco Packet Tracer** — Network simulation and validation
- **Python + ReportLab** — PDF report generation
- **OBS Studio** — Video pitch recording

---

### 👤 Author

**Eduardo Souza Mattos**
Student ID: 35984 · Systems Analysis and Development · UniFECAF · 2026

---

<div align="center">

Made with 💙 by Eduardo Souza Mattos · UniFECAF 2026

</div>

