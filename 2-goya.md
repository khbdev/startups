---

# 🧾 TEXNIK TOPSHIRIQ (TZ)

## 📌 Loyiha nomi:

Forge CLI — VPS serverda dasturchilar uchun branch asosida mustaqil sandbox yaratadigan CLI vosita.

---

## 🎯 Loyihaning asosiy maqsadi:

Laravel, Node, Go, Python, Rust, yoki har qanday texnologiyada ishlovchi dasturchilar uchun VPS serverda git kabi ishlovchi tizim

---

## 👥 Maqsadli auditoriya:

* Middle / Senior backend developerlar
* Junior developerlar (xavfsiz sandboxda ishlashi uchun)
* DevOps engineer’lar (oddiy test muhitlarini ajratish uchun)
* Team lead’lar (yangi ishga kelganlarga xavfsiz joy berish uchun)

---

## 🔑 Asosiy konsepsiya:

* Har bir developer forge branch <name> buyrug‘i orqali o‘zining izolyatsiyalangan ish joyini yaratadi.
* Har bir branch faqat 1 ta katalog va unga tegishli snapshot**lardan iborat.
* Hech qanday Laravel, PHP, nginx, MySQL avtomatik o‘rnatilmaydi.
* Har bir branchdagi o‘zgarishlar `forge commit` bilan snapshot qilinadi.
* VPS serverga zarar yetkazmaslik uchun `forge destroy` bilan branch tozalab tashlanadi.
* Bu Git falsafasiga o‘xshaydi, lekin bu CLI darajasida, **operatsion tizim muhitida branchlash hisoblanadi.

---

## 🧱 Arxitektura:

### 📂 Katalog struktura:

/home/forge/
├── forge_branch_ali/
├── forge_branch_sardor/
└── .forge_snapshots/
    ├── forge_branch_ali_2025-06-14_12-00.zip
    └── forge_branch_sardor_2025-06-14_13-30.zip

---

### ⚙️ Buyruqlar funksionalligi:

#### ✅ forge branch <name>

* Katalog yaratadi: forge_branch_<name>
* Ichida hech nima avtomatik bo‘lmaydi

#### ✅ forge ssh <name>

* Terminal ichida cd forge_branch_<name> qiladi
* (Kelajakda: chroot, port isolation qo‘shilishi mumkin)

#### ✅ forge commit

* Joriy branch holatini .forge_snapshots/ katalogiga saqlaydi
* .zip, tar.gz, yoki rsync bilan bajariladi

#### ✅ forge rollback

* Oxirgi snapshotni joriy branchga qaytaradi

#### ✅ forge destroy <name>

* Katalogni va snapshot’ni o‘chiradi

#### ✅ forge list

* Barcha mavjud branchlarni chiqaradi

#### ✅ forge status <name>

* Branch haqida meta ma'lumot: yaratilgan vaqt, commit soni, oxirgi snapshot

---

## 🧰 Texnologiyalar:

| Texnologiya  | Izoh                          |
| ------------ | ----------------------------- |
| Laravel Zero | CLI framework sifatida        |
| PHP 8+       | CLI logika                    |
| Bash         | Fayl tizimi amallari          |
| rsync / zip  | Snapshot yaratish va rollback |
| JSON / Yaml  | Metadata saqlash uchun        |

---

## 🚀 Kelajakdagi imkoniyatlar (Optional):

* Port izolatsiyasi (8001, 8002, ...) — nginx conf bilan
* .forge.yml — branchdagi sozlamalar uchun config fayl
* forge push — branchdan remote VPS ga eksport
* forge merge — boshqa branch bilan birlashtirish (manual merge)
* forge env — umumiy PATH, ALIAS, ENV sozlamalarni saqlash

---

## 🛡 Xavfsizlik:

* Har bir branch **faqat o‘z hududi**da ishlaydi
* Root/keng huquqlar kerak bo‘lsa ogohlantirish beriladi
* Buzilgan branch butun tizimga ta’sir qilmaydi

---

## 📅 Bosqichma-bosqich reja:

| Bosqich | Tavsif                                                   |
| ------- | -------------------------------------------------------- |
| 1       | branch, destroy, list komandalarini yozish         |
| 2       | commit, rollback uchun snapshot mexanizmini qo‘shish |
| 3       | ssh, status komandalarini yozish                     |
| 4       | Snapshot arxivlash, log yozish                           |
| 5       | .forge.yml, port izolatsiya, qo‘shimcha modullar       |

---