# WORKLOG — Onik Portfolio (onikcreation.com)

সমস্ত আপডেট ও পরিবর্তনের লগ। নতুন থেকে পুরাতন ক্রমে।

---

## 2026-07-15

### About Me — Image Flip Effect সরানো
- `style.css` থেকে `.about-image-wrap:hover img { transform: scaleX(-1); }` সরানো হয়েছে
- এখন ছবিতে hover করলে আর flip হবে না

### Profile Photo — Illustrated Avatar দিয়ে Replace
- `assets/profile.jpg` → `assets/profile.png` (Adobe Firefly দিয়ে তৈরি illustrated avatar)
- `index.html`-এ সব `profile.jpg` reference → `profile.png` করা হয়েছে (og:image, Hero, About — ৩ জায়গা)

### Navbar — FIFA World Cup 2026 বাটন সরানো
- `index.html` navbar থেকে FIFA WC26 বাটন ও logo সরানো হয়েছে

### Hero Section — Mobile Responsive Compress
- `@media (max-width: 480px)` block-এ hero section-এর সব element compact করা হয়েছে
- Photo: 120px → 86px, margin/padding কমানো, quote ও bio font ছোট করা
- `min-height: 100svh` ব্যবহার করে পুরো hero এক স্ক্রিনে দেখানো নিশ্চিত করা হয়েছে
- Scroll-down arrow মোবাইলে hide করা হয়েছে

### Hero Section — Personal Quote Block যোগ
- `.hero-bio` এর পরে `<blockquote class="hero-quote">` যোগ করা হয়েছে
- `style.css`-এ `.hero-quote` style: left accent border, glass background, italic Bengali text

### Project Links — Renamed Repository URLs আপডেট
- `The_Holy_Quran` → `Quran`
- `fifa-world-cup-2026` → `fifa26`
- `Digital_V_Card` → `VCard`
- মোট ৪টি জায়গা আপডেট: navbar (1) + project cards (3)

### Projects Section — Holy Quran Project Card যোগ
- `fa-solid fa-quran` icon সহ নতুন card projects grid-এর শুরুতে যোগ করা হয়েছে
- Live URL: `https://onikcreation.com/Quran/`
- Tags: HTML, CSS, JavaScript, Web API

### Work Experience — ৪টি Timeline Card যোগ
- Placeholder card সরিয়ে ৪টি পূর্ববর্তী পদের card যোগ:
  1. Senior Executive – IT & Hardware | Udvash (Corporate) | 2020–2022
  2. Executive – Computer Operation | Udvash (Motijheel) | 2016–2020
  3. Junior Executive – Computer Operation | Udvash (Shantinagar) | 2014–2016
  4. Junior Executive – Computer Operation | Udvash (Farmgate) | 2013–2014
- প্রতিটিতে timeline dot, duties (3টি), skill tags আছে

### data.html — Mobile Responsive Card Layout
- `@media (max-width: 600px)` এ table → card layout করা হয়েছে
- `td[data-label]::before` দিয়ে column label দেখানো হয়
- JS-এ `td.dataset.label = col.label` যোগ করা হয়েছে
- Header buttons মোবাইলে compact করা হয়েছে

### My Data Button — Floating Left Button
- `index.html` navbar থেকে `nav-mydata-btn` সরানো হয়েছে
- নতুন `.mydata-floater` div যোগ (fixed, bottom-left, থিম বাটনের মতো)
- `style.css` থেকে `nav-mydata-btn` style সরানো, নতুন `.mydata-float-btn` style যোগ

---

## পূর্ববর্তী Session (সারসংক্ষেপ)

### data.html — Private Data Manager তৈরি
- Firebase Auth (Email/Password) + Firestore real-time database
- `browserSessionPersistence` — browser বন্ধ হলে auto logout
- দুটি Tab: 📋 Records এবং 💰 Finance
- Records columns: Title → Description → Note → URL → Category → Updated

### data.html — Edit/View Mode System
- Header-এ সবসময় mode badge দেখায়: `👁 View` / `✏️ Edit`
- View Mode: Edit/Delete বাটন থাকে না
- Edit Mode: Text "Edit" + "Delete" বাটন দেখায়
- `sessionStorage` দিয়ে reload-এ Edit Mode persist

### data.html — Category Filter
- Records tab-এ category chip filter যোগ
- Default: "All" selected
- Category tag থেকে auto-generate হয়

### data.html — Copy Buttons
- Description ও Note (textarea) column-এ 📋 copy বাটন
- URL column-এ 📋 copy বাটন
- ডাটা না থাকলে copy বাটন দেখায় না

### data.html — Loading Fix
- `tabLoading` state দিয়ে "No records yet" flash সমস্যা সমাধান
- প্রথম snapshot আসার আগে spinner দেখায়

### login.html — Font Fix
- Google Fonts (Inter) যোগ করা হয়েছে
- `browserSessionPersistence` সঠিক জায়গায় (sign-in এর আগে) সেট করা হয়েছে

### firestore.rules তৈরি
- শুধু authenticated user নিজের data read/write করতে পারবে

### Portfolio — GitHub Links সরানো
- Hero section social links থেকে GitHub সরানো
- Contact section থেকে GitHub সরানো
- Project cards-এ Code বাটন disable করা (Digital Business Card, DU Result Scraper, Random Number Picker)

---

## ফাইল সংক্রান্ত তথ্য

| ফাইল | কাজ |
|------|-----|
| `index.html` | মূল portfolio পেইজ |
| `style.css` | সব styling |
| `app.js` | vCard download, loader, theme switcher, color picker |
| `login.html` | Firebase login পেইজ |
| `data.html` | Private data manager dashboard |
| `firestore.rules` | Firestore security rules |
| `assets/profile.png` | Illustrated avatar (Adobe Firefly) |
| `assets/OnikLogo.png` | Site logo |
| `assets/HeaderLogo.png` | Navbar logo |

---

## Deploy Info
- GitHub Pages: `onikcreation.github.io` → custom domain `onikcreation.com`
- Firebase Project: `onik-private-data`
- Auto-deploy: `git push` করলেই GitHub Pages আপডেট হয়
