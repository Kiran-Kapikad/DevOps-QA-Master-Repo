
# 🧩 Git Hooks Explained (Beginner Friendly)

## 🔧 What Are Git Hooks?

Git **hooks** are like mini programs that run **automatically** at specific points in your Git workflow.

They help you **automate checks or tasks** during actions like committing, pushing, merging, etc.

Hooks live inside your project's `.git/hooks/` folder and include examples like:

- `pre-commit`
- `pre-push`
- `post-merge`
- `commit-msg`

You can **customize** these to do things like run tests, format code, or block commits with bugs.

---

## 🔍 What is `pre-commit`?

The `pre-commit` hook runs **right before a commit is finalized**.

It’s mainly used to **check your code** and make sure you're not committing:

- Debug statements (like `console.log` or `print()`)
- TODO comments
- Bad formatting
- Insecure or broken code

### ✅ Example Use Cases:

- Check for forbidden code (e.g., print statements)
- Run automated tests or linters
- Prevent secrets or passwords from being committed
- Enforce code standards across the team

---

## 📦 Where to Place the Script?

Create or paste your script into:

```bash
.git/hooks/pre-commit
```

Then give it permission to run:

```bash
chmod +x .git/hooks/pre-commit
```

Now, every time you do:

```bash
git commit -m "some message"
```

The hook runs first. If it finds problems, it stops the commit!

---

## 🧪 Why Pre-Commit Hooks Matter in DevOps & QA

| Benefit                             | How It Helps                              |
|-------------------------------------|--------------------------------------------|
| 🛡 Prevent bugs early                | Stops bad code before reaching the repo    |
| 🚫 Block debug/test code             | Prevents test prints or TODOs in commits   |
| 🧼 Enforce clean code                | Ensures team follows consistent practices  |
| 🔁 Automate testing/linting          | Saves time & catches errors fast           |

---

## 🎯 Summary

- Git hooks = auto-running scripts for Git actions  
- `pre-commit` runs before every commit  
- You can block or fix issues early  
- Great for DevOps, QA, and CI/CD pipelines

