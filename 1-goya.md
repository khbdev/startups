
# ⚡ Flash CLI

Terminal ichida dasturchilarga tezlik va qulaylik beradigan oddiy, lekin kuchli CLI vosita.

## 🎯 Maqsad

Dasturchilar har kuni bajaradigan takroriy amallarni (git, repo, package setup) bitta buyruq bilan bajarish.

---

## 🔑 Asosiy 3 funksiya

### 1. `flash start "commit message"`

Git uchun 3 ta komanda o‘rniga bitta:

```bash
flash start "login page added"
````

👉 Nima qiladi:

* `git add .`
* `git commit -m "login page added"`
* `git push`



### 3. `flash box`

Doim ishlatadigan package yoki komandalarni **quti sifatida** saqlaydi:

#### Saqlash:

```bash
flash box record laravel
```

Sen yozgan komandalarni eslab qoladi:

```
composer require laravel/sanctum
composer require predis/predis
composer require laravel/octane
```

#### Qayta ishlatish:

```bash
flash box apply laravel
```

👉 Shu komandalar yangi loyihada avtomatik bajariladi.

---

## 📌 Xulosa

Flash CLI — bu oddiy, ammo samarali 3 funksiya orqali developer hayotini tezlashtiradigan vosita:

* `flash start` → Git push shortcut
* `flash repo` → GitHub repo ochish
* `flash box` → Laravel yoki boshqa framework’lar uchun setup template


///////////
