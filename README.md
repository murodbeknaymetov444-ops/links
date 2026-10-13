# NAYMETOV — havolalar sahifasi (GitHub Pages)

## Fayllar
- `index.html` — ochiq sayt (havolalar, profil rasm). Panel yo'q.
- `admin.html` — himoyalangan panel (parol bilan). Alohida havola.
- `data.json` — sayt ma'lumotlari (ism, username, rasm, havolalar).
- `robots.txt` — panelni Google'dan yashiradi.
- `.nojekyll` — GitHub Pages uchun kerak.

## 1) GitHub Pages'ga joylash
1. github.com'da **yangi repo** oching (masalan `links`), Public.
2. Shu papkadagi barcha fayllarni repo ildiziga yuklang (Add file → Upload files).
3. Repo → **Settings → Pages** → Source: `Deploy from a branch`, Branch: `main`, papka `/ (root)` → Save.
4. 1–2 daqiqadan keyin havola chiqadi:
   `https://<username>.github.io/links/`

## 2) Saytni yangilash (nashr qilish)

> Muhim: panel saytni **o'zi avtomatik o'zgartirmaydi**. Tahrirni saqlagach, uni **nashr** qilish kerak.

### A) Avtomatik nashr (bir marta sozlanadi) — asosiy usul
1. GitHub'da **fine-grained token** yarating:
   https://github.com/settings/personal-access-tokens/new
   - **Name:** `panel` | **Expiration:** 90 days
   - **Repository access** → *Only select repositories* → **links**
   - **Permissions → Repository permissions → Contents → Read and write**
   - **Generate token** → tokenni nusxalang (`github_pat_...`)
2. `admin.html` ni oching → parolni kiriting.
3. Pastdagi **«GitHub'ga ulash»** → tokenni joylashtiring → **Ulanishni saqlash**.
   (Owner/Repo/Branch oldindan to'ldirilgan: `murodbeknaymetov444-ops` / `links` / `main`)
   → tepadagi yozuv **yashil** bo'ladi: "GitHub ulangan ✓".
4. Endi har safar: tahrirlang → **«GitHub'ga saqlash (jonli)»** → ~1 daqiqa kuting → saytni **Ctrl+F5** qiling.

### B) Qo'lda nashr (token yo'q bo'lsa)
1. Tahrirlang → **data.json yuklab olish**.
2. Yuklab olingan `data.json` ni repodagi eskisi ustiga yuklang (commit).
3. Sayt avtomatik yangilanadi.

## 3) Parolni o'zgartirish
Panel → «Parolni o'zgartirish» → yangi parol → **Hash yaratish** → chiqqan hash'ni
`admin.html` ichidagi `PASS_SHA = "..."` qatoriga qo'ying va repoga yuklang.

## 4) Google'ga indekslash (bepul)
1. [Google Search Console](https://search.google.com/search-console) → URL prefix → sayt manzilini qo'shing.
2. `https://<username>.github.io/links/` ni tekshirib, **Request indexing** bosing.
3. `admin.html` `robots.txt` bilan yashirilgan + `noindex` — qidiruvda chiqmaydi.

## 5) Xavfsizlik (muhim)
- Bu statik sayt — server yo'q, ya'ni "buzib" ma'lumot o'g'irlash mumkin emas.
- **Asosiy himoya = GitHub akkaunti:** kuchli parol + **2FA** yoqing.
- `admin.html` havolasini hech kimga bermang. Xohlasangiz fayl nomini `admin.html` → maxfiy nomga o'zgartiring.
- Parol-qatlam faqat tasodifiy kirishni to'sadi (kod ochiq, chunki sayt statik).

## Lokal ko'rish
`index.html` ni ikki marta bosib ochsangiz ham ishlaydi (ma'lumot ichida).
`admin.html` lokalda `data.json` ni o'qiy olmasa — **Import (data.json)** tugmasidan foydalaning.
