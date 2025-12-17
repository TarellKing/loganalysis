# loganalysis

# Dataset 6: EDR Detection Events

edr_detections = [
    {"host": "ws-finance-05", "detection_type": "malware", "severity": 9, "indicators": ["evil.dll", "bad.exe"], "mitigated": True},
    {"host": "ws-hr-12", "detection_type": "ransomware", "severity": 10, "indicators": ["ransom.note", "encrypt.ps1", "volume-shadow-delete"], "mitigated": False},
    {"host": "ws-finance-05", "detection_type": "credential_dump", "severity": 8, "indicators": [], "mitigated": True},
    {"host": "server-db-01", "detection_type": "lateral_movement", "severity": 7, "indicators": ["psexec.exe"], "mitigated": False},
    {"host": "ws-it-03", "detection_type": "malware", "severity": 6, "indicators": None, "mitigated": True},
    {"host": "ws-hr-12", "detection_type": "data_exfil", "severity": 9, "indicators": ["ftp.exe", "7z.exe"], "mitigated": False},
]



Perfect dataset. This is **very realistic EDR / detection-engineering material**.

I’ll give you:

1. **8 questions**, ordered from warm-up → medium → harder
2. A **single GPT helper prompt** you can paste in *only if you get stuck* (without giving away the solution)

---

# 🔐 Dataset 6 – EDR Detection Events

Use **plain Python**, no imports required.

---

## 🟢 Warm-Up (Foundations)

### **Q1.**

**Which unique hosts appear in the EDR detections?**

Focus:

* deduplication
* missing nothing fancy

---

### **Q2.**

**How many detections occurred per detection type?**

Example output shape:

```python
{
  "malware": 2,
  "ransomware": 1,
  ...
}
```

---

## 🟡 Medium (Interview-Level)

### **Q3.**

**Which hosts had at least one unmitigated detection?**

Focus:

* boolean filtering
* deduplication

---

### **Q4.**

**What is the average severity per detection type?**

Focus:

* grouping
* sum + count
* division at the end

(Hint: you’ll likely need *two* values per key.)

---

### **Q5.**

**Which detection types have severity ≥ 9 and were not mitigated?**

Focus:

* compound conditions
* filtering first, grouping optional

---

## 🔴 Medium-Hard (Staff-Level Thinking)

### **Q6.**

**For each host, list all unique indicators observed.
Ignore events where indicators are empty or None.**

Expected structure:

```python
{
  "ws-hr-12": {"ftp.exe", "7z.exe", "ransom.note", ...},
  ...
}
```

---

### **Q7.**

**Which hosts triggered more than one detection type?**

Focus:

* grouping by host
* deduplicating detection types per host
* filtering on size

---

### **Q8.**

**Which detection type had the highest average severity?**

Focus:

* aggregation
* “max by derived metric” (average)
* no sorting required

---

# 🧠 Helper GPT Prompt (use only if stuck)

Paste this **exactly** if you get stuck on a question:

> *“I’m solving a Python interview-style log analysis problem.
> Do NOT give me the full solution.
> Explain only:*
>
> 1. *What data structure I should use (list, set, dict, or nested)*
> 2. *What the intermediate data shape should look like*
> 3. *Whether filtering happens before or after aggregation*
>
> *Do not write code unless I explicitly ask.”*

This keeps you thinking like an engineer, not copying answers.

---

## How to use this set effectively (important)

* Do **2–3 questions per day max**
* Stop as soon as you feel mental fatigue
* Verbally explain your approach *before* typing
* If stuck >5 minutes → use the helper prompt

---

## Final reassurance

If you can solve:

* Q1–Q5 comfortably
* Q6–Q8 with some thinking time

You are **well within** staff detection engineer expectations.

You are not memorizing — you are **learning how to reason**.
That’s exactly what this interview is testing.

If you want, next I can:

* review your answers
* turn these into a **mock interview**
* or help you practice **explaining detections verbally**

Just tell me.
