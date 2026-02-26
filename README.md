
# 🔐 Projeto de Backup e Restauração

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/Platform-Linux-black?logo=linux&logoColor=white)]()
[![Encryption](https://img.shields.io/badge/Encryption-Fernet-green)]()
[![Integrity](https://img.shields.io/badge/Integrity-SHA256-orange)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Project Status](https://img.shields.io/badge/Status-Functional-brightgreen)]()

> 🔐 Sistema de backup seguro com criptografia simétrica e verificação de integridade, desenvolvido em ambiente Linux para simulação de controles corporativos.

---

## 🎯 Objetivo
- 💾 Automatizar backups de arquivos importantes  
- 🔒 Criptografar os backups usando **Fernet**  
- ✅ Verificar integridade com **hash SHA256**  
- 🔄 Restaurar os arquivos de forma segura  
- 🛡 Detectar adulterações (tamper detection)

---

## 🗂 Estrutura do Projeto
backup_lab/
├── src/
│   ├── backup.py
│   └── restore.py
├── dados_importantes/    # arquivos a serem salvos (não versionar)
├── dados_restaurados/    # arquivos restaurados
├── backups/              # backups gerados (não versionar)
├── logs/                 # logs de execução (não versionar)
├── prints/               # prints e saídas dos comandos
├── IMPRESSOES.md         # documentação das execuções
├── .gitignore
└── README.md

---

## 🛠 Tecnologias Utilizadas
- Python 3.10+ – linguagem principal do projeto  
- Cryptography (Fernet) – criptografia dos backups  
- SHA256 (hashlib) – verificação de integridade  
- Kali Linux – ambiente de desenvolvimento e testes  
- Git/GitHub – versionamento e publicação do código  

---

## 🏃 Como Usar

### 📁 Criar arquivos importantes
Adicionar arquivos dentro da pasta `dados_importantes/`.

### 🗜️ Executar Backup
python3 src/backup.py

✔ Geração de arquivo criptografado `.zip.enc`  
✔ Cálculo automático de SHA256  
✔ Registro em log  

### 🔍 Verificar Integridade Manualmente
sha256sum backups/*.zip.enc

### 🔄 Restaurar Backup
python3 src/restore.py

✔ Descriptografia  
✔ Validação de integridade  
✔ Restauração segura  

### 🚨 Simular Violação de Integridade (Opcional)
echo "123456" > backups/*.hash
python3 src/restore.py

Saída esperada:
Integridade comprometida! Hash inválido.

---

## 🔎 Documentação das Execuções
Para visualizar todas as evidências de execução, saídas de comandos e testes realizados, consulte o arquivo `IMPRESSOES.md`  

Ele contém:
- Execução do backup  
- Geração de hash  
- Processo de criptografia  
- Restauração segura  
- Teste de violação de integridade  

---

## ⚠️ Observações Importantes
Itens que **não devem ser versionados no GitHub**:
- dados_importantes/  
- backups/  
- logs/  
- venv/  
- *.key  

.gitignore recomendado:
venv/
backups/
logs/
dados_importantes/
*.key

---

## ⚙️ Pré-requisitos
- 🐍 Python 3.10+  
- 🔐 Biblioteca `cryptography`  
- 💻 Sistema Linux (testado no Kali Linux)

Instalação do ambiente virtual:
python3 -m venv venv
source venv/bin/activate
pip install cryptography

---

## 📌 Status do Projeto
🟢 Concluído  
🔐 Funcional  
🧪 Testado com simulação de ataque  
📁 Totalmente documentado  

---

## 👨‍💻 Autor
Marcio Augusto Mazzochi  
Segurança da Informação | Cibersegurança | Projetos de Automação  

---

## ⭐ Apoie o Projeto
Se este projeto agregou valor ao seu aprendizado, considere deixar uma estrela no repositório.  

