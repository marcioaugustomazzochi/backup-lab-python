# 🔐 Projeto de Backup e Restauração

Este projeto demonstra a criação de backups, criptografia, restauração e verificação de integridade utilizando Python e Kali Linux.

---

## 🎯 Objetivo

- Automatizar backups de arquivos importantes  
- Criptografar os backups usando Fernet  
- Verificar integridade com hash SHA256  
- Restaurar os arquivos de forma segura  

---

## 🗂 Estrutura do Projeto

backup_lab/  
├── backup.py  
├── restore.py  
├── src/                  # scripts Python  
├── dados_importantes/    # arquivos a serem salvos (não versionar)  
├── backups/              # backups gerados (não versionar)  
├── logs/                 # logs de execução (não versionar)  
└── prints/               # prints e saídas dos comandos  

---

## 🛠 Tecnologias Utilizadas

- Python 3.10+ – linguagem principal  
- Cryptography (Fernet) – criptografia dos backups  
- Kali Linux – ambiente de desenvolvimento e testes  
- SHA256 – verificação de integridade  
- Git/GitHub – versionamento e publicação do código  

---

## 🏃 Guia de Uso (Passo a Passo)

1️⃣ Preparar os arquivos importantes  
$ ls dados_importantes/  
📌 O que fazer: coloque aqui os arquivos originais que serão incluídos no backup.

2️⃣ Executar o Backup  
$ python3 src/backup.py  
📌 O que acontece: o script gera um backup compactado e criptografado em backups/ e cria um hash SHA256 correspondente.  

3️⃣ Confirmar Backup Concluído  
[INFO] Backup criado: backups/backup_20260225_102723.zip.enc  
[INFO] Hash SHA256 gerado: backups/backup_20260225_102723.hash  
📌 O que fazer: verifique se o arquivo .zip.enc e o .hash foram criados corretamente.

4️⃣ Verificar Integridade  
$ sha256sum backups/backup_20260225_102723.zip.enc  
📌 O que acontece: o comando gera o hash SHA256 do backup. Compare com o conteúdo do arquivo .hash.

5️⃣ Validar Hash  
1234567890abcdef... backups/backup_20260225_102723.zip.enc  
📌 O que fazer: confirme que o hash confere. Se sim, o backup está íntegro.

6️⃣ Iniciar Restauração  
$ python3 src/restore.py  
📌 O que acontece: o script descriptografa e extrai os arquivos para dados_restaurados/.

7️⃣ Confirmar Restauração  
[INFO] Restauração concluída com sucesso!  
Arquivos extraídos em: dados_restaurados/  
📌 O que fazer: verifique se os arquivos foram restaurados corretamente.

8️⃣ Listar Arquivos Restaurados  
$ ls dados_restaurados/  
📌 O que fazer: confirme que os arquivos estão acessíveis e íntegros.

9️⃣ Consultar Logs de Backup  
$ cat logs/backup.log  
📌 O que fazer: analise o histórico detalhado da execução do backup.

🔟 Consultar Logs de Restauração  
$ cat logs/restore.log  
📌 O que fazer: analise o histórico detalhado da execução da restauração.

1️⃣1️⃣ Testar Falha de Integridade (opcional)  
$ echo "123456" > backups/backup_20260225_102723.hash  
$ python3 src/restore.py  
[ERROR] Hash SHA256 não confere! Arquivo corrompido ou modificado.  
📌 O que acontece: simula adulteração do hash para validar o mecanismo de integridade.

---

## ⚠️ Atenção

As pastas dados_importantes/, backups/, logs/ e a chave .key não devem ser versionadas no GitHub.  

Recomenda-se configurar um .gitignore com:  
venv/  
backups/  
logs/  
dados_importantes/  
*.key

---

## 🔗 Prints e Comandos do Projeto

### Estrutura da pasta prints

backup_lab/prints/  
01_backup_inicio.png         # Início da execução do backup  
02_backup_concluido.png      # Backup concluído  
03_hash_gerado.png           # Hash SHA256 gerado  
04_verificacao_hash_ok.png   # Verificação de integridade OK  
05_restore_inicio.png        # Início da restauração  
06_restore_concluido.png     # Restauração concluída  
07_restore_arquivos.png      # Arquivos restaurados  
08_logs_backup.png           # Exemplo de logs de backup  
09_logs_restore.png          # Exemplo de logs de restauração  
10_teste_falha_hash.png      # Teste de falha de integridade  
11_estrutura_dados.png       # Estrutura da pasta dados_importantes/  
12_estrutura_backups.png     # Estrutura da pasta backups/  

1️⃣ Execução do Backup  
$ python3 src/backup.py  
Função: cria um backup compactado e criptografado.  

2️⃣ Backup Concluído  
[INFO] Backup criado: backups/backup_20260225_102723.zip.enc  
[INFO] Hash SHA256 gerado: backups/backup_20260225_102723.hash  
Função: confirma que o backup e o hash foram criados.

3️⃣ Verificação de Integridade  
$ sha256sum backups/backup_20260225_102723.zip.enc  
Função: valida se o arquivo não foi alterado comparando com o hash.

4️⃣ Verificação OK  
1234567890abcdef... backups/backup_20260225_102723.zip.enc  
Função: confirma que o backup está íntegro.

5️⃣ Início da Restauração  
$ python3 src/restore.py  
Função: descriptografa e extrai os arquivos.

6️⃣ Restauração Concluída  
[INFO] Restauração concluída com sucesso!  
Arquivos extraídos em: dados_restaurados/  
Função: confirma que os arquivos foram restaurados corretamente.

7️⃣ Arquivos Restaurados  
$ ls dados_restaurados/  
Função: lista os arquivos restaurados.

8️⃣ Logs de Backup  
$ cat logs/backup.log  
Função: exibe o histórico detalhado do backup.

9️⃣ Logs de Restauração  
$ cat logs/restore.log  
Função: exibe o histórico detalhado da restauração.

🔟 Teste de Falha de Integridade  
$ echo "123456" > backups/backup_20260225_102723.hash  
$ python3 src/restore.py  
[ERROR] Hash SHA256 não confere! Arquivo corrompido ou modificado.  
Função: simula alteração do hash para validar a integridade.

1️⃣1️⃣ Estrutura da Pasta dados_importantes/  
$ ls dados_importantes/  
Função: mostra arquivos originais.

1️⃣2️⃣ Estrutura da Pasta backups/  
$ ls backups/  
Função: mostra os backups gerados.
