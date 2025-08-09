
---

# 🛠️ Forge CLI — Branch-based VPS Sandbox Manager

## 📌 Loyihaning G‘oyasi

**Forge CLI** — bu VPS (virtual private server) ichida o‘rnatiladigan, `git`ga o‘xshash **branch asosida izolyatsiyalangan sandboxlar boshqaruv tizimi**. Dasturchilar bir xil serverda mustaqil ishlashlari uchun mo‘ljallangan. Har bir branch — alohida muhit.

### 🎯 Muammo

* Bir nechta dasturchi bitta VPSda ishlayotganda chalkashlik, fayllar ustiga yozilishi, `.env` buzilishi va konfliktlar tez-tez yuz beradi.
* Har bir deploy yoki test uchun alohida sozlashlar kerak bo‘ladi: nginx, port, pm2, start skriptlar va hokazo.
* VPSni boshqarish uchun har safar SSH bilan kirish kerak bo‘ladi.

---

## ✅ Yechim — Forge CLI

### 🔑 Asosiy imkoniyatlar:

| Buyruq                       | Tavsif                                        |
| ---------------------------- | --------------------------------------------- |
| `forge branch <nomi>`        | Yangi branch yaratadi (sandbox)               |
| `forge commit "<xabar>"`     | Branchga snapshot (version point) qo‘shadi    |
| `forge status`               | Hozirgi branch holatini ko‘rsatadi            |
| `forge delete branch <nomi>` | Branchni butunlay o‘chiradi                   |
| `forge log`                  | Commitlar tarixini ko‘rsatadi                 |
| `forge checkout <nomi>`      | Aktive branchni almashtiradi                  |
| `forge current`              | Hozir qaysi branchda turganingizni ko‘rsatadi |

---

## 🏗️ Arxitektura

* **Til**: Go (Statik, portable, tez)
* **CLI interface**: `cobra` yoki `urfave/cli`
* **Configlar**: `.forge.json` yoki `.forge.yml`
* **Branchlar**: `/var/forge/branches/<branch-name>/`
* **Commitlar**: Fayl snapshotlar (zips, metadata)
* **Current branch**: `.current` fayl bilan belgilanadi

---

## 🔄 Ishlash Mantig‘i

1. VPS ichida `forge` o‘rnatiladi.
2. Dasturchi SSH bilan kiradi yoki kelajakda localdan ulanadi.
3. Har kim `forge branch` orqali o‘z sandboxini ochadi.
4. `commit`, `status`, `log` orqali ishlanma yuritiladi.
5. VPS darajasidagi sozlashlar avtomatlashtiriladi (keyingi bosqichda).

---

## 🌍 Kelajakdagi Yo‘nalishlar

### 🧬 Remote Boshqaruv (Forge Remote)

* Localdan turib `forge` vositasi orqali VPSga ulanib boshqarish:

  ```bash
  forge remote branch feature-x --host 192.168.1.2
  ```

### 📦 Paket (Stack) tizimi

* Laravel, Node.js, Go, Python, PHP va boshqalar uchun tayyor `package templates`:

  ```bash
  forge init --stack laravel
  ```
* VPS avtomatik:

  * kerakli fayllarni joylashtiradi
  * port/hostlarni sozlaydi
  * run/start/stop ssenariylarini tayyorlaydi

---

## 👤 Maqsadli auditoriya

* Laravel, Node.js, Go, Python, Express, Next.js developerlar
* VPSda ishlab, branch-style sandboxni istaydiganlar
* Oddiy, xavfsiz, izolyatsiyalangan dev/test muhiti kerak bo‘lgan jamoalar

---

## 🧪 Misol

```bash
forge branch api-v2
forge checkout api-v2
forge commit "Initial API endpoints"
forge status
forge log
forge delete branch api-v2
```

---

## 📁 Fayl Struktura

```
/var/forge/
├── .current
├── branches/
│   ├── main/
│   ├── feature-x/
│   │   ├── commits/
│   │   ├── .meta/
├── forge.json
```

---

## 🌟 Nima uchun bu muhim?

> VPS’dagi tartibsizlikni tartibga soladi.
> Git kabi tanish terminal tajribasi beradi.
> Sandboxlar bilan xavfsiz va muammosiz ishlash imkonini yaratadi.

---

