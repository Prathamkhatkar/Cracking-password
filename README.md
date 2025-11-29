# Cracking Password

This project demonstrates how to identify and crack password hashes on **Kali Linux** using two tools:
- **HashPals – Search-That-Hash**
- **Hashcat**

The goal of the project is to understand how hash identifiers work and how to perform dictionary-based password cracking.

---

## 🖥 Operating System
- **Kali Linux**

---

## 🔧 Tools Used
- **Search-That-Hash (HashPals)** – for identifying & cracking some hashes  
- **Hashcat** – for professional password cracking  
- **rockyou.txt** wordlist  

---

## 📝 Steps Performed

### **1️⃣ Downloaded hash values**
- Downloaded **5 hash values** from GitHub.
- Created **5 text files**, containing **five hash values** one in each.

Example:
hash1.txt
hash2.txt
hash3.txt
hash4.txt
hash5.txt

---

### **2️⃣ Installed Search-That-Hash**
Installed the tool from GitHub using:

```bash
sudo pip3 install search-that-hash

3️⃣ Identified and cracked hashes using STH

Used Search-That-Hash to detect hash types and crack simple hashes:

sth -f hash1.txt
The tool identified the hash type and displayed the cracked passwords.

4️⃣ Started cracking with Hashcat

Before using Hashcat, checked available options:

hashcat --help

5️⃣ Cracked the hash using Hashcat

Example command used:

hashcat -a 0 -m 17400 hash1.txt /usr/share/wordlists/rockyou.txt -o crackedhash1.txt


-a 0 → dictionary attack

-m 0 → specific hash mode

Output saved to: crackedhash1.txt

6️⃣ Verified results

Checked the output file containing cracked passwords:

cat crackedhash1.txt

hashcat -a 0 -m 0 hash1.txt /usr/share/wordlists/rockyou.txt -o crackedhash1.txt
