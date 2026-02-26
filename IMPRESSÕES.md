# 🔐 Projeto de Backup e Restauração com Verificação de Integridade e Criptografia

Este projeto demonstra a criação de um sistema de backup utilizando Python no Kali Linux, incluindo:

- Compactação de arquivos
- Geração de hash SHA256 para integridade
- Registro de logs
- Implementação de criptografia com Fernet
- Teste de falha de integridade

---

# 🎯 Objetivo do Projeto

O objetivo é desenvolver um sistema simples, porém completo, que:

- Automatize a criação de backups
- Garanta integridade por meio de hash SHA256
- Permita restauração segura
- Implemente criptografia simétrica
- Detecte alterações maliciosas nos arquivos

---

# 🗂 Estrutura Final do Projeto

backup_lab/  
├── backup.py  
├── restore.py  
├── dados_importantes/  
├── dados_restaurados/  
├── backups/  
├── logs/  
└── venv/  

---

# 🔗 Prints do Projeto – Ordem Real de Execução

---

## 1️⃣ Desktop do Kali Linux

Mostra a interface gráfica do sistema operacional Kali Linux.  
É o ambiente onde todos os comandos e scripts serão executados.  
Não há comandos neste print. Serve como introdução ao ambiente.

---

## 2️⃣ Criação da Estrutura Inicial do Projeto

Comandos executados:

$ mkdir ~/backup_lab  
$ cd ~/backup_lab  
$ mkdir src backups logs  

Descrição:

Cria a pasta principal backup_lab no diretório home.  
Acessa o diretório criado.  
Cria três subpastas principais:
- src → para scripts
- backups → para armazenar arquivos gerados
- logs → para armazenar registros de execução

---

## 3️⃣ Criação do Diretório e Arquivos Importantes

Comandos executados:

$ mkdir dados_importantes  
$ echo "Relatorio Confidencial" > dados_importantes/relatorio.txt  
$ echo "Senha super secreta" > dados_importantes/senha.txt  
$ ls -la dados_importantes  

Descrição:

Cria o diretório dados_importantes.  
Cria dois arquivos simulando dados sensíveis.  
Lista os arquivos para confirmar a criação.

---

## 4️⃣ Execução do Script de Backup

Comando executado:

$ python3 backup.py  

Descrição:

Executa o script backup.py.  
Gera um arquivo compactado .zip dentro da pasta backups.  
Calcula e exibe o hash SHA256 para verificação de integridade.

---

## 5️⃣ Verificação da Integridade

Comando executado:

$ sha256sum backups/backup_20260225_094050.zip  

Descrição:

Calcula manualmente o hash SHA256 do arquivo gerado.  
Permite comparar com o hash exibido pelo script para validar integridade.

---

## 6️⃣ Teste de Extração do Backup

Comandos executados:

$ unzip backups/*.zip -d .  
$ ls  

Descrição:

Descompacta o arquivo .zip no diretório atual.  
Lista os arquivos extraídos.  
Valida que o backup pode ser restaurado manualmente.

---

## 7️⃣ Novo Backup e Verificação de Log

Comandos executados:

$ rm -rf backups/  
$ python3 backup.py  
$ cat logs/backup.log  

Descrição:

Remove backups anteriores.  
Executa novamente o script.  
Exibe o arquivo de log contendo detalhes técnicos da execução.

---

## 8️⃣ Criação de Ambiente Virtual e Instalação de Biblioteca

Comandos executados:

$ python3 -m venv venv  
$ source venv/bin/activate  
$ pip install cryptography  

Descrição:

Cria ambiente virtual Python.  
Ativa o ambiente.  
Instala a biblioteca cryptography para implementação de criptografia simétrica.

---

## 9️⃣ Geração de Chave de Criptografia

Comandos executados no interpretador Python:

>>> from cryptography.fernet import Fernet  
>>> key = Fernet.generate_key()  
>>> print(key)  

Descrição:

Importa a classe Fernet.  
Gera chave criptográfica simétrica.  
Exibe a chave que será utilizada para criptografar os backups.

---

## 🔟 Backup Criptografado

Comandos executados:

$ python3 backup.py  
$ ls backups  

Descrição:

Executa o script já com suporte à criptografia.  
Gera arquivo com extensão .zip.enc.  
Lista o arquivo criptografado dentro da pasta backups.

---

## 1️⃣1️⃣ Restauração do Backup Criptografado

Comandos executados:

$ python3 restore.py  
$ ls dados_restaurados  

Descrição:

Executa o script restore.py.  
Descriptografa o arquivo .zip.enc.  
Restaura os arquivos para dados_restaurados.  
Lista os arquivos restaurados para validação.

---

## 1️⃣2️⃣ Teste de Integridade com Falha

Comandos executados:

$ echo "123456" > backups/*.hash  
$ python3 restore.py  

Descrição:

Substitui o hash original por valor inválido.  
Ao tentar restaurar, o script detecta inconsistência.  
Exibe erro semelhante a:

"Integridade comprometida! Hash inválido."

Isso comprova que o mecanismo de verificação de integridade está funcionando corretamente.

---

# ✅ Conclusão

O projeto demonstra:

- Implementação de backup automatizado
- Verificação de integridade com SHA256
- Registro de logs
- Criptografia simétrica com Fernet
- Detecção de adulteração de arquivos

Trata-se de uma aplicação prática dos conceitos de Segurança da Informação aplicados em ambiente Linux.
