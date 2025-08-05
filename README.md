# CodeMinder

**Daily Algorithm Challenge with C# & Python**

CodeMinder is an automated system that generates a daily algorithm question (sourced from LeetCode) and stores a complete solution set in both **C#** and **Python**, along with an English explanation. This project is designed to strengthen problem-solving skills and demonstrate cross-language proficiency for technical interviews.

---

## ✨ Why CodeMinder?

Modern software engineers are expected to:

- Write clean, efficient code.
- Solve algorithmic problems under pressure.
- Work in multiple languages.

CodeMinder addresses all three by creating a structured, self-improving routine that:

- Automates coding practice.
- Encourages bilingual (C#/Python) proficiency.
- Generates explainable, readable content suitable for public GitHub portfolios.

---

## 🚀 Key Features

- ✍️ **Daily auto-generated LeetCode question**
- ⚖️ **Dual-language solutions**: C# and Python
- 🔗 **Clickable shortcut to the original question**
- � **Markdown file with clean code blocks and English explanation**
- 💾 **GitHub integration** using `n8n` for automated commits

---

## 🔍 Project Structure

```
CodeMinder/
├── Solutions/
│   ├── YYYY-MM-DD/
│   │   ├── [Problem Title].md       # Includes both solutions & explanation
│   │   └── [Problem Title].url      # Opens LeetCode problem directly
└── .n8n/                  # Automation logic and GitHub integration
```

---

## 🤝 Technologies Used

- **Languages**: C# (.NET), Python 3
- **Platform**: LeetCode
- **Automation Tool**: `n8n` (self-hosted)
- **Deployment**: GitHub (public repo)

---

## ✅ Sample Output

Each question generates:

1. `Markdown` file:
   - Title
   - Python solution
   - C# solution
   - English explanation
2. `.url` file:
   - Clickable link to LeetCode

---


## 💼 Author

**Yosef Hakim**\
B.Sc in Computer Science | Backend Developer (C#, Python, SQL)

---

## ✨ Contributions

This project is currently personal, but you're welcome to fork it and build your own automated practice routine!

---

## ☑ License

MIT License

