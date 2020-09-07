# Ransomware-PoC
A simple python ransomware PoC that can be used for Atomic Red Team testing for **ATT&CK Technique: Data Encrypted for Impact (T1486)**. The updated code demonstrates a typical ransomware flow. It uses AES encryption to encrypt the local files for speed reasons. The AES key is then encrypted with RSA asymmetric encryption using the RSA's public key. The RSA's private key and/or encrypted AES key is then sent to the C2. If the encrypted AES is not sent, then the victim will have to provide it. When the ransom is paid, the attacker will then provide the private key to decrypt the AES key and thus decrypt the encrypted files. More simply, a decryptor is sent to the victims which will perform those actions automatically. 

# How to run
Install dependencies:
```bash
pip3 install pycryptodome
```

Run:
```
Encrypt: python3 main.py
Decrypt: python3 main.py -d
```

Variables to change
* Path
* Ransomware Extension [default: .wasted for WastedLocker]

NB: As this is simply a PoC for Atomic Red Team, there is no real need to change the keys or other variables.

# Additional Features
* RSA asymmetric encryption of the AES key
* Autodetects Windows, Linux or MacOS
* Fixed handling of renaming files with a ransomware extension

# Credit
Credit goes to deadPix3l (https://github.com/deadPix3l/CryptSky) and contributers.
