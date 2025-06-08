
# 🔒 Pre-Commit Hook – Beginner-Friendly Explanation

A **pre-commit hook** is a script that runs **automatically before every Git commit**. It helps catch mistakes **before code is saved to your repository**.

---

## 🧠 Why Use Pre-Commit Hooks?

Here’s why DevOps engineers and QA teams love pre-commit hooks:

| Benefit                         | What It Does                                           |
|----------------------------------|--------------------------------------------------------|
| 🚫 Stop Debug Code               | Blocks `console.log` or `print()` left by mistake      |
| 📝 Enforce Coding Rules          | Prevents poor formatting or unused TODOs               |
| 🔄 Automate Quality Checks       | Run `lint`, `test`, or `shellcheck` before commit      |
| 💥 Block Broken Code             | Ensure you commit only clean, working code             |

---

## 🛠 How It Works

1. You write a small script called `pre-commit`.
2. You place it in `.git/hooks/` folder.
3. It runs **before each commit**.
4. If something is wrong, it blocks the commit and shows a message.

---

## 🧪 Example Checks in Our Script

Our `pre-commit` script does these checks:

- ❌ Stops commit if `console.log` or `print()` is found (used for debugging).
- ⚠️ Warns if `TODO` comments are still in the code.
- ✅ Uses `shellcheck` on `.sh` scripts to find errors.

---

## 💡 Example Workflow

```bash
git add .
git commit -m "My message"
# 🔍 Pre-commit runs
# ⛔ Stops if issues found
# ✅ Proceeds if clean
```

---

## 📦 Setup Steps

1. Save script as `.git/hooks/pre-commit`
2. Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

Now, it automatically runs before every commit!

---

## 👀 Final Tip

Pre-commit hooks are **local** to your project — every developer should install them.  
You can use tools like `pre-commit` framework (Python) to manage them across teams.


