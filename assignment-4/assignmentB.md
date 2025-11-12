### Assignment B – Hashed Time-Lock Contract (HTLC)

This script allows Alice and Bob to trade Bitcoin safely.

---

### 1 HTLC Script

```
OP_IF
    OP_HASH160 <H(secret)> OP_EQUALVERIFY
    <Alice_pubKey> OP_CHECKSIG
OP_ELSE
    <21*60> OP_CHECKLOCKTIMEVERIFY OP_DROP
    <Bob_pubKey> OP_CHECKSIG
OP_ENDIF
```

 If Alice reveals the secret (preimage), she gets the Bitcoin.  
If she doesn’t within 21 minutes, Bob can get his refund.

---

### 2️ Claiming Transaction (Alice)

```
<sig_Alice> <preimage> TRUE
```

---

### 3️ Refund Transaction (Bob)

```
<sig_Bob> FALSE
```

---

### 4️ Example Values

| Item | Example |
|------|----------|
| Secret | "abc123" |
| Hash | hash160("abc123") |
| Timeout | 21 minutes (1260 seconds) |

---

### 5️ How it works

- Alice can claim the Bitcoin by showing the secret before timeout.  
- If time runs out, Bob gets a refund automatically.  
