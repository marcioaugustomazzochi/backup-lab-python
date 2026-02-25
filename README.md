# 🔐 Projeto de Backup e Restauração

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/) 
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) 
[![GitHub Repo Size](https://img.shields.io/badge/Repo-Size-blue)]() 
[![Build Status](https://img.shields.io/badge/Status-In%20Progress-yellow)]()

> Este projeto demonstra a criação de **backups**, **criptografia**, **restauração** e **verificação de integridade** utilizando **Python** e **Kali Linux**.

---

## 🎯 Objetivo

- 💾 Automatizar backups de arquivos importantes  
- 🔒 Criptografar os backups usando **Fernet**  
- ✅ Verificar integridade com **hash SHA256**  
- 🔄 Restaurar os arquivos de forma segura  

---

## 🗂 Estrutura do projeto


backup_lab/
│
├─ backup.py
├─ restore.py
├─ src/ # scripts Python
├─ dados_importantes/ # arquivos a serem salvos (não versionar)
├─ backups/ # backups gerados (não versionar)
├─ logs/ # logs de execução (não versionar)
└─ prints/ # prints e saídas dos comandos


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

## 🛠 Tecnologias utilizadas


Python 3.10+ – linguagem principal do projeto
Cryptography (Fernet) – criptografia dos backups
Kali Linux – ambiente de desenvolvimento e testes
SHA256 – verificação de integridade
Git/GitHub – versionamento e publicação do código


---

## 🏃 Como usar


📁 Criar arquivos importantes em dados_importantes/

🗜️ Executar backup:
python3 src/backup.py

🔑 Verificar integridade:
sha256sum backups/*.zip.enc

🔄 Restaurar backup:
python3 src/restore.py

⚠️ Testar integridade falha (opcional):
echo "123456" > backups/*.hash
python3 src/restore.py


> ⚠️ Atenção: os arquivos em `dados_importantes/`, `backups/`, `logs/` e a chave `.key` **não devem ser comitados** no GitHub.

---

## 📂 Estrutura de pastas sugerida


backup_lab/
│
├─ backup.py
├─ restore.py
├─ src/
├─ dados_importantes/ # ignorado pelo Git
├─ backups/ # ignorado pelo Git
├─ logs/ # ignorado pelo Git
└─ prints/ # prints de comandos e saídas


Adicionar `.gitignore` recomendado:


venv/
backups/
logs/
dados_importantes/
*.key


---

## 🔗 Documentação dos prints


Para ver todos os prints das saídas e comandos,
consulte o arquivo 'prints.md' na pasta 'prints/'.

---

Desenvolvido com Python e Kali Linux
