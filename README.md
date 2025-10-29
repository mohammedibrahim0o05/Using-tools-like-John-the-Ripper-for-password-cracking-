# Using-tools-like-John-the-Ripper-for-password-cracking

### Name Mohammed ibrahim  MN 
### Reg No 212223100034

## AIM:
To crack password hashes using John the Ripper in Kali Linux.
## REQUIREMENTS:
- **Operating System:** Kali Linux / Ubuntu / Windows (with JtR binaries)
- **Tools:**
    - John the Ripper (Community/Pro version)
    - Hash generating tools (e.g., openssl, unshadow)
- **Test Data:**
    - /etc/shadow file (Linux hashed passwords)
    - Custom password-protected file (ZIP, RAR, etc.)
## ARCHITECTURE DIAGRAM:
```mermaid
flowchart TD
    A[Password Protected File / Hash] --> B[John the Ripper]
    B --> C[Select Attack Mode: Dictionary or Brute Force]
    C --> D[Load Wordlist / Charset Rules]
    D --> E[Password Cracking Process]
    E --> F[Recovered Passwords]
```
## DESIGN STEPS:
### Step 1: Install John the Ripper
```bash
sudo apt update
sudo apt install john -y
```

### Step 2: Prepare Hash File
- Extract hashes (Linux example):
```
unshadow /etc/passwd /etc/shadow > myhashes.txt
```
- For a ZIP file:
```
zip2john secret.zip > ziphash.txt
```
### Step 3: Run John the Ripper
- Dictionary Attack:
```
john --wordlist=/usr/share/wordlists/rockyou.txt myhashes.txt
```
- Brute Force (Incremental Mode):
```
john --incremental myhashes.txt
```
### Step 4: Show Cracked Passwords
```
john --show myhashes.txt
```
## PROGRAM:
1. **Hash Extraction** – Obtain password hashes from system files or encrypted archives.
2. **Attack Mode Selection** – Choose between dictionary, brute force, or hybrid.
3. **Cracking Phase** – John the Ripper runs through candidate passwords.
4. **Password Recovery** – Successfully cracked passwords are displayed.

## OUTPUT:
<img width="1920" height="1080" alt="KALI 2  Running  - Oracle VirtualBox 08-10-2025 08_28_27" src="https://github.com/user-attachments/assets/efad7ae2-596a-4076-a662-447a80f93a8b" />
<img width="1920" height="1080" alt="KALI 2  Running  - Oracle VirtualBox 08-10-2025 08_28_21" src="https://github.com/user-attachments/assets/a638d74b-b835-4349-b907-56ef3f3ecdb2" />
<img width="1410" height="288" alt="Screenshot 2025-10-08 084703" src="https://github.com/user-attachments/assets/135ae702-0839-4cf5-a991-49f63eba4a84" />


## RESULT:
The password hashes were successfully cracked using John the Ripper.


