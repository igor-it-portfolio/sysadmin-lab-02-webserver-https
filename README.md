# 🌐 Infraestrutura Web Segura na AWS

Projeto prático de **Administração de Sistemas & Cloud Computing**, focado na implementação de um servidor web resiliente, seguro e monitorado em ambiente de nuvem.

> **Status do Projeto:** ✅ Concluído e Validado

---

## 🚀 Objetivo
Provisionar e configurar uma infraestrutura completa em uma instância **AWS EC2 (Ubuntu)**, transformando-a em um servidor web de produção que segue as melhores práticas de mercado:

- **Hardening de Acesso:** Proteção da camada de gerenciamento (SSH).
- **Segurança de Rede:** Configuração granular de Firewall (Security Groups).
- **Criptografia:** HTTPS nativo com Let's Encrypt e redirecionamento forçado.
- **Automação de DNS:** Configuração de DNS dinâmico para acessibilidade.
- **Auditoria:** Monitoramento ativo de logs de acesso e erro.

---

## 🏗️ Arquitetura da Solução

```text
AWS EC2 (Ubuntu Server)
│
├── Nginx (Web Server Engine)
├── Certbot (Gestão de SSL/TLS)
├── OpenSSH (Acesso Seguro RSA)
├── DuckDNS (Resolução de Nomes)
└── Security Groups (Firewall de Borda AWS)
```

---

## 🛡️ Camadas de Segurança Implementadas

### 🔐 SSH Hardening (Acesso Administrativo)
Para mitigar ataques de força bruta, a configuração do `/etc/ssh/sshd_config` foi endurecida:
- **Login por senha:** Desativado (`PasswordAuthentication no`).
- **Acesso Root:** Bloqueado (`PermitRootLogin no`).
- **Autenticação:** Exclusiva via par de chaves RSA (.pem).

### 🔥 Firewall (AWS Security Groups)
Configuração de regras de entrada (*Inbound Rules*) baseada no princípio do menor privilégio:

| Porta | Serviço | Protocolo | Origem | Ação |
| :--- | :--- | :--- | :--- | :--- |
| 22 | SSH | TCP | Meu IP (Restrito) | ALLOW |
| 80 | HTTP | TCP | Any (0.0.0.0/0) | REDIRECT |
| 443 | HTTPS | TCP | Any (0.0.0.0/0) | ALLOW |

### 🔒 HTTPS & Certificados
Implementação de criptografia em trânsito com **Certbot/Let's Encrypt**:
- **Redirecionamento 301:** Encaminhamento permanente de HTTP para HTTPS configurado no Nginx.
- **SSL/TLS:** Certificado emitido e validado.
- **Renovação:** Configurada via Crontab para automação total.

---

## 📊 Monitoramento e Operação (Evidências)

### Análise de Logs em Tempo Real
Acompanhamento dos acessos e detecção de comportamentos anômalos no Web Server:
```bash
# Monitorando acessos ao vivo
tail -f /var/log/nginx/access.log
```

### Validação de Renovação de Certificado
```bash
# Teste de renovação automática (Dry Run)
sudo certbot renew --dry-run
```

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Stack |
| :--- | :--- |
| **Cloud** | AWS EC2 (T3.Micro) |
| **Sistema Operacional** | Ubuntu Server 24.04 LTS |
| **Web Server** | Nginx |
| **Segurança** | OpenSSH, Certbot (SSL/TLS) |
| **DNS** | DuckDNS |
| **Interface** | Linux Terminal / Bash |

---

## 📈 Resultados Obtidos

- [x] Instância EC2 provisionada e atualizada.
- [x] Site publicado com protocolo **HTTPS** ativo e seguro.
- [x] Certificado configurado para **auto-renewal**.
- [x] Servidor blindado contra tentativas de login por senha.
- [x] Logs de acesso estruturados e monitorados.

---

## 👨‍💻 Autor
**Igor Cesar**
*SysAdmin / Infraestrutura / Cloud em formação*
