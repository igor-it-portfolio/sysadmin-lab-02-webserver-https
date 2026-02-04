🌐 Projeto: Infraestrutura Web Segura na AWS (Semana 1)
Este repositório documenta a implementação de um servidor web de alta segurança, realizado como projeto final da primeira semana de estudos em administração de sistemas e cloud computing.

🚀 Resumo do Projeto
O objetivo foi configurar uma instância EC2 (Ubuntu) na AWS, tornando-a um servidor web capaz de servir conteúdo de forma segura via HTTPS, com renovação automática de certificados e proteção contra acessos não autorizados.
  README.md

Dia,Foco Técnico,Atividades Principais
1,Redes & Acesso,"Configuração de IP, DNS, Gateways e regras de Security Groups (Firewall)."
2,Protocolos,Estudo aprofundado de TCP/IP e do funcionamento do handshake HTTP/HTTPS.
3,Servidor Web,Instalação e otimização do Nginx.
4,Host Virtual,Configuração de Virtual Hosts para servir múltiplos domínios.
5,Diagnóstico,"Troubleshooting de rede utilizando ss, netstat e curl."
6,Criptografia,Implementação de SSL/TLS via Let's Encrypt e Certbot.
7,Projeto Final,"Consolidação da infraestrutura, Hardening de SSH e análise de logs."


🛡️ Diferenciais de Segurança Implementados
SSH Hardening: Desativação de autenticação por senha, permitindo apenas acesso via chaves criptográficas (.pem).

Gestão de Logs: Monitoramento em tempo real do access.log para identificação de bots e tentativas de exploit.

Forçamento de HTTPS: Redirecionamento automático (301) de todo tráfego inseguro (porta 80) para a porta segura (443).

DNS Dinâmico: Integração com DuckDNS para resolução de nome em IPs dinâmicos.

🛠️ Tecnologias Utilizadas
Cloud: AWS (EC2)

OS: Ubuntu Server 24.04 LTS

Web Server: Nginx

Security: Certbot, OpenSSH

Tools: Linux Terminal, PowerShell, DuckDNS
