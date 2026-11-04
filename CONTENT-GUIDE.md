# Prep Meal থিম: কনটেন্ট ইনপুট গাইড

এই গাইড দিয়ে ক্লায়েন্ট কোনো ডেভেলপার ছাড়াই পুরো সাইটের কনটেন্ট বসাতে পারবে।

> **নোট:** এই ফাইলের সব সেটিংস, ফিল্ডের নাম আর মেটাফিল্ড কি (key) থিমের আসল কোড থেকে যাচাই করা। থিম আপডেট করলে আবার মিলিয়ে দেখুন।

---

## ১. কাজের নিয়ম (একবার পড়ুন)

থিমে প্রতিটি সেকশন **দুইভাবে** কনটেন্ট নেয়:

| মোড | কখন ব্যবহার করবেন | কোথায় এডিট করবেন |
|---|---|---|
| **Blocks মোড** | অল্প কনটেন্ট (৩–৬টি আইটেম) | Online Store → Themes → Customize → সেকশন সিলেক্ট করে |
| **Metaobject মোড** | বেশি কনটেন্ট (৭+ আইটেম), বারবার বদলায় | Content → Metaobjects → এন্ট্রি যোগ করুন |

**ক্রম:** সেকশনে Metaobject লিস্ট সিলেক্ট করা থাকলে সেটা দেখাবে। খালি বা সব এন্ট্রি খালি থাকলে Blocks-এর কনটেন্ট দেখাবে। দুটোই খালি থাকলে এডিটরে একটি এম্পটি মেসেজ দেখাবে — সাইট ভাঙবে না।

**Metaobject মোড চালু করার ধাপ:**
1. Shopify Admin → **Content → Metaobjects → Add definition**।
2. নিচের তালিকা থেকে **Type** নামটি হুবহু লিখুন (যেমন `meal_plan`)। তৈরি করার পর Type বদলানো যায় না।
3. প্রতিটি ফিল্ডের নামও হুবহু মিলিয়ে দিন — ফিল্ডের নামই Liquid-এ ব্যবহার হয়।
4. Entry যোগ করুন এবং **Active** স্ট্যাটাস দিন।
5. Customize-এ গিয়ে সেকশনের **Content source** থেকে ওই লিস্ট সিলেক্ট করুন।
6. Save দিন।

---

## ২. কনটেন্ট এরিয়া অনুযায়ী ইনপুট গাইড

### ২.০ প্ল্যান পেজ Customize (৬ মিল) — ক্লিক করে এডিট

৬ মিল প্ল্যান টেমপ্লেটে Hero আর Benefits **আলাদা সেকশন**. প্রিভিউতে ক্লিক করলে বাম পাশে সেই সেকশন সিলেক্ট হয়, ডান পাশে শুধু সেই ফিল্ডগুলো দেখায়।

| বাম সাইডবার | সেকশন ফাইল | কী এডিট করবেন |
|---|---|---|
| **MP Hero** | `cm-mp-hero` | হেডিং, টেক্সট, ফ্যাক্ট, বাটন, হিরো ছবি |
| **MP Benefits** | `cm-mp-benefits` | “6 meals. 1 week. Zero stress.”, নোট, Benefit chip ব্লক |
| **CM meal plan page** | `cm-meal-plan-page` | প্ল্যান প্রোডাক্ট, মেনু, অর্ডার বক্স, শেফ, ডেলিভারি, FAQ… |

**ধাপ:** Customize → ৬-মিল পেজ → প্রিভিউতে হিরো টেক্সটে ক্লিক → বামে **MP Hero** → ডানে Heading এডিট। বিস্তারিত: `PLAN-PRODUCT-CONTENT.md` সেকশন ০।

CM meal plan page-এ **Show built-in hero / benefits** বন্ধ রাখুন — না হলে দুইবার Hero দেখাবে।

### ২.১ Hero (হোমপেজের ব্যানার)

**মোড:** শুধু Customizer (Metaobject লাগবে না)। প্ল্যান পেজের Hero আলাদা — উপরের **MP Hero** দেখুন।

| ফিল্ড | ধরন | নির্দেশনা |
|---|---|---|
| Heading | Text | সর্বোচ্চ ৬০ অক্ষর। যেমন: "সারা সপ্তাহের খাবার, রেডি।" |
| Text / subheading | Text | সর্বোচ্চ ১২০ অক্ষর। এক বাক্যে মূল সুবিধা |
| Background image | Image | ১৯২০×১০৮০ px, ৩০০ KB এর নিচে, খাবারের উপর টেক্সট পড়া যায় এমন ছবি |
| Button label / link | Text / URL | লেবেল ২–৩ শব্দ ("প্ল্যান দেখুন")। লিংক: কালেকশন বা প্ল্যান পেজ |

### ২.২ Meal Plans (প্ল্যান)

**Metaobject type:** `meal_plan`

| ফিল্ড | ধরন | নির্দেশনা |
|---|---|---|
| Name | Single line text | যেমন: "Lean 5-Day" |
| Image | File (image) | ৮০০×৮০০ px, বর্গাকার, সব প্ল্যানে একই স্টাইল |
| Short description | Single line text | সর্বোচ্চ ৮০ অক্ষর |
| Meals per week | Integer | যেমন: 10 |
| Calories per meal | Integer | গড় ক্যালরি |
| Protein / Carbs / Fat | Integer (৩টি আলাদা ফিল্ড) | প্রতি মিলের গড় গ্রাম |
| Tags | List of single line text | যেমন: Keto, High Protein, Vegan |
| Linked product | Product reference | কার্টে যাবে যে প্রোডাক্টে |
| Badge | Single line text | ঐচ্ছিক: "Best Seller" |

**টিপ:** প্ল্যান ৩–৬টির মধ্যে রাখুন। বেশি হলে ফিল্টার ট্যাগ ব্যবহার করুন।

### ২.৩ Individual Meals (মেনু আইটেম)

প্রতিটি মিল Shopify **Variant** হিসেবে থাকে। নিউট্রিশন ও অ্যালার্জেনের তথ্য **Variant metafield**-এ দিন, তাহলে প্রতি মিল আলাদা দেখাবে।

কোথায় যোগ করবেন: **Settings → Custom data → Variants → Add definition**

| Metafield | ধরন | ব্যবহার |
|---|---|---|
| `custom.calories` | Integer | কার্ডে ক্যালরি ব্যাজ |
| `custom.protein` / `carbs` / `fat` | Integer | নিউট্রিশন বার |
| `custom.ingredients` | Multi-line text | প্রোডাক্ট পেজের Ingredients ট্যাব |
| `custom.allergens` | List of text | অ্যালার্জেন আইকন (Gluten, Dairy, Nuts) |
| `custom.diet_tags` | List of text | ফিল্টার ও ব্যাজ |
| `custom.reheat_instructions` | Multi-line text | গরম করার নিয়ম |

**গুরুত্বপূর্ণ:** থিম এই কি-গুলো তিন জায়গায় খোঁজে — Variant metafield → `meal` metaobject → Product metafield (`custom.*`)। শুধু Product metafield-এ দিলে সব মিল একই মান দেখাবে। তাই **Variant-এ দিন**।

**নির্দেশনা:** অ্যালার্জেন তথ্য সবসময় সঠিক ও আপ-টু-ডেট রাখুন। এটা গ্রাহকের স্বাস্থ্য-নিরাপত্তার বিষয়।

### ২.৪ প্ল্যান পেজের ছবি

প্ল্যান পেজের প্রতিটি ছবি **তিন ধাপে** খোঁজা হয় — Product metafield → Customizer → থিমের বান্ডল করা ছবি। তাই একটি প্ল্যানের ছবি বদলাতে নতুন টেমপ্লেট লাগে না।

| ছবি | ১ম — Product metafield | ২য় — Customizer | ৩য় — বান্ডল করা |
|---|---|---|---|
| Hero (২টি) | `custom.hero_image_1`, `custom.hero_image_2` (+ shop-level) | **MP Hero** → `hero_image_1`, `hero_image_2` | বান্ডল করা ছবি |
| Chef story (২টি) | `custom.chef_image_1`, `custom.chef_image_2` (+ shop-level) | `chef_image_1`, `chef_image_2` | বান্ডল করা ছবি |
| Thali প্লেট | `custom.thali_image` | `thali_image` | `four-items-plate.webp` |
| Meal কার্ড | `meal` metaobject → `image` | — | Variant-এর ছবি → প্ল্যানের featured image → `mp-food-N.jpg` |
| CTA ব্যাকগ্রাউন্ড | `custom.cta_image` (+ shop-level) | `cta_image` | বান্ডল করা ছবি |
| রিভিউয়ার ফটো | `testimonial` → `photo` | — | কিছু দেখাবে না (ফটো ছাড়া কার্ড ঠিকই থাকে) |

**নিয়ম:** metafield-এর মান মুছে দিলে থিমের ছবি ফিরে আসে। মান খালি রাখা মানে "সেট করা নেই" — "কিছু দেখাবে না" নয়।

### ২.৫ Thali প্লেটের ৪টি ট্যাগ (কোণা)

প্লেটের চার কোণায় চারটি ট্যাগ বসে। ক্রম অনুযায়ী কোণা ঠিক হয়:

| লাইন | কোণা |
|---|---|
| ১ম | উপরে বাঁয়ে |
| ২য় | উপরে ডানে |
| ৩য় | নিচে বাঁয়ে |
| ৪র্থ | নিচে ডানে |

**যদি মাত্র ৩টি ট্যাগ দেখেন** — কিছু ভাঙেনি, আপনার লেখা মাত্র ৩ লাইন। চতুর্থ লাইন যোগ করুন।

- লেখা আসে: `custom.thali_chips` → **Plate labels** (Customizer) → বান্ডল করা ডিফল্ট (Homestyle Sabzi / 2 Soft Rotis / Authentic Curries / Fluffy Portion of Rice)
- প্রতি লাইনে ২–৩ শব্দ রাখুন। লম্বা লেখা প্লেটের খাবারের উপর চলে আসে
- **ফাঁকা লাইন স্কিপ হয়।** মাঝখানে ফাঁকা লাইন দিলে পরের ট্যাগগুলো এক কোণা উপরে সরে যাবে
- ৪টির বেশি লাইন দিলে ৫ম লাইনটি কোনো কোণা পায় না — প্লেটের উপর এলোমেলোভাবে বসে যায়

### ২.৬ How It Works (কীভাবে কাজ করে)

**Metaobject type:** `how_it_works_step`

| ফিল্ড | ধরন | নির্দেশনা |
|---|---|---|
| Step number | Integer | 1, 2, 3... (এই ক্রমেই দেখাবে) |
| Title | Single line text | ২–৪ শব্দ। যেমন: "প্ল্যান বাছুন" |
| Description | Multi-line text | ১–২ বাক্য, সর্বোচ্চ ১৫০ অক্ষর |
| Icon | File | SVG বা ১২০×১২০ px PNG |

**টিপ:** ৩ বা ৪ ধাপ সবচেয়ে ভালো কাজ করে।

### ২.৭ FAQ

**Metaobject type:** `faq_item`

| ফিল্ড | ধরন | নির্দেশনা |
|---|---|---|
| Question | Single line text | গ্রাহক যেভাবে জিজ্ঞেস করে সেভাবে লিখুন |
| Answer | Rich text | সর্বোচ্চ ৩–৪ বাক্য, লিংক দেওয়া যাবে |
| Category | Single line text | Delivery, Meals, Billing, Account |
| Sort order | Integer | ছোট সংখ্যা আগে দেখাবে |

**অবশ্যই কভার করুন:** ডেলিভারির দিন, স্কিপ/পজ করার নিয়ম, ফ্রিজে কতদিন থাকে, অ্যালার্জেন, রিফান্ড।

### ২.৮ Testimonials

**Metaobject type:** `testimonial`

| ফিল্ড | ধরন | নির্দেশনা |
|---|---|---|
| Customer name | Single line text | প্রথম নাম + নামের প্রথম অক্ষর |
| Photo | File (image) | ২০০×২০০ px, বর্গাকার, ঐচ্ছিক |
| Review | Multi-line text | সর্বোচ্চ ২০০ অক্ষর |
| Rating | Rating | ৫ এর মধ্যে |
| Plan name | Single line text | ঐচ্ছিক |

**নিয়ম:** শুধু বাস্তব রিভিউ ব্যবহার করুন এবং গ্রাহকের অনুমতি নিন। একটি রিভিউ একবার যোগ করলে সাইটের সব জায়গায় সেটি দেখাবে — আলাদা করে দুইবার যোগ করবেন না।

### ২.৯ ডেলিভারি এরিয়া (শুধু নাম লিখলেই হবে)

এটি **দুইটি আলাদা জিনিস** — গুলিয়ে ফেলবেন না:

| কোনটি | কোথায় | কাজ |
|---|---|---|
| **ডেলিভারি চেকার** (কাস্টমার টাউন/জিপ লিখে "ডেলিভারি হয় কি না" দেখে) | `delivery_area` metaobject | এটাই আসল চেকার |
| **Delivery Areas পেজের ম্যাপ** | `cm-delivery-areas` → Delivery area ব্লক | শুধু নাম লিখলেই হবে, তবে নতুন নামে পিন বসবে না |
| **ডেলিভারি জোন কার্ড** (দিন, কাট-অফ টাইম, ফি দেখায়) | `delivery_zone` metaobject | তথ্যমূলক কার্ড |

#### চেকার: নাম লিখলেই হবে

**Metaobject type:** `delivery_area` — প্রতিটি টাউনের জন্য একটি এন্ট্রি

| ফিল্ড | লাগবে? | কী দিবেন |
|---|---|---|
| `name` | **হ্যাঁ** | শুধু টাউনের নাম, যেমন `Hartland`। এটুকুই যথেষ্ট |
| `postcodes` | না | জিপ কোড, কমা দিয়ে। জিপ দিয়ে খোঁজা যাবে |
| `is_kitchen` | না | যে টাউনে কিচেন, শুধু সেটিতে `true` |
| `latitude`, `longitude` | না | খালি রাখলে থিম নিজেই খুঁজে নেবে। ভরলে দ্রুততর |
| `map_x`, `map_y` | না | **আর ব্যবহার হয় না** — খালি রাখুন |

**নাম কীভাবে খোঁজা হয়:** থিমটি আপনার **কিচেনের কাছে** খোঁজে, সারা পৃথিবীতে নয়। শুধু `Sussex` লিখলে Sussex, England-এ চলে যেত — কিচেনের কাছে খোঁজার কারণে Sussex, Wisconsin-এ আসে। তবুও ভুল জায়গায় গেলে ওই লাইনে রাজ্য যোগ করুন: `Sussex, WI`।

**কোথায় সিলেক্ট করবেন:** Customizer → প্ল্যান পেজ → Delivery areas → `delivery_area` লিস্ট।

লিস্ট খালি থাকলে থিম ক্রমান্বয়ে খোঁজে: `delivery_area_list` → `delivery_towns` → `plate_towns` → বান্ডল করা Hartland লিস্ট। কোনো ধাপেই কিছু না পেলে আগের ধাপে ফিরে যায়।

#### Delivery Areas পেজের ম্যাপ (আলাদা নিয়ম)

`/pages/delivery-areas` পেজে সেকশনটি `cm-delivery-areas`। এখানে টাউন যোগ করবেন এভাবে:

**Customizer → Delivery Areas পেজ → CM delivery areas → Delivery area ব্লক → Area name** (শুধু নাম, আর কিছু না)

⚠️ **এখানে একটি সীমাবদ্ধতা আছে:** এই পেজের ম্যাপে পিন বসে থিমের ভেতরে বান্ডল করা একটি **স্থির কোঅর্ডিনেট তালিকা** থেকে (২৬টি Wisconsin টাউন)। ওই তালিকায় নেই এমন নতুন নাম দিলে —

- টাউনটি সার্চ লিস্টে দেখাবে ✔
- "হ্যাঁ, ডেলিভারি হয়" উত্তর দেবে ✔
- কিন্তু **ম্যাপে পিন বসবে না** ✘

তালিকায় থাকা টাউনগুলো: Hartland, Delafield, Pewaukee, Waukesha, Sussex, Merton, Nashotah, Okauchee Lake, Oconomowoc, Oconomowoc Lake, Chenequa, Lisbon, Lannon, Menomonee Falls, Brookfield, Elm Grove, Wales, Dousman, Summit, Lake Country, Stone Bank, North Lake, Mapleton, Genesee, Mukwonago।

**নতুন এলাকায় পিন চাইলে** ডেভেলপারকে `assets/cm-da-map.js` ফাইলের `COORDS` তালিকায় ওই টাউনের নাম ও কোঅর্ডিনেট যোগ করতে হবে। শুধু নাম লিখে পিন বসানো এই পেজে সম্ভব নয়।

**প্ল্যান পেজের চেকারে** এই সীমাবদ্ধতা নেই — সেখানে যেকোনো নাম স্বয়ংক্রিয়ভাবে খোঁজা হয়।

#### জোন কার্ড: দিন ও ফি

**Metaobject type:** `delivery_zone` — সেকশন: `delivery-zones`

| ফিল্ড | নির্দেশনা |
|---|---|
| Area name | যেমন: "Hartland" |
| Postcodes | ম্যাচিং এর জন্য |
| Delivery days | যেমন: Sunday, Wednesday |
| Cut-off time | যেমন: "Friday 8 PM" |
| Delivery fee | ফ্রি হলে 0 |
| Minimum order | ঐচ্ছিক |

### ২.১০ Pricing ও Subscription তথ্য

- মূল্য সবসময় **Product/Variant** থেকে আসবে, আলাদা করে টেক্সটে লিখবেন না (দাম বদলালে ভুল দেখাবে)।
- সাবস্ক্রিপশনের সুবিধা লিখতে Customizer-এর "Benefits" ব্লক ব্যবহার করুন (প্রতি ব্লকে ১টি সুবিধা, সর্বোচ্চ ৮০ অক্ষর)।

### ২.১১ Announcement Bar ও Footer

| এরিয়া | কোথায় | নির্দেশনা |
|---|---|---|
| Announcement bar | Customize → Header group → Announcement bar | ১টি বাক্য, সর্বোচ্চ ৮০ অক্ষর |
| Footer links | Customizer → Footer → **Menu** ব্লক, অথবা Footer-এর **Custom links** ব্লক | Menu ব্লকে Content → Menus থেকে মেনু বাছুন |
| Social links | Theme settings → **Social media** | পুরো URL দিন (https://...) |
| ফোন / ইমেইল / ঠিকানা | **Customizer → Footer → Contact info ব্লক** → Phone / Email / Delivery area or address | Theme settings-এ নয় — Footer সেকশনের ভেতরে |

---

## ৩. ছবির সাধারণ নিয়ম

| ব্যবহার | সাইজ | ফরম্যাট |
|---|---|---|
| Hero | ১৯২০×১০৮০ | JPG / WebP |
| প্ল্যান / মিল কার্ড | ৮০০×৮০০ | JPG / WebP |
| আইকন | SVG বা ১২০×১২০ | SVG / PNG |
| প্রোফাইল ফটো | ২০০×২০০ | JPG |
| Thali প্লেট | বর্গাকার (১:১) | WebP / PNG (স্বচ্ছ ব্যাকগ্রাউন্ড ভালো) |

- প্রতিটি ছবিতে **Alt text** দিন (যেমন: "গ্রিলড চিকেন ও ব্রকলি মিল বক্স")।
- খাবারের ছবির আলো ও ব্যাকগ্রাউন্ড একই ধরনের রাখুন।

## ৪. প্রকাশের আগে চেকলিস্ট

- [ ] সব Metaobject এন্ট্রি **Active**
- [ ] প্রতিটি সেকশনে সঠিক Content source সিলেক্ট করা
- [ ] সব প্ল্যান ও মিলের নিউট্রিশন এবং অ্যালার্জেন তথ্য যাচাই করা
- [ ] Thali প্লেটে ঠিক ৪টি লেবেল আছে
- [ ] মোবাইল প্রিভিউতে প্রতিটি পেজ দেখা
- [ ] সব বাটনের লিংক টেস্ট করা
- [ ] ডেলিভারি চেকারে নিজের এলাকার নাম লিখে দেখুন — "হ্যাঁ" আসছে কি না
- [ ] ডেলিভারি জোন কার্ডে দিন ও কাট-অফ টাইম সঠিক
- [ ] সব ছবিতে Alt text আছে

## ৫. সাধারণ সমস্যা ও সমাধান

| সমস্যা | কারণ | সমাধান |
|---|---|---|
| সেকশনে কনটেন্ট আসছে না | Metaobject এন্ট্রি Draft অবস্থায় | স্ট্যাটাস Active করুন |
| ভুল ক্রমে দেখাচ্ছে | Sort order নেই | Sort order ফিল্ডে সংখ্যা দিন |
| ছবি কেটে যাচ্ছে | ভুল অনুপাত | নির্দেশিত সাইজে আপলোড করুন |
| Metaobject লিস্ট সিলেক্ট করা যাচ্ছে না | Definition-এর type নাম মেলেনি | উপরের type নাম হুবহু ব্যবহার করুন |
| পুরোনো কনটেন্ট দেখাচ্ছে | ব্রাউজার ক্যাশ | হার্ড রিফ্রেশ করুন |
| Thali প্লেটে ৩টি ট্যাগ | লেখা মাত্র ৩ লাইন | ৪র্থ লাইন যোগ করুন |
| প্ল্যান পেজে সব কনটেন্ট একসাথে হারিয়ে গেছে | Product picker-এ ভুল | **CM meal plan page**-এ প্রোডাক্ট আবার বাছুন (হ্যান্ডেল টাইপ করবেন না) |
| হিরোতে ক্লিক করলে ডান সাইডবার বদলায় না | পুরনো টেমপ্লেট / ক্যাশ | হার্ড রিফ্রেশ; বামে **MP Hero** ক্লিক করুন; `PLAN-PRODUCT-CONTENT.md` §০ |
| দুইবার Hero দেখাচ্ছে | Built-in hero চালু + MP Hero আছে | CM meal plan page → Show built-in hero **বন্ধ** |
| টাউন ভুল জায়গায় পিন হচ্ছে | নাম একাধিক জায়গায় আছে | ওই লাইনে রাজ্য যোগ করুন, যেমন `Sussex, WI` |
| Delivery Areas পেজে নতুন টাউনে পিন বসছে না | পিন আসে `cm-da-map.js`-এর স্থির তালিকা থেকে | ডেভেলপারকে `COORDS` তালিকায় নাম যোগ করতে বলুন |
| সব মিল একই নিউট্রিশন দেখাচ্ছে | মান Product-এ দেওয়া হয়েছে, Variant-এ নয় | Variant metafield-এ সরান |
| ডেলিভারি চেকার দেখাচ্ছে না | `delivery_style` বা `delivery_checker` বন্ধ | প্ল্যান পেজ সেকশনে Delivery style ঠিক করুন |
