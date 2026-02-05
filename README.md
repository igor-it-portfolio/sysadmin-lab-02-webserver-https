# 🌐 Infraestrutura Web Segura na AWS
Projeto prático de **Administração de Sistemas + Cloud Computing**, focado na criação de um servidor web seguro, exposto na internet com HTTPS, boas práticas de hardening e monitoramento.

---

## 🚀 Objetivo
Provisionar uma instância **EC2 Ubuntu** na AWS e transformá-la em um **servidor web seguro e produtivo**, aplicando:

- Segurança de acesso (SSH Hardening)
- Firewall (Security Groups)
- HTTPS com Let's Encrypt
- Redirecionamento forçado HTTP → HTTPS
- Monitoramento de logs
- DNS dinâmico
- Boas práticas de Linux + Nginx

---

## 🏗️ Arquitetura

AWS EC2 (Ubuntu)
│
├── Nginx (Web Server)
├── Certbot (SSL/TLS)
├── OpenSSH (Acesso seguro)
├── DuckDNS (DNS dinâmico)
└── Security Groups (Firewall AWS)

## 🛡️ Segurança Implementada

### 🔐 SSH Hardening
- Login por senha desativado
- Acesso apenas via chave `.pem`
- Root login bloqueado

### 🔥 Firewall (Security Groups)
- 22 → SSH restrito
- 80 → HTTP
- 443 → HTTPS

### 🔒 HTTPS obrigatório
- Certificado SSL automático (Let's Encrypt)
- Redirecionamento 301 HTTP → HTTPS
- Renovação automática via cron

### 📊 Monitoramento
- Análise em tempo real:
```bash
tail -f /var/log/nginx/access.log

🛠️ Tecnologias Utilizadas
Categoria	Stack
Cloud	AWS EC2
Sistema	Ubuntu Server 24.04 LTS
Web Server	Nginx
Segurança	OpenSSH, Certbot
DNS	DuckDNS
CLI	Linux Terminal, PowerShell

📈 Resultados

✅ Site publicado com HTTPS
✅ Certificado renovando automaticamente
✅ Servidor protegido contra brute force
✅ Logs monitorados
✅ Infraestrutura pronta para produção
