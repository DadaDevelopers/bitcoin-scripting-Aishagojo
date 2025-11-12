
```
OP_DUP OP_HASH160 OP_EQUALVERIFY OP_CHECKSIG
```

This is the standard Bitcoin script used when someone sends Bitcoin to another person.  
It makes sure only the real owner of the private key can spend the Bitcoin.

### 1️ What each part does

| Code | Meaning | What it does |
|------|----------|--------------|
| **OP_DUP** | Duplicate | Copies your public key |
| **OP_HASH160** | Hash | Turns your public key into a short hash |
| **OP_EQUALVERIFY** | Compare | Checks if the hash matches the one on the blockchain |
| **OP_CHECKSIG** | Signature Check | Verifies your signature to confirm ownership |

---

### 2️ How it works step by step

1. You give your **public key** and **signature**.  
2. The script **duplicates** your public key (OP_DUP).  
3. It **hashes** your key (OP_HASH160).  
4. It **compares** that hash with the saved hash (OP_EQUALVERIFY).  
5. It **checks your signature** (OP_CHECKSIG).  
If all checks pass → You can spend the Bitcoin.  
If something is wrong → The transaction fails.

---

### 3 Why it’s secure

- Keeps your public key hidden until spending  
- Protects against tampering and copying  
- Ensures only the private key owner can spend funds  
