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

<img width="1920" height="936" alt="PRINT 1 Desktop do Kali" src="https://github.com/user-attachments/assets/eafdc11b-507e-4db4-903a-1a7be17184a4" />

---

### 2️⃣ Backup Concluído
[INFO] Backup criado: backups/backup_20260225_102723.zip.enc  
[INFO] Hash SHA256 gerado: backups/backup_20260225_102723.hash  
Função: confirma que o backup foi gerado com sucesso e que o hash de integridade foi criado.

<img width="1920" height="936" alt="PRINT 2 Terminal mostrando a criação das pastas" src="https://github.com/user-attachments/assets/4e77ffdf-6606-400f-a80a-20d2563cfd66" />

---

### 3️⃣ Verificação de Integridade
$ sha256sum backups/backup_20260225_102723.zip.enc  
Função: valida se o arquivo não foi alterado, comparando o hash SHA256.

<img width="1920" height="936" alt="PRINT 3 preparação do ambiente" src="https://github.com/user-attachments/assets/825d7a5f-3afd-4b69-90f7-649e4978dd22" />

---

### 4️⃣ Verificação OK
1234567890abcdef... backups/backup_20260225_102723.zip.enc  
Função: confirma que o hash confere e o backup está íntegro.

<img width="1920" height="936" alt="PRINT 4 02_backup_execution" src="https://github.com/user-attachments/assets/2d5030a9-9200-4936-a2f9-4c3e94bb2c26" />

---

### 5️⃣ Início da Restauração
$ python3 src/restore.py  
Função: inicia o processo de restauração dos arquivos criptografados.

<img width="1920" height="936" alt="PRINT 5 03_hash_validation" src="https://github.com/user-attachments/assets/dc1de98f-6c1a-4108-9ede-cbc9cd50d211" />

---

### 6️⃣ Restauração Concluída
[INFO] Restauração concluída com sucesso!  
Arquivos extraídos em: dados_restaurados/  
Função: confirma que os arquivos foram restaurados corretamente.

<img width="1920" height="936" alt="PRINT 6 05_restore_structured_success" src="https://github.com/user-attachments/assets/3402eaa2-8e10-4915-a8a3-a1e25454324b" />

---

### 7️⃣ Arquivos Restaurados
$ ls dados_restaurados/  
Função: lista os arquivos restaurados para verificar acessibilidade.

<img width="1920" height="936" alt="PRINT 7 06_logging_system" src="https://github.com/user-attachments/assets/f2e4d7d1-9ec7-4222-a86f-5b1988e945ec" />

---

### 8️⃣ Logs de Backup
$ cat logs/backup.log  
Função: exibe o histórico detalhado da execução do backup.

<img width="1920" height="936" alt="PRINT 8 07_venv_cryptography_install" src="https://github.com/user-attachments/assets/f6f03984-3329-418c-90b8-8eaa22090570" />

---

### 9️⃣ Logs de Restauração
$ cat logs/restore.log  
Função: exibe o histórico detalhado da execução da restauração.

<img width="1920" height="936" alt="PRINT 9 08_secure_backup_with_encryption" src="https://github.com/user-attachments/assets/4024c8e4-d055-4cf5-bf6a-2fca186974a7" />

---

### 🔟 Teste de Falha de Integridade
$ echo "123456" > backups/backup_20260225_102723.hash  
$ python3 src/restore.py  
[ERROR] Hash SHA256 não confere! Arquivo corrompido ou modificado.  
Função: simula alteração no hash para validar o mecanismo de integridade.

<img width="1920" height="936" alt="PRINT 10 09_encrypted_backup_restore_proof" src="https://github.com/user-attachments/assets/246d8529-4952-4216-ae0b-e06b000c2c56" />

---

### 1️⃣1️⃣ Estrutura da Pasta dados_importantes/
$ ls dados_importantes/  
Função: mostra os arquivos originais incluídos no backup.

<img width="1920" height="936" alt="PRINT 11 secure-backup-python" src="https://github.com/user-attachments/assets/bb6c076f-316f-4c99-b8f5-5d56b0fa26b2" />

---

### 1️⃣2️⃣ Estrutura da Pasta backups/
$ ls backups/  
Função: mostra os arquivos de backup gerados e armazenados.

<img width="1920" height="936" alt="PRINT 12 “Bloqueio de Restauração Após Adulteração de Hash – Teste de Integridade”" src="https://github.com/user-attachments/assets/1905b36b-e477-413d-944a-82fc0f34c43c" />

