# WORKLOG — Onik Portfolio (onikcreation.com)

সমস্ত আপডেট ও পরিবর্তনের লগ। নতুন থেকে পুরাতন ক্রমে।

---

## 2026-11-04

### UUU Task Tracker — Clear Filter ও সার্চ বক্সের লেখা
- Release Notes ফিল্টারের শেষে "Clear Filter" বোতাম
- ডার্ক মোডে উপরের সার্চ বক্সে টাইপ করা লেখা দেখা যেত না — ঠিক করা হয়েছে

### UUU Task Tracker — Release Notes-এ Platform ও Given By ফিল্টার
- সার্চ বক্সের পাশে দুটো ড্রপডাউন ফিল্টার (শুধু নোটে ব্যবহৃত মান)

### UUU Task Tracker — Release Notes-এ Platform ও "নোট দিয়েছেন"
- প্রতিটা নোটে Platform (একাধিক) আর কে নোট দিয়েছেন; সাইডবারে সংখ্যা বাদ

### UUU Task Tracker — সাইডবারে "Release Notes" মেনু
- `tasks/index.html` আপডেট: ডেভেলপারদের রিলিজ নোট কপি-পেস্ট করে সেভ (তারিখ, ঐচ্ছিক শিরোনাম, লেখা হুবহু), সার্চ, কপি/এডিট/মোছা
- ডেটা Supabase-এ (`app.release_notes`)

---

## 2026-11-03

### UUU Task Tracker — ড্যাশবোর্ডের নতুন ডিজাইন
- `tasks/index.html` আপডেট: KPI ডেস্কটপে এক লাইনের স্ট্রিপে (বিশেষ ভিউসহ), মোবাইলে ৩ কলামের ছোট বক্স; "Entered this month" → "This Month"
- help.ums মেইল কার্ড তিন ভাগে সাজানো, Sync বাটন (সাথে সাথে নতুন হিসাব), মেম্বার টেবিলে "গত মাস" কলাম

### UUU Task Tracker — ড্যাশবোর্ডে "help.ums মেইল" কার্ড
- `tasks/index.html` আপডেট: KPI-র নিচে help.ums মেইলের হিসাব — Unread, রিপ্লে বাকি, কে কতগুলো রিপ্লে দিলেন, রিপ্লে বাকি মেইলের তালিকা (৩০ সেকেন্ড পরপর)
- শুধু লগইন করা ইউজার দেখে; তথ্য আসে help.ums-এর Apps Script থেকে, লিংক ডেটাবেসে (পেইজে নেই)

---

## 2026-11-02

### UUU Task Tracker — ড্যাশবোর্ডে "Tasks entered last month"
- `tasks/index.html` আপডেট: এই মাসের প্রতিদিনের এন্ট্রি চার্টের নিচে গত মাসের একই রকম চার্ট (সারাংশ, টেবিল, বারে চাপলে সেই দিনের টাস্ক)

---

## 2026-11-01

### UUU Task Tracker — `/tasks` এখন Supabase সংস্করণ (চূড়ান্ত)
- `tasks/index.html` = পুরো সাইট (আগে Google Apps Script-এ redirect ছিল); শেয়ারের প্রিভিউ (og:*) ও noindex আছে
- `tasks-beta/index.html` এখন `/tasks/`-এ redirect (পপআপ লিংকের #task=… সহ)
- পুরনো Apps Script লিংক নিজেও নতুন ঠিকানা দেখায়, সেভ নেয় না

### UUU Task Tracker — Supabase সংস্করণের পরীক্ষামূলক সাইট (`/tasks-beta`)
- `tasks-beta/index.html` যোগ → `onikcreation.com/tasks-beta`: Google Sheet-এর বদলে Supabase ডেটাবেস, UI হুবহু একই
- উৎস: `ERP UI Design/5. MixData/ERPTechnicalProblemSupabaseClaude` (`_build/build_supabase.js` → `site/index.html`)
- পরীক্ষা শেষে `/tasks`-এর redirect-এর বদলে এই সাইট বসবে

---

## 2026-10-20

### UUU Task Tracker — ছোট লিংক (`/tasks`)
- `tasks/index.html` যোগ করা হয়েছে → `onikcreation.com/tasks` খুললে UUU Task Tracker (Google Apps Script web app)-এ নিয়ে যায়
- JavaScript দিয়ে redirect (meta refresh না, যাতে WhatsApp/Messenger প্রিভিউ ঠিক থাকে), শেয়ারের og: প্রিভিউ, `noindex`, ফলব্যাক "সাইট খুলুন" বাটন
- গুগলের লিংক বদলালে শুধু `tasks/index.html`-এর `TARGET` আর বাটনের `href` আপডেট করতে হবে

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
| `tasks/index.html` | UUU Task Tracker (Supabase) — পুরো সাইট |
| `tasks-beta/index.html` | পুরনো বিটা লিংক → `/tasks/` redirect |

---

## Deploy Info
- GitHub Pages: `onikcreation.github.io` → custom domain `onikcreation.com`
- Firebase Project: `onik-private-data`
- Auto-deploy: `git push` করলেই GitHub Pages আপডেট হয়
