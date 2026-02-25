# 📸 Prints e Comandos do Projeto

Este arquivo documenta os **prints das saídas**, **exemplos de execução** e **comandos utilizados** no projeto de backup e restauração.

---

## 🗂 Estrutura da pasta `prints`

```text
backup_lab/prints/
├── 01_backup_inicio.png         # Início da execução do backup
├── 02_backup_concluido.png      # Backup concluído
├── 03_hash_gerado.png           # Hash SHA256 gerado
├── 04_verificacao_hash_ok.png   # Verificação de integridade OK
├── 05_restore_inicio.png        # Início da restauração
├── 06_restore_concluido.png     # Restauração concluída
├── 07_restore_arquivos.png      # Arquivos restaurados
├── 08_logs_backup.png           # Exemplo de logs de backup
├── 09_logs_restore.png          # Exemplo de logs de restauração
├── 10_teste_falha_hash.png      # Teste de falha de integridade
├── 11_estrutura_dados.png       # Estrutura da pasta dados_importantes/
└── 12_estrutura_backups.png     # Estrutura da pasta backups/
🏃 Exemplos de execução
1️⃣ Executando o backup

$ python3 src/backup.py

📌 Função: cria um backup compactado e criptografado dos arquivos em dados_importantes/.

2️⃣ Backup concluído

[INFO] Backup criado: backups/backup_20260225_102723.zip.enc
[INFO] Hash SHA256 gerado: backups/backup_20260225_102723.hash

📌 Função: confirma que o backup foi gerado com sucesso e o hash foi criado.

3️⃣ Verificando integridade

$ sha256sum backups/backup_20260225_102723.zip.enc

📌 Função: valida se o arquivo não foi alterado comparando o hash SHA256.

4️⃣ Verificação de integridade OK

1234567890abcdef... backups/backup_20260225_102723.zip.enc

📌 Função: confirma que o hash confere e o backup está íntegro.

5️⃣ Início da restauração

$ python3 src/restore.py

📌 Função: inicia o processo de restauração dos arquivos criptografados.

6️⃣ Restauração concluída

[INFO] Restauração concluída com sucesso!
Arquivos extraídos em: dados_restaurados/

📌 Função: confirma que os arquivos foram restaurados corretamente.

7️⃣ Arquivos restaurados

$ ls dados_restaurados/

📌 Função: lista os arquivos restaurados para verificar se estão acessíveis.

8️⃣ Logs de backup

$ cat logs/backup.log

📌 Função: mostra o histórico detalhado da execução do backup.

9️⃣ Logs de restauração

$ cat logs/restore.log

📌 Função: mostra o histórico detalhado da execução da restauração.

🔟 Testando falha de integridade

$ echo "123456" > backups/backup_20260225_102723.hash
$ python3 src/restore.py
[ERROR] Hash SHA256 não confere! Arquivo corrompido ou modificado.

📌 Função: simula uma alteração no hash para testar a validação de integridade.

1️⃣1️⃣ Estrutura da pasta dados_importantes/

$ ls dados_importantes/

📌 Função: mostra os arquivos originais que foram incluídos no backup.

1️⃣2️⃣ Estrutura da pasta backups/

$ ls backups/

📌 Função: mostra os arquivos de backup gerados e armazenados.
