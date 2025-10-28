# 🔐 Projeto de Segurança Cibernética - Ataques de Força Bruta com Medusa

## 📌 Descrição
Este projeto demonstra a execução de **ataques de força bruta** utilizando **Kali Linux** e a ferramenta **Medusa** contra ambientes vulneráveis (Metasploitable 2).  
A documentação inclui **prints reais dos testes realizados**, comandos utilizados e medidas de mitigação.

---

## 🛠️ Ambiente Configurado
- **Máquina atacante:** Kali Linux (VirtualBox)
- **Máquina alvo:** Metasploitable 2
- **Rede:** Host-only
- **Ferramentas:** Medusa, Nmap, Wordlists

---

## ✅ Etapas do Projeto

### 1. Teste de Conectividade (Ping)
Antes de iniciar os ataques, foi realizado um teste de conectividade para garantir que a máquina alvo estava acessível.

**Comando:**
```bash
ping 192.168.56.103
```

**Resultado:**
![Ping para Metasploitable](1000163683.png.jpg)

---

### 2. Varredura de Serviços com Nmap
Foi feita uma varredura para identificar portas abertas e serviços ativos.

**Comando:**
```bash
nmap -sV -p 21,22,80,445,139 192.168.56.103
```

**Resultado:**
![Scan Nmap](1000163692.png.jpg)

---

### 3. Ataque de Força Bruta em FTP com Medusa
Após identificar o serviço FTP ativo, foi realizado um ataque de força bruta utilizando Medusa.

**Comando:**
```bash
medusa -h 192.168.56.103 -u msfadmin -P pass.txt -M ftp
```

**Resultado:**
![Ataque FTP com Medusa](1000163693.png.jpg)

---

## 🛡️ Medidas de Mitigação
- **Senhas fortes:** Evitar credenciais fracas como "msfadmin".
- **Bloqueio de tentativas:** Implementar limite de tentativas para evitar ataques automatizados.
- **Monitoramento:** Analisar logs e alertas para detectar acessos suspeitos.

---

## 📚 Aprendizados
- A importância da análise de serviços antes do ataque.
- Como ferramentas como Medusa podem comprometer sistemas mal configurados.
- Necessidade de políticas de segurança robustas.

---

## 📂 Estrutura do Repositório
```
├── README.md
├── imagens/
│   ├── 1000163683.png.jpg  # ping
│   ├── 1000163692.png.jpg  # nmap
│   ├── 1000163693.png.jpg  # ftp attack
└── wordlists/
    ├── users.txt
    ├── pass.txt
```

---

## 🔗 Referências
- [Medusa - Ferramenta de força bruta](http://foofus.net/goons/jmk/medusa/medusa.html)
- [Metasploitable 2](https://sourceforge.net/projects/metasploitable/)
- [Kali Linux](https://www.kali.org/)
