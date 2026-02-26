# 🔐 Secure Backup System
### Professional Secure Backup Project with Integrity Verification and Encryption

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Linux](https://img.shields.io/badge/Platform-Kali%20Linux-black?logo=linux)
![Security](https://img.shields.io/badge/Domain-Information%20Security-red)
![Encryption](https://img.shields.io/badge/Encryption-Fernet-green)
![Hash](https://img.shields.io/badge/Integrity-SHA256-orange)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)

---

## 🛡 Project Overview

This project implements a secure and automated backup system developed in Python within a Kali Linux environment.

It demonstrates practical application of core Information Security principles:

- Data integrity verification
- Symmetric encryption
- Secure restoration workflow
- Structured logging
- Tamper detection mechanisms

The system simulates real-world defensive controls used in corporate environments.

---

## 🎯 Technical Objectives

- Automate backup generation  
- Ensure file integrity using SHA256 hashing  
- Implement symmetric encryption (Fernet)  
- Log system activity for traceability  
- Detect unauthorized modifications  
- Securely restore encrypted backups  

---

## 🧱 Project Structure

backup_lab/  
├── backup.py  
├── restore.py  
├── dados_importantes/  
├── dados_restaurados/  
├── backups/  
├── logs/  
└── venv/  

---

# 🖥 Full Execution Demonstration

---

## 1️⃣ Kali Linux Environment

Development and testing performed in a controlled Kali Linux lab environment.

<img width="1920" height="936" alt="Desktop Kali Linux" src="https://github.com/user-attachments/assets/a3c0611a-9825-48fb-ac2b-4dc01665a638" />

---

## 2️⃣ Initial Project Setup

```bash
mkdir ~/backup_lab
cd ~/backup_lab
mkdir backups logs
```

<img width="1920" height="936" alt="Criação da Estrutura" src="https://github.com/user-attachments/assets/a8a5acf5-deb5-43db-9c24-6a2420a972c1" />

---

## 3️⃣ Sensitive Data Simulation

```bash
mkdir dados_importantes
echo "Relatorio Confidencial" > dados_importantes/relatorio.txt
echo "Senha super secreta" > dados_importantes/senha.txt
```

<img width="1920" height="936" alt="Preparação do Ambiente" src="https://github.com/user-attachments/assets/d317ed8e-64e5-43e8-b7db-98ea0704b514" />

---

## 4️⃣ Initial Backup Execution

```bash
python3 backup.py
```

✔ Archive generation  
✔ Automatic SHA256 calculation  
✔ Log registration  

<img width="1920" height="936" alt="Execução do Backup" src="https://github.com/user-attachments/assets/8fc27a8f-f04c-4a0a-be22-2871c5906696" />

---

## 5️⃣ Manual Integrity Verification

```bash
sha256sum backups/backup_YYYYMMDD_HHMMSS.zip
```

<img width="1920" height="936" alt="Validação de Hash" src="https://github.com/user-attachments/assets/3fea2e6d-3031-4e3b-9c55-30217d9ed507" />

---

## 6️⃣ Manual Backup Extraction

```bash
unzip backups/*.zip -d .
ls
```

<img width="1920" height="936" alt="Extração Manual" src="https://github.com/user-attachments/assets/a64b3db2-ed50-46d2-b56f-0c08d551428a" />

---

## 7️⃣ Logging System Verification

```bash
rm -rf backups/
python3 backup.py
cat logs/backup.log
```

<img width="1920" height="936" alt="Sistema de Logs" src="https://github.com/user-attachments/assets/29698e32-53d7-4bfc-907e-79deda0502aa" />

---

## 8️⃣ Virtual Environment & Encryption Setup

```bash
python3 -m venv venv
source venv/bin/activate
pip install cryptography
```

<img width="1920" height="936" alt="Ambiente Virtual" src="https://github.com/user-attachments/assets/b4a9784b-e2b0-47b5-bb9e-67a3c17ef940" />

---

## 9️⃣ Encryption Key Generation

```python
from cryptography.fernet import Fernet
key = Fernet.generate_key()
print(key)
```

<img width="1920" height="936" alt="Geração de Chave" src="https://github.com/user-attachments/assets/de0e2930-311e-4629-a744-495055ea4ce6" />

---

## 🔟 Encrypted Backup (.zip.enc)

```bash
python3 backup.py
ls backups
```

<img width="1920" height="936" alt="Backup Criptografado" src="https://github.com/user-attachments/assets/164e0341-de88-4312-b4aa-b0e88ebc8135" />

---

## 1️⃣1️⃣ Secure Restoration Process

```bash
python3 restore.py
ls dados_restaurados
```

✔ Decryption  
✔ Integrity validation  
✔ Controlled restoration  

<img width="1920" height="936" alt="Restauração Segura" src="https://github.com/user-attachments/assets/e4196b00-0cb8-4408-9395-028f05c90ca8" />

---

## 1️⃣2️⃣ Integrity Violation Simulation

```bash
echo "123456" > backups/backup_YYYYMMDD_HHMMSS.hash
python3 restore.py
```

Expected output:

```
Integridade comprometida! Hash inválido.
```

<img width="1920" height="936" alt="Falha de Integridade Detectada" src="https://github.com/user-attachments/assets/8b0c24cd-9844-41ff-9cb7-1f06ffbdd644" />

---

# 🔐 Technologies Used

- Python 3  
- hashlib (SHA256)  
- zipfile  
- cryptography (Fernet)  
- Kali Linux  

---

# 🧠 Security Concepts Demonstrated

- Symmetric Encryption  
- Cryptographic Hashing  
- Integrity Validation  
- Secure Logging  
- Tamper Detection  
- Controlled Data Recovery  

---

# 🚀 Technical Highlights

✔ Real Linux security lab execution  
✔ Full encryption + integrity workflow  
✔ Simulated tampering scenario  
✔ Clean and scalable structure  
✔ Portfolio-ready security implementation  

---

# 📌 Project Status

🟢 Completed  
🔐 Functional  
🧪 Tested with simulated attack  
📁 Fully documented  

---

# 👨‍💻 Author

**Marcio Augusto Mazzochi**  
Information Security | Cybersecurity | Automation Projects
