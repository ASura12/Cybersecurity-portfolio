# 🔐 picoCTF – Bytemancy (0) Write-Up

## 📌 Challenge Info
- **CTF:** :contentReference[oaicite:0]{index=0}  
- **Author:** :contentReference[oaicite:1]{index=1}  
- **Category:** General Skills / Scripting  
- **Difficulty:** Easy  

---

## 🧠 Concept Tested
- :contentReference[oaicite:2]{index=2} values  
- Reading source code  
- Automating repetitive input  
- Basic scripting with Python  

---

## ⚙️ Bytemancy 0

## 🔍 Analysis

After launching the instance:

```bash
nc candy-mountain.picoctf.net 52338

Or inspecting the source code:

cat app(1).py
📊 Observations
Program expects ASCII decimal value: 101
Input must be repeated 3 times
No spaces allowed
💡 Solution

ASCII 101 = 'e'

So the required input is:

eee
⚡ Input Generation

Instead of typing manually, use:

python -c "print('e' * 3, end='')"
