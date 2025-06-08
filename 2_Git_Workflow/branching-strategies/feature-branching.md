
# 🌿 Feature Branching (Beginner Friendly Guide)

Feature branching is a simple and safe way to work on new features in Git without affecting the main codebase.

---

## ✅ What is a Feature Branch?

A **feature branch** is a separate copy of your main code where you can safely build or test a new feature (like login, dashboard, etc).

You work in your own space — and when everything works fine, you merge it back!

---

## 🛠 How to Use Feature Branches (Step-by-Step)

```bash
# Step 1: Start from the main or develop branch
git checkout develop

# Step 2: Create a new branch for your feature
git checkout -b feature/login-page

# Step 3: Do your work (add files, make changes)

# Step 4: Save and commit your changes
git add .
git commit -m "Added login page UI"

# Step 5: Merge your feature back into develop
git checkout develop
git merge feature/login-page

# Step 6: Delete the feature branch if no longer needed
git branch -d feature/login-page
```

---

## 💡 Example Names for Feature Branches

| Branch Name             | Purpose                     |
|--------------------------|-----------------------------|
| `feature/login-page`     | Login page design           |
| `feature/user-profile`   | Profile view/edit screen    |
| `feature/payment-api`    | Payment gateway connection  |

---

## 🔁 Visual Diagram

```
       develop
          ▲
          |
   feature/login-page
        |
        └── Do work → Commit → Merge back
```

---

## 🎯 Why Use Feature Branches?

- You won’t mess up main code
- Work without disturbing teammates
- Easier to test your work separately
- Great for CI/CD pipelines and QA reviews

---

## 🔒 Best Practices

- Keep branch names clear
- Don’t make branches too long (merge often)
- Always test before merging
- Use `git pull` or `git rebase` to stay updated

---

## 📌 Summary

| Task                  | Command                                  |
|------------------------|-------------------------------------------|
| Create feature branch | `git checkout -b feature/my-feature`      |
| Save work             | `git add . && git commit -m "msg"`        |
| Merge to develop      | `git checkout develop && git merge feature/...` |
| Delete branch         | `git branch -d feature/my-feature`        |

---

