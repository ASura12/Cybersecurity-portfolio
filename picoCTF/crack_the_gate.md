🎯 Objective
Connect to the remote service
Analyze the transformed string
Reverse all applied transformations
Recover the original flag
⚠️ Key Concept

The challenge is based on reversing a transformation pipeline:

Original → Encode → Reverse → Replace → Modify → ROT13 → Final Output

To solve it:

Final Output → Reverse Steps (in reverse order) → Original
🛠️ Step-by-Step Solution
🔹 Step 1: Base64 Decode
base64 -d

Reason: The string is Base64 encoded, so we decode it.

🔹 Step 2: Reverse the String
rev

Reason: The text was reversed during transformation.

🔹 Step 3: Replace Dash with Underscore
tr '-' '_'

Reason: _ was replaced with -, so we revert it.

🔹 Step 4: Replace Parentheses with Curly Braces
tr '()' '{}'

Reason: {} was changed to (), so we restore it.

🔹 Step 5: Apply ROT13 Decoding
tr 'A-Za-z' 'N-ZA-Mn-za-m'

Reason: ROT13 was applied, so applying it again decodes it.

⚙️ Final Command Pipeline
echo "encoded_string_here" | base64 -d | rev | tr '-' '_' | tr '()' '{}' | tr 'A-Za-z' 'N-ZA-Mn-za-m'
🏁 Flag
picoCTF{your_flag_here}
🧠 Key Learnings
Understanding Linux pipelines
Reversing transformations logically
Using tools like base64, rev, and tr
Thinking step-by-step instead of guessing
💡 Real-World Relevance

These techniques are useful in:

Data decoding
Log analysis
Security testing
Malware analysis
🚀 Conclusion

This challenge demonstrates that solving problems in cybersecurity is not about guessing, but about understanding how transformations work and reversing them correctly.

👉 Always reverse both:

The order of steps
The logic of each step
