# Whoami Kali — APK (GitHub Actions orqali avtomatik qurish)

Bu loyiha ikonka bosilganda `kali_maktab.pdf` kitobini ILOVANING O'ZI
ICHIDA (tashqi PDF-dastur ochilmasdan) sahifama-sahifa, barmoq bilan
varaqlab ko'rsatadigan Android ilova. Android'ning o'ziga xos
`PdfRenderer` vositasidan foydalanilgan — hech qanday tashqi PDF
kutubxona shart emas. Kitobning o'zi ilova ichida
(`app/src/main/assets/kali_maktab.pdf`) tayyor holda turibdi.

## APK ni GitHub orqali qurish

1. Yangi (bo'sh) GitHub repo oching, masalan `whoami-kali-apk`.
2. Ushbu papkadagi BARCHA fayl va papkalarni (`.github` papkasi ham
   ko'rinishi uchun yashirin fayllarni ko'rsatishni yoqing) o'sha
   repoga yuklang (push qiling).
3. GitHub'da repo ichidagi **Actions** bo'limini oching — "APK qurish"
   workflow'i avtomatik ishga tushadi (`main` branchga push qilinganda).
   Agar o'zi ishga tushmasa, Actions bo'limida workflow'ni tanlab
   **Run workflow** tugmasini bosing.
4. Qurilish tugagach (~5–10 daqiqa), ochilgan workflow natijasi ichidagi
   **Artifacts** qismidan `whoami-kali-apk` faylini yuklab oling — bu
   ZIP ichida `app-debug.apk` bor.
5. `app-debug.apk` ni telefoningizga ko'chiring va o'rnating (noma'lum
   manbalardan o'rnatishga ruxsat berish kerak bo'lishi mumkin).
6. Ikonkani bossangiz — kitob ilova ICHIDA ochiladi; sahifalarni chapga/
   o'ngga suring, pastda joriy sahifa raqami ko'rinib turadi.

## Kitobni yangilash

Agar kitobni qayta qursangiz (`build.py` orqali yangi
`kali_maktab.pdf` chiqsa), shunchaki uni
`app/src/main/assets/kali_maktab.pdf` fayli o'rniga qo'yib, qayta
GitHub'ga push qiling — Actions o'zi qayta quradi.

## Eslatma

- Ilova kitobni o'zi QAYTA QURMAYDI (reportlab, matplotlib,
  python-docx kabi kutubxonalarni Android'ga ko'chirish juda murakkab
  va beqaror); ilova faqat tayyor PDF faylni ICHKARIDA ko'rsatadi
  (sahifalarni rasmga chizib, varaqlab chiqish imkonini beradi).
- Kitob hajmi katta bo'lgani uchun (rasmlar bilan ~70 MB) tayyor APK
  ham shunga mos ravishda katta chiqadi — bu normal holat.
- Agar kelajakda kitobni ilova ICHIDA (masalan yangi mavzu qo'shilganda)
  qayta generatsiya qilish kerak bo'lsa, bu butunlay boshqa, ancha
  murakkabroq loyiha bo'ladi (Kivy/Buildozer yoki server-side qurish).
- Workflow birinchi marta ishga tushganda GitHub action versiyalari
  (masalan `android-actions/setup-android@v3`) eskirgan bo'lishi mumkin —
  shunday xato chiqsa, action versiyasini bir qadam yuqoriga
  (masalan `@v4`) o'zgartirib qayta urinib ko'ring.
