# RevicTen — PC Setup Guide
> Powered by **WriterTen**

এই guide টা follow করলে আপনার PC তে RevicTen সেটআপ হয়ে যাবে এবং video generate করা শুরু করতে পারবেন।

---

## সিস্টেম requirements

| বিষয় | Minimum | 
|---|---|
| Operating System | Windows 10 / Windows 11 (64-bit) |
| RAM | 4 GB |
| Storage | 500 MB (exe + Chromium browser) |
| Internet | চাই — Amazon + Pixabay scraping এর জন্য |
| Browser | Chrome / Edge / Firefox (dashboard দেখার জন্য) |

---

## ধাপ ১ — exe ডাউনলোড করুন

1. আপনার কাছে পাঠানো `RevicTen.exe` ফাইলটা ডাউনলোড করুন
2. যেকোনো জায়গায় রাখুন — যেমন `C:\Tools\RevicTen.exe` অথবা Desktop এ

> **নোট:** exe টা একটাই ফাইল, আলাদা install করতে হয় না।

---

## ধাপ ২ — প্রথমবার চালু করুন

`RevicTen.exe` তে **double-click** করুন।

### প্রথমবার চালানোর সময় যা হবে

```
✅ Server শুরু হবে (localhost:5812)
✅ Chromium browser download হবে (~150 MB) — একবারই হয়
✅ System tray এ icon দেখাবে (নিচের right কোণে)
```

Chromium download হতে **2–5 মিনিট** লাগতে পারে internet speed এর উপর নির্ভর করে। এই সময় exe টা বন্ধ করবেন না।

#### Windows Defender / Antivirus warning দেখালে

```
"Windows protected your PC" popup এলে:
→ "More info" চাপুন
→ "Run anyway" চাপুন
```

এটা স্বাভাবিক — আমাদের RevicTen exe টা Microsoft এর code signing certificate ছাড়া, তাই Windows প্রথমবার সতর্ক করে। এটা WriterTen এর একটা official tool।

---

## ধাপ ৩ — Dashboard খুলুন

exe চালু হওয়ার পর browser এ যান এবং এই address লিখুন:

```
http://localhost:5812
```

Login page দেখাবে।

---

## ধাপ ৪ — Account তৈরি করুন বা Login করুন

### নতুন account তৈরি করতে

1. **First Name, Last Name, Username, Email, Password** দিন
2. **Signup** চাপুন
3. Email এ একটা **6 digit code** আসবে
4. সেই code দিয়ে email verify করুন

### আগে থেকে account থাকলে

Email এবং Password দিয়ে **Login** করুন।

### Google দিয়ে login করতে

**"Continue with Google"** চাপুন → আপনার Gmail account select করুন।

---

## ধাপ ৫ — YouTube Channel connect করুন

Video upload করার জন্য আপনার YouTube channel connect করতে হবে।

1. **YouTube channels** menu তে যান (বাম sidebar এ)
2. **"+ Connect channel"** button চাপুন
3. একটা popup window খুলবে → আপনার Google account দিয়ে login করুন
4. **"Allow"** চাপুন
5. Popup বন্ধ হয়ে যাবে এবং channel টা list এ দেখাবে

### একাধিক channel connect করা যাবে

**"+ Connect channel"** আবার চাপুন এবং অন্য Google account দিয়ে login করুন। প্রতিটা channel আলাদাভাবে connect করতে হবে।

---

## ধাপ ৬ — API Keys যুক্ত করুন (Lifetime plan)

> এই ধাপটা শুধু **Lifetime plan** ব্যবহারকারীদের জন্য।

নিজের API key দিলে আপনার নিজের quota ব্যবহার হবে।

**Settings → API keys** এ যান।

| Provider | কোথায় পাবেন | কীসের জন্য |
|---|---|---|
| **ElevenLabs** | elevenlabs.io → Profile → API key | AI voiceover |
| **Anthropic** | console.anthropic.com → API keys | Script লেখা (Claude) |
| **OpenAI** | platform.openai.com → API keys | Alternative script |
| **OpenRouter** | openrouter.ai → Keys | Multiple AI models |

প্রতিটার জন্য:
1. সেই provider এর website এ যান
2. API key copy করুন
3. Settings page এ paste করুন → **Save** চাপুন

API key না দিলেও হয় — তখন platform এর shared key ব্যবহার হবে।

---

## ধাপ ৭ — Video generate করুন

1. **Generate video** menu তে যান
2. একটা format select করুন:

| Format | কীসের জন্য |
|---|---|
| **Single product review** | একটা product এর review |
| **VS comparison** | দুটো product এর তুলনা |
| **Best N picks** | Top 3/5/10 product countdown |
| **Info / explainer** | Educational নিশ content |
| **Bulk video generator** | একসাথে অনেক video |
| **Seasonal / deal alert** | Sale/trending সময়ের video |

3. Keyword অথবা Amazon ASIN দিন
4. কোন YouTube channel এ upload হবে select করুন
5. **"Generate video"** চাপুন

Video generate হতে সময় লাগবে — **3–10 মিনিট** (একটা video এর জন্য)।

---

## System Tray থেকে control করা

exe চালু থাকলে Windows taskbar এর নিচে right কোণে একটা icon দেখাবে।

**Right-click** করলে menu আসবে:

```
📂 Open Dashboard     → browser এ localhost:5812 খোলে
ℹ️  Version: 1.0.0    → current version দেখায়
🔴 Quit               → agent বন্ধ করে
```

---

## Auto-update

নতুন version available হলে agent চালু হওয়ার সময় automatically download করবে এবং নিজেই update হবে। আপনাকে কিছু করতে হবে না।

Update এর সময় একটা notification আসবে:
```
"New version available. Updating..."
```

Update শেষ হলে agent restart হবে — browser refresh করুন।

---

## সাধারণ সমস্যা এবং সমাধান

### `localhost:5812` খুললে কিছু দেখা যাচ্ছে না (blank page)

**কারণ:** exe চালু হয়নি বা server start হতে সময় লাগছে।

**সমাধান:**
1. Taskbar এ RevicTen icon আছে কিনা দেখুন
2. না থাকলে exe আবার double-click করুন
3. 10–15 সেকেন্ড অপেক্ষা করুন তারপর refresh করুন

---

### Chromium download হচ্ছে না বা আটকে আছে

**সমাধান:**
1. Internet connection check করুন
2. Antivirus temporarily disable করুন
3. exe বন্ধ করুন এবং আবার চালু করুন

---

### Login করার পর `Not authorized` error

**কারণ:** Token মেয়াদ শেষ হয়ে গেছে।

**সমাধান:** Page refresh করুন অথবা logout করে আবার login করুন.

---

### YouTube channel connect করতে `access_denied` error

**কারণ:** আপনার Gmail account টা app এর test user list এ নেই।

**সমাধান:** আপনার Gmail address আমাদের কাছে পাঠান — আমরা যুক্ত করে দেব।

---

### Video generate করার সময় অনেকক্ষণ লাগছে

এটা **স্বাভাবিক**। Video generate করতে সময় লাগে:

| কাজ | সময় |
|---|---|
| Amazon scraping | 30–90 সেকেন্ড |
| AI script লেখা | 15–45 সেকেন্ড |
| Voice generation | 30–60 সেকেন্ড |
| Video render | 1–5 মিনিট |
| YouTube upload | 1–3 মিনিট |

Browser tab বন্ধ করবেন না — background এ চলছে।

---

### exe চালানোর পর Windows Defender block করছে

**সমাধান:**
1. Start menu → **Windows Security** খুলুন
2. **Virus & threat protection** → **Protection history** তে যান
3. RevicTen সংক্রান্ত alert খুঁজুন
4. **"Allow on device"** চাপুন

---

### Port 5812 already in use error

**কারণ:** আগের একটা instance চলছে।

**সমাধান:**
1. System tray এ icon এ right-click → **Quit**
2. অথবা Task Manager (Ctrl+Shift+Esc) → RevicTen → End Task
3. আবার exe চালু করুন

---

## PC বন্ধ করলে কী হবে?

PC বন্ধ করলে agent ও বন্ধ হয়ে যায়। পরের বার PC চালু করার পর exe আবার double-click করতে হবে।

**Auto-start** করতে চাইলে (PC চালু হলে agent automatically start হবে):

1. `Win + R` চাপুন → `shell:startup` লিখুন → Enter
2. যে folder খুলবে সেখানে `RevicTen.exe` এর একটা **shortcut** রাখুন

---

## Uninstall করতে

1. System tray → Right-click → **Quit**
2. `RevicTen.exe` file টা delete করুন
3. Chromium browser delete করতে চাইলে:
   `C:\Users\আপনার নাম\AppData\Local\ms-playwright` ফোল্ডারটা delete করুন

---

## সাহায্য দরকার?

RevicTen এর support team এর সাথে যোগাযোগ করুন।

সমস্যা হলে এই তথ্য সহ contact করুন:

1. কী সমস্যা হচ্ছে (screenshot সহ হলে ভালো)
2. Windows version (Settings → System → About)
3. exe version (system tray icon এ right-click করলে দেখাবে)
