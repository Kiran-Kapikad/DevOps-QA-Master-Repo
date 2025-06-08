
# GitFlow Branching Strategy (Animated with ASCII Diagrams)

GitFlow is a robust branching model ideal for CI/CD pipelines and QA workflows. Here's a visually guided explanation using diagrams.

---

## 🌿 Branch Roles

```
          +------------------------+               
          |     Production Code    |               
          |        `main`          |               
          +------------------------+               
                    ▲  ▲                            
          Merges from |  | Merges from                
                 +---------+                         
                 | release |                         
                 +---------+                         
                     ▲                                
             +--------------+                        
             |   develop    | ← ongoing dev work      
             +--------------+                        
             ▲    ▲      ▲                            
  Features → |    |      | ← Hotfixes                 
         +------+------+
         |feature/*   |
         +------------+
```

---

## 🛠️ Feature Branch Workflow

```bash
# Start from develop
git checkout develop

# Create a feature
git checkout -b feature/login-ui

# Work on code...

# Merge back when done
git checkout develop
git merge feature/login-ui
```

Diagram:

```
develop
   ▲
   |
feature/login-ui
   |
   └──> merge back
```

---

## 🚀 Release Branch Workflow

```bash
git checkout develop
git checkout -b release/1.0.0

# Final QA, bugfixes...

git checkout main
git merge release/1.0.0

git checkout develop
git merge release/1.0.0
```

Diagram:

```
     develop
        ▲
        |
   release/1.0.0
        |
  +-----+------+
  |            |
main        develop
```

---

## 🔥 Hotfix Branch Workflow

```bash
git checkout main
git checkout -b hotfix/fix-crash

# Fix, test...

git checkout main
git merge hotfix/fix-crash

git checkout develop
git merge hotfix/fix-crash
```

Diagram:

```
   main
    ▲
    |
hotfix/fix-crash
    |
+---+---+
|       |
main  develop
```

---

## 📋 Summary Table

| Branch Type     | Base Branch | Purpose               | Merge Targets         |
|------------------|-------------|------------------------|------------------------|
| `main`          | `release`   | Production-ready code  | -                      |
| `develop`       | `feature`   | Latest development     | `release`              |
| `feature/*`     | `develop`   | New features           | `develop`              |
| `release/*`     | `develop`   | Pre-release hardening  | `main`, `develop`      |
| `hotfix/*`      | `main`      | Emergency fixes        | `main`, `develop`      |

---

