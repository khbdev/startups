
# AI Terminal Assistant (Project name to be decided)

AI yordamida ishlovchi terminal assistant. Foydalanuvchi tabiiy tilda (o‘z tilida) buyruq beradi, assistant esa uni bash komandasiga aylantirib, real tizimda bajaradi.

---

## 🧠 Nega bu loyiha kerak?

Dasturchilar, DevOpschilar, Linux/macOS foydalanuvchilari har kuni terminal orqali takroriy, murakkab yoki eslab qolish qiyin bo‘lgan komandalarga duch keladi. Bu jarayon:
- Vaqt oladi
- Xatoliklarga olib keladi
- Fokusni buzadi

Bu loyiha aynan shu muammoni yechadi:  
**"Yozma, ayt. Terminal o‘zi bajaradi."**

---

## 🎯 Loyiha nima qiladi?

- Tabiiy tilda yozilgan so‘zlardan bash komanda yaratadi
- OS (Linux yoki macOS) bilan bevosita ishlaydi
- Komandani bajaradi, natijani terminalga chiqaradi
- Kontekstni yodda saqlaydi (masalan: “rasmlar”, “eski fayllar” nimani anglatishini biladi)
- Foydalanuvchi bilan muloqotda bo‘ladi (suhbat asosida)

---

## 🧩 Misollar

```bash
$ ai
🤖: Salom, nima xizmat?
👤: Documentsda eski rasm bor edi, shuni zip qil.
🤖: zip ~/Documents/rasmlar/eski.zip ~/Documents/rasmlar/eski/*
````

```bash
👤: Tizimda ishlamayotgan ilovalarni tozalab tashla.
🤖: sudo apt autoremove
```

```bash
👤: VSCode'da Laravel loyihamni och.
🤖: code ~/Documents/my-laravel-project
```

---

## 👥 Kimlar uchun?

* Terminalda ishlaydigan har qanday foydalanuvchi
* Dasturchilar (Node, Laravel, Go, Python)
* DevOps va System Adminlar
* Linux/macOS foydalanuvchilari
* Bash yozishni o‘rganayotgan boshlovchilar

---

## ❗ Yechayotgan muammo:

| Muammo                           | Yechim                            |
| -------------------------------- | --------------------------------- |
| Bash komandalarni yodlash kerak  | Tabiiy til orqali boshqarish      |
| Har kuni bir xil terminal ishlar | AI yordamida avtomatlashtirish    |
| Terminaldan foydalanish qiyin    | Suhbat asosidagi yengil assistant |
| Fokus buziladi, vaqt ketadi      | 1 ta buyruq bilan ko‘p ish        |

---

