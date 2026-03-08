# 🚀 GitHub'ga Loyiha Joylash — To'liq Qo'llanma (0 dan)

> Har safar yangi loyihani GitHub'ga push qilishda ushbu qo'llanmadan foydalaning.

---

## 📋 Bir martalik sozlash (birinchi marta)

### 1. Git o'rnatish
- Windows: https://git-scm.com/download/win — yuklab o'rnating

### 2. Git'ni sozlash
```bash
git config --global user.name "Ismingiz"
git config --global user.email "github@email.com"
```

### 3. SSH kalit yaratish (tavsiya — parolsiz ishlaydi)
```bash
ssh-keygen -t ed25519 -C "github@email.com"
```
Keyin chiqgan kalitni ko'rish:
```bash
cat ~/.ssh/id_ed25519.pub
```
GitHub → **Settings** → **SSH and GPG keys** → **New SSH key** → kalitni joylashtiring.

---

## 📁 Har yangi loyiha uchun qadamlar

### 1-qadam — GitHub'da bo'sh repo yaratish
1. github.com ga kiring
2. **"New repository"** bosing
3. Nom bering (masalan: `anor-market-sayt`)
4. **"Create repository"** bosing (README, .gitignore qo'shmang — keyinroq qo'shiladi)

---

### 2-qadam — Terminal orqali loyihani boshlash

```bash
# Loyiha papkasiga kirish
cd C:/Users/sheyx/OneDrive/Documents/PYTHON/loyiha-nomi

# Git boshlash
git init

# Barcha fayllarni qo'shish
git add .

# Birinchi commit
git commit -m "Initial commit"
```

---

### 3-qadam — GitHub bilan bog'lash va push qilish

**HTTPS orqali:**
```bash
git remote add origin https://github.com/username/repo-nomi.git
git branch -M main
git push -u origin main
```

**SSH orqali (tavsiya):**
```bash
git remote add origin git@github.com:username/repo-nomi.git
git branch -M main
git push -u origin main
```

---

## 🔄 Keyingi o'zgarishlarni push qilish

```bash
git add .
git commit -m "O'zgarish tavsifi"
git push
```

---

## ⚠️ Tez-tez uchraydigan xatolar va yechimlari

| Xato | Yechim |
|------|--------|
| `remote origin already exists` | `git remote set-url origin <yangi-url>` |
| `failed to push — non-fast-forward` | `git pull origin main --rebase` keyin `git push` |
| Parol so'ralsa (HTTPS) | Token yarating: GitHub → Settings → Developer settings → Personal access tokens |
| `src refspec main does not match` | `git branch -M main` ni qayta ishga tushiring |

---

## 🪄 Foydali buyruqlar

```bash
git status                    # Holatni ko'rish
git log --oneline             # Commit tarixini ko'rish
git remote -v                 # Remote URL ni ko'rish
git branch                    # Branch larni ko'rish
git pull                      # Yangilanmalarni tortish
git clone <url>               # Reponi yuklab olish
```

---

## 📦 .gitignore (Python loyihalari uchun)

`.gitignore` nomli fayl yarating va quyidagilarni yozing:

```
__pycache__/
*.pyc
*.pyo
.env
venv/
.vscode/
*.sqlite3
*.db
node_modules/
```

---

*Tayyorlandi: shakhswt uchun | GitHub: github.com/shakhswt*
