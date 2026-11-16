# cyber_security
# Custom Wordlist Generator with Mangling Rules

A CUPP-like (Common User Passwords Profiler) custom wordlist generator and dictionary-attack demonstration tool built for the Cyber Security Lab (RTU 7CS4-22)[cite: 4, 7]. 

---

## 📌 Project Overview

Most real-world password guessing does not rely on blind brute force; instead, it narrows the search space using personal facts about the target (name, nickname, pet, date of birth) combined with predictable mangling rules such as leetspeak substitution, case changes, and year suffixes[cite: 4]. 

This project consists of three independent command-line Python scripts that:
1. **Generate a targeted wordlist** from a personal profile using realistic password-mangling rules[cite: 4, 10].
2. **Create sample password hashes** (MD5, SHA-1, and SHA-256) as a known ground truth[cite: 4, 10].
3. **Execute a dictionary attack** by hashing every candidate word and checking it against target hashes, measuring cracking speed and effectiveness[cite: 4, 10].

---

## 🛠️ Project Files

| File Name | Description |
| :--- | :--- |
| `wordlist_generator.py` | Profile-driven wordlist generator implementing leetspeak, case variants, word combinations, date tokens, prefix/suffix rules, and a birth-year sweep[cite: 11]. |
| `make_sample_hashes.py` | Hashes a chosen set of sample passwords across MD5, SHA-1, and SHA-256 into `sample_hashes.txt`[cite: 11]. |
| `crack_demo.py` | Performs a dictionary attack by hashing every wordlist entry and checking it against target hashes with early stopping[cite: 11, 14]. |
| `profile.json` | Example JSON profile configuration file used with `--config`[cite: 11]. |
| `wordlist.txt` | Generated output wordlist (created when the generator runs)[cite: 5, 11]. |
| `sample_hashes.txt` | Target hashes file in `algorithm:hexdigest` format (created by `make_sample_hashes.py`)[cite: 10, 11]. |
| `README.md` | Usage instructions and project documentation[cite: 11]. |

---

## ⚙️ Prerequisites & Environment

* **Python Version:** Python 3.8 or higher[cite: 10]
* **Dependencies:** Standard library only (`hashlib`, `argparse`, `itertools`, `json`, `pathlib`, `time`). **No external packages required[cite: 6, 10].**
* **Operating System:** Compatible with Windows 10/11, Linux, and macOS[cite: 10].

---

## 🚀 Usage Instructions

### Step 1: Generate the Wordlist
Run the wordlist generator using the built-in demo profile (Riya, Tommy, DOB: 14-08-2003)[cite: 4, 16]:
```bash
python3 wordlist_generator.py
