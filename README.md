# 🛡️ Simulação de Ataques Brute Force com Kali Linux e Medusa em Ambientes Vulneráveis

Projeto prático desenvolvido para o desafio da **Digital Innovation One (DIO)**. O objetivo deste trabalho é simular cenários controlados de ataques de força bruta (*Brute Force*), *password spraying* e automação de credenciais contra serviços de rede (FTP, Web e SMB) no ambiente vulnerável **Metasploitable 2** e **DVWA**, demonstrando a perspectiva defensiva e aplicando medidas de mitigação.

---

## 📐 Arquitetura do Ambiente de Testes

O laboratório foi construído em ambiente isolado de testes utilizando o **Oracle VirtualBox** em uma rede local dedicada (**Host-Only / Rede Interna**), garantindo a contenção do tráfego de auditoria.

| Máquina Virtual | Sistema Operacional | Função no Laboratório | IP Simulado |
| :--- | :--- | :--- | :--- |
| **Atacante** | Kali Linux | Execução de varreduras e testes de estresse com Medusa | `192.168.56.100` |
| **Alvo** | Metasploitable 2 | Servidor com serviços vulneráveis (FTP, SMB, DVWA) | `192.168.56.101` |

---

## 🔎 Fase 1: Reconhecimento e Mapeamento do Alvo

Antes de executar as validações de força bruta, foi realizada uma varredura de portas com o **Nmap** para mapear os serviços ativos no servidor de destino.

```bash
nmap -sV -Pn 192.168.56.101
