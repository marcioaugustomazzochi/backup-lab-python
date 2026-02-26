# 🔐 Projeto de Backup e Restauração

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![GitHub Repo Size](https://img.shields.io/badge/Repo-Size-blue)]() [![Build Status](https://img.shields.io/badge/Status-In%20Progress-yellow)]()

Este projeto demonstra a criação de backups, criptografia, restauração e verificação de integridade utilizando Python e Kali Linux.

---

## 🎯 Objetivo

- Automatizar backups de arquivos importantes  
- Criptografar os backups usando Fernet  
- Verificar integridade com hash SHA256  
- Restaurar os arquivos de forma segura  

---

## 🗂 Estrutura do projeto

- backup_lab/
  - backup.py
  - restore.py
  - src/                  # scripts Python
  - dados_importantes/    # arquivos a serem salvos (não versionar)
  - backups/              # backups gerados (não versionar)
  - logs/                 # logs de execução (não versionar)
  - prints/               # prints e saídas dos comandos

---

## 🛠 Tecnologias utilizadas

- Python 3.10+ – linguagem principal do projeto  
- Cryptography (Fernet) – criptografia dos backups  
- Kali Linux – ambiente de desenvolvimento e testes  
- SHA256 – verificação de integridade  
- Git/GitHub – versionamento e publicação do código  

---

## 🏃 Como usar

# Criar arquivos importantes em dados_importantes/
# Executar backup
python3 src/backup.py

# Verificar integridade
sha256sum backups/*.zip.enc

# Restaurar backup
python3 src/restore.py

# Testar integridade falha (opcional)
echo "123456" > backups/*.hash
python3 src/restore.py

⚠️ Atenção: os arquivos em `dados_importantes/`, `backups/`, `logs/` e a chave `.key` não devem ser comitados no GitHub.

---

## 📂 Estrutura de pastas sugerida

- backup_lab/
  - backup.py
  - restore.py
  - src/
  - dados_importantes/   # ignorado pelo Git
  - backups/             # ignorado pelo Git
  - logs/                # ignorado pelo Git
  - prints/              # prints de comandos e saídas

Adicionar `.gitignore` recomendado:

venv/
backups/
logs/
dados_importantes/
*.key

---

## 🔗 Prints e Comandos do Projeto

### Estrutura da pasta prints

backup_lab/prints/
- 01_backup_inicio.png         # Início da execução do backup
- 02_backup_concluido.png      # Backup concluído
- 03_hash_gerado.png           # Hash SHA256 gerado
- 04_verificacao_hash_ok.png   # Verificação de integridade OK
- 05_restore_inicio.png        # Início da restauração
- 06_restore_concluido.png     # Restauração concluída
- 07_restore_arquivos.png      # Arquivos restaurados
- 08_logs_backup.png           # Exemplo de logs de backup
- 09_logs_restore.png          # Exemplo de logs de restauração
- 10_teste_falha_hash.png      # Teste de falha de integridade
- 11_estrutura_dados.png       # Estrutura da pasta dados_importantes/
- 12_estrutura_backups.png     # Estrutura da pasta backups/

---

### 1️⃣ Execução do Backup
$ python3 src/backup.py  
Função: cria um backup compactado e criptografado dos arquivos presentes em dados_importantes/.

---

### 2️⃣ Backup Concluído
[INFO] Backup criado: backups/backup_20260225_102723.zip.enc  
[INFO] Hash SHA256 gerado: backups/backup_20260225_102723.hash  
Função: confirma que o backup foi gerado com sucesso e que o hash de integridade foi criado.

---

### 3️⃣ Verificação de Integridade
$ sha256sum backups/backup_20260225_102723.zip.enc  
Função: valida se o arquivo não foi alterado, comparando o hash SHA256.

---

### 4️⃣ Verificação OK
1234567890abcdef... backups/backup_20260225_102723.zip.enc  
Função: confirma que o hash confere e o backup está íntegro.

---

### 5️⃣ Início da Restauração
$ python3 src/restore.py  
Função: inicia o processo de restauração dos arquivos criptografados.

---

### 6️⃣ Restauração Concluída
[INFO] Restauração concluída com sucesso!  
Arquivos extraídos em: dados_restaurados/  
Função: confirma que os arquivos foram restaurados corretamente.

---

### 7️⃣ Arquivos Restaurados
$ ls dados_restaurados/  
Função: lista os arquivos restaurados para verificar acessibilidade.

---

### 8️⃣ Logs de Backup
$ cat logs/backup.log  
Função: exibe o histórico detalhado da execução do backup.

---

### 9️⃣ Logs de Restauração
$ cat logs/restore.log  
Função: exibe o histórico detalhado da execução da restauração.

---

### 🔟 Teste de Falha de Integridade
$ echo "123456" > backups/backup_20260225_102723.hash  
$ python3 src/restore.py  
[ERROR] Hash SHA256 não confere! Arquivo corrompido ou modificado.  
Função: simula alteração no hash para validar o mecanismo de integridade.

---

### 1️⃣1️⃣ Estrutura da Pasta dados_importantes/
$ ls dados_importantes/  
Função: mostra os arquivos originais incluídos no backup.

---

### 1️⃣2️⃣ Estrutura da Pasta backups/
$ ls backups/  
Função: mostra os arquivos de backup gerados e armazenados.
