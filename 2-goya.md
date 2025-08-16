

# 📌 Igris CLI — Loyiha mazmuni

## 1️⃣ Loyiha nomi

**Igris CLI**
(*qorong‘ulikdan kuch oladigan va hamma narsani boshqaradigan qurol* 😎)

---

## 2️⃣ Loyihaning maqsadi

Dasturchilarga **VPS serverlarda loyihani tez va oson deploy qilish** imkoniyatini berish.
👉 Endi `ssh`, `apt install`, `docker run`, `systemctl` bilan qiynalish shart emas.

Foydalanuvchi faqat:

```bash
igris vps add  
igris deploy go
```

deydi, va loyiha VPS’da avtomatik ishlay boshlaydi.

---

## 3️⃣ Yechim (oddiy qilib tushuntirish)

* Odatda dasturchi VPS’da loyiha qo‘yish uchun ko‘p vaqt sarflaydi: **ssh qilish, kutubxonalar o‘rnatish, docker sozlash, nginx sozlash, ssl qo‘shish**.
* **Igris CLI** bu jarayonni avtomatlashtiradi:

  1. VPS ma’lumotini (IP, user, password) saqlab qo‘yadi.
  2. Github’dan loyihani avtomatik yuklab oladi.
  3. Dasturlash tilini aniqlaydi (Go, PHP, Node, Python).
  4. Dockerfile bo‘lsa → uni ishlatadi, bo‘lmasa tayyor Docker template beradi.
  5. Servisni ishga tushirib beradi (`systemd` yoki `docker-compose`).
  6. Natijada loyiha ishlashga tayyor bo‘ladi.

👉 Xuddi **git** qanchalik soddalashgan bo‘lsa, **igris** ham deployni shunchalik soddalashtiradi.

---

## 4️⃣ Funksiyalar

### 🔹 VPS boshqaruvi

* `igris vps add` → VPS qo‘shish (ssh + password saqlanadi).
* `igris vps list` → VPS ro‘yxatini ko‘rish.
* `igris vps select` → VPS tanlash.

### 🔹 Deploy funksiyasi

* `igris deploy go` → Go loyihani deploy qilish.
* Repo’dan `git clone` qiladi.
* Docker yoki systemd orqali avtomatik ishga tushiradi.
* `igris deploy php/node/python` → keyingi versiyalarda qo‘shiladi.

### 🔹 Qo‘shimcha buyruqlar

* `igris logs` → loyiha loglarini ko‘rsatish.
* `igris restart` → loyihani qayta ishga tushirish.
* `igris update` → yangi kodni yuklab qayta build qilish.
* `igris remove` → loyihani o‘chirish.

### 🔹 Kelajakda

* Domain + nginx sozlash.
* SSL sertifikat (Let’s Encrypt) qo‘shish.
* Monitoring (CPU, RAM, traffic).
* CI/CD integratsiyasi (Github Actions → Igris CLI → VPS).

---

## 🚀 Xulosa

**Igris CLI** — bu dasturchilar uchun **universal deploy CLI**.

* Hozircha **1.0.0 versiya faqat Go uchun** chiqadi (binary yoki docker).
* Keyin PHP, Node.js va Python qo‘shilib, hamma texnologiyalarni qo‘llab-quvvatlaydi.
* Maqsad: VPS’da loyiha qo‘yishni **1 daqiqada va 2 ta buyruqda** qilish.

---
