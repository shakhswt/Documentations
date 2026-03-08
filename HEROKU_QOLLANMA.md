# 🚀 Heroku'ga Loyihani Yuklash — To'liq Qo'llanma

---

## 📋 Talablar (Prerequisites)

- [Heroku akkaunt](https://signup.heroku.com/) — bepul ro'yxatdan o'tish
- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) o'rnatilgan bo'lishi kerak
- [Git](https://git-scm.com/) o'rnatilgan bo'lishi kerak
- Loyiha papkasida `git init` qilingan bo'lishi kerak

---

## 1️⃣ Heroku CLI O'rnatish

### Windows:
```bash
# Rasmiy saytdan yuklab o'rnating:
# https://devcenter.heroku.com/articles/heroku-cli
```

### Ubuntu/Debian:
```bash
curl https://cli-assets.heroku.com/install.sh | sh
```

### Tekshirish:
```bash
heroku --version
```

---

## 2️⃣ Heroku'ga Login Bo'lish

```bash
heroku login
```
> Brauzer ochiladi — email va parol bilan kiring.

---

## 3️⃣ Loyihani Tayyorlash

### Node.js uchun — `package.json` ichida `start` script bo'lishi shart:
```json
{
  "scripts": {
    "start": "node index.js"
  },
  "engines": {
    "node": "18.x"
  }
}
```

### Python (Flask/Django) uchun — `Procfile` yarating:
```
web: gunicorn app:app
```

### `Procfile` (barcha loyihalar uchun):
```
web: node index.js
```
> `Procfile` — kengaytmasiz fayl, loyiha ildiz papkasida bo'lishi kerak.

---

## 4️⃣ `.gitignore` Fayli

```gitignore
node_modules/
.env
__pycache__/
*.pyc
venv/
.DS_Store
```

---

## 5️⃣ Git Tayyorlash

```bash
# Loyiha papkasiga o'ting
cd loyiha-nomi

# Git boshlash (agar qilinmagan bo'lsa)
git init

# Barcha fayllarni qo'shish
git add .

# Birinchi commit
git commit -m "Birinchi commit"
```

---

## 6️⃣ Heroku App Yaratish

```bash
# Yangi app yaratish (nom avtomatik beriladi)
heroku create

# YOKI o'z nomingizni bering
heroku create mening-loyiham-nomi
```

---

## 7️⃣ Loyihani Heroku'ga Push Qilish

```bash
git push heroku main
```

> Agar `master` branch ishlatayotgan bo'lsangiz:
```bash
git push heroku master
```

---

## 8️⃣ Muhit O'zgaruvchilarini (ENV) Sozlash

```bash
# .env faylini Heroku'ga qo'shish
heroku config:set SECRET_KEY=mening_maxfiy_kalitim
heroku config:set DATABASE_URL=postgres://...
heroku config:set NODE_ENV=production

# Barcha o'zgaruvchilarni ko'rish
heroku config
```

---

## 9️⃣ Ma'lumotlar Bazasi Qo'shish (PostgreSQL)

```bash
# Bepul Postgres addon qo'shish
heroku addons:create heroku-postgresql:essential-0

# DB URL ni ko'rish
heroku config:get DATABASE_URL
```

---

## 🔟 Loyihani Ochish

```bash
# Brauzerda ochish
heroku open

# Loglarni ko'rish
heroku logs --tail
```

---

## 🔄 Yangilanishlarni Yuklash

```bash
git add .
git commit -m "Yangilanish tavsifi"
git push heroku main
```

---

## ⚙️ Foydali Buyruqlar

| Buyruq | Tavsif |
|--------|--------|
| `heroku logs --tail` | Real vaqtda loglar |
| `heroku ps` | Ishlaydigan processlar |
| `heroku restart` | Serverni qayta ishga tushirish |
| `heroku run bash` | Terminal ochish |
| `heroku config` | ENV o'zgaruvchilar |
| `heroku apps` | Barcha applar ro'yxati |
| `heroku destroy app-nomi` | Appni o'chirish |

---

## ❗ Keng Tarqalgan Xatolar

### `No web process running`
```bash
# Procfile to'g'ri yozilganini tekshiring
cat Procfile
```

### `Application Error` (H10)
```bash
# Loglarni tekshiring
heroku logs --tail
```

### Port xatosi
> Heroku port ni o'zi belgilaydi. Kodda shunday yozing:
```javascript
// Node.js
const PORT = process.env.PORT || 3000;
app.listen(PORT);
```
```python
# Python
port = int(os.environ.get("PORT", 5000))
app.run(host="0.0.0.0", port=port)
```

---

## 📁 Loyiha Tuzilishi Namunasi

```
loyiha/
├── index.js          # Asosiy fayl
├── package.json      # Node uchun
├── Procfile          # Heroku jarayoni
├── .gitignore        # Git ignore
└── .env              # Lokal muhit (push qilinmaydi!)
```

---

## ✅ Tekshiruv Ro'yxati (Checklist)

- [ ] Heroku CLI o'rnatildi
- [ ] `heroku login` qilindi
- [ ] `Procfile` yaratildi
- [ ] `.gitignore` sozlandi
- [ ] `git init` va `git commit` qilindi
- [ ] `heroku create` qilindi
- [ ] `git push heroku main` qilindi
- [ ] ENV o'zgaruvchilari sozlandi
- [ ] `heroku open` bilan tekshirildi

---

> 💡 **Maslahat:** Loyihangiz turi (Node.js, Python, Django, React va h.k.) bo'yicha qo'shimcha sozlamalar kerak bo'lishi mumkin. `heroku logs --tail` — eng yaxshi debug vositasi!
