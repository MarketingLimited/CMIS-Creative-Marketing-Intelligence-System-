<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- تكييف الرسائل والإعلانات للسوق والقنوات مع احترام **RTL** والخصوصيات المحلية لمملكة البحرين، وتوليد أصول قابلة للنشر فورًا مع حدود طول دقيقة، مواصفات بصرية/سمعية، وتسمية تصديرية موحّدة.
<!-- CMIS:END::PURPOSE -->

<!-- CMIS:START::INPUTS -->
## المدخلات (JSON)
```json
{
  "brand": "",
  "product_or_service": "",
  "objective": "awareness|sales|leads",
  "target_audience": "",
  "channels": [],
  "budget_bhd": "",
  "trend_research": {
    "topic": "",
    "language": "ar",
    "depth": "summary|detailed"
  }
}
```

### المدخلات الأصلية (منسوخة حرفيًا)
```json
{
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL", "seasons": ["رمضان","العيد","اليوم الوطني 16–17 ديسمبر","التخفيضات","العودة للمدارس"] },
  "voice": "ثابت للعلامة",
  "tone": "ودية|رسمية|ملهمة|مقنعة|تعليمية|جريئة|مهني متوازن",
  "framework_output": [
    {
      "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing|UGC|WhatsApp|Radio|OOH|AppStore",
      "framework": "AIDA|PAS|FAB|4U|4C|PASTOR|StoryBrand|Hybrid",
      "awareness_stage": "unaware|problem|solution|product|most",
      "copy": { "short": "", "long": "", "hook": "", "cta": "", "proof": [] }
    }
  ],
  "max_variations_per_channel": 3,
  "numbers_locale": "ar",
  "disclosure_hashtag": "#إعلان"
}
```
<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب.
2. إن وُجد `trend_research` فعّل آلية البحث وادمج الملخص والمصدر في المخرجات.
3. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات…).
4. إنتاج المخرجات وفق القالب أدناه.

### المحتوى الأصلي الكامل (منسوخ حرفيًا)
## **افتراضات التوطين — البحرين (افتراضي)**

```
localization:
  market: "Bahrain"
  currency: "BHD"
  language: "AR"
  direction: "RTL"
  seasons: ["رمضان", "العيد", "اليوم الوطني 16–17 ديسمبر", "مواسم التخفيضات", "العودة للمدارس"]
  hashtags_default: ["#البحرين", "#تسويق", "#إعلان"]
  style_hints:
    phrasing: ["قبل الدوام", "بعد الفطور", "نهاية الأسبوع"]
    numerals: "ar"
    disclosure: "#إعلان" # يظهر في البداية للمواد المرعية
```

---

## **حواجز الحراسة (Guardrails)**

* Voice ثابت؛ Tone متغيرة حسب القناة/المرحلة.

* لا CTA شرائي لجمهور بارد؛ استخدم CTA تجريبي/استكشافي.

* لا مطلقات: «مضمون/فوري/الأفضل».

* زر/CTA واحد لكل أصل.

* التزام `#إعلان` في بداية المواد المرعية.

* احترام حدود الطول والقوالب أدناه حرفيًا.

---

## **حدود الطول حسب القناة**

```
limits:
  Meta:
    primary_text_lines: 4
    headline_chars: 40
    description_chars: 90
  TikTok:
    video_seconds: [6,12]
    on_screen_words_max: 8
    scenes_max: 4
  Google_RSA:
    headlines: [10,20]
    headline_chars: 30
    descriptions: [5,10]
    description_chars: 90
  LinkedIn:
    paragraphs: [2,4]
    data_line: true
  Email:
    subject_chars: 50
    preheader_chars: 80
  Landing:
    h1_chars: 70
    subhead_chars: 140
    sections_max: 8
  WhatsApp_SMS:
    total_chars: 100
  Radio_Podcast:
    seconds: [15,30]
  OOH:
    words_max: 5
  AppStore:
    short_desc_chars: 80
    full_desc_chars: 4000
```

---

## **مواصفات بصرية/سمعية (RTL/LTR-aware)**

```
visual_audio_specs:
  direction: "RTL"
  palette: ["#0F172A", "#16A34A", "#2563EB", "#F59E0B"] # قابلة للتبديل بهوية العلامة
  fonts_ar: ["IBM Plex Arabic", "Cairo", "Tajawal"]
  iconography: "بسيطة، دلالات محلية عند اللزوم"
  photography: "تمثيل معاصر، احترام الخصوصية"
  contrast_ratio_min: 4.5
  focal_point: "عنصر بصري مهيمن واحد"
  motion: "انتقالات ناعمة ≤ 300ms"
```

---

## **قناة: Meta (Facebook/Instagram)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Meta",
  "placement": "Feed|Story|Reel|Carousel",
  "tone": "",
  "awareness_stage": "",
  "assets": {
    "primary_text": "≤4 أسطر، السطر الأول Hook",
    "headline": "",
    "description": "",
    "media": {
      "type": "image|video|carousel",
      "ratio": "1:1|4:5|9:16",
      "overlay_text": "≤8 كلمات",
      "visual_idea": ""
    }
  },
  "cta": "جرّب الآن|اطّلع على الخطط|احجز ديمو",
  "disclosure": "#إعلان",
  "length_check": "auto",
  "naming": "Ad_v{n}_Meta_{Placement}_{Len}_{HookID}"
}
```

### **تنويعات سريعة (≤3)**

* v1: PAS (Problem/Agitation/Solution) — CTA تجريبي.

* v2: AIDA (Hook رقمي/نتيجة) — CTA استكشافي.

* v3 (اختياري Conversion): PAS→AIDA — CTA تسعير/Demo.

---

## **قناة: TikTok/Reels**

### **سكربت قصير (6–12 ثانية)**

```json
{
  "channel": "TikTok",
  "tone": "مرحة|حوارية",
  "script": {
    "S1_hook_0_2": { "on_screen": "≤8 كلمات", "vo": "", "visual": "" },
    "S2_problem_2_5": { "on_screen": "", "vo": "", "visual": "" },
    "S3_solution_proof_5_9": { "on_screen": "", "vo": "", "visual": "" },
    "S4_cta_9_12": { "on_screen": "CTA مختصر", "vo": "", "visual": "" }
  },
  "music": "محايد/محلي غير طاغٍ",
  "captions": "سطران كحد أقصى (RTL)",
  "disclosure": "#إعلان",
  "naming": "Ad_v{n}_TikTok_{HookID}"
}
```

---

## **قناة: Google Search (Responsive Search Ads)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Google_RSA",
  "tone": "مباشرة",
  "headlines_≤30": [
    "{{result}} خلال {{time}}",
    "خطة تبدأ من {{price}} BHD",
    "{{feature}} → {{benefit}}"
  ],
  "descriptions_≤90": [
    "اختبر 2–3 زوايا اليوم — إعداد 3 دقائق.",
    "ضمان 14 يومًا، تقييم {{rating}}/5 (آخر 90 يومًا)."
  ],
  "path": "category/bahrain",
  "assets": { "sitelinks": [], "callouts": [], "price_extension": true },
  "naming": "Ad_v{n}_Google_RSA_{Intent}"
}
```

---

## **قناة: LinkedIn (Sponsored Post/Lead Gen)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "LinkedIn",
  "tone": "مهني متوازن",
  "framework": "PASTOR|StoryBrand",
  "post": {
    "paragraphs": [
      "سطر استراتيجي بالأرقام/الأثر.",
      "كيف يعمل الحل مختصرًا.",
      "دليل مختصر (رقم/شعار/شهادة)."
    ],
    "data_line": "رقم/نطاق زمني موثّق أو [افتراض]",
    "cta": "احجز ديمو قصير (15 دقيقة)"
  },
  "lead_gen_form": {
    "headline": "CTA + قيمة",
    "fields": ["الاسم","البريد","الهاتف","الشركة"],
    "consent": "صياغة موافقة واضحة (Bahrain)"
  },
  "naming": "Ad_v{n}_LinkedIn_{Objective}"
}
```

---

## **قناة: Email**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Email",
  "tone": "تعليمي|مقنع",
  "subject_≤50": "",
  "preheader_≤80": "",
  "body": {
    "opening_≤25w": "",
    "value": "{{usp}} + {{proof_snippet}}",
    "bullets": ["ميزة → منفعة → دليل", "ميزة → منفعة → دليل"],
    "cta_button": "واحد فقط"
  },
  "footer": {
    "disclosure": "#إعلان عند اللزوم",
    "unsubscribe": "صياغة إلغاء الاشتراك المتوافقة"
  },
  "naming": "Email_v{n}_{Goal}"
}
```

---

## **قناة: Landing Page**

### **بنية مقترحة**

```
landing:
  h1: "وعد واضح بالنتيجة"
  subhead: "سطر داعم يحدد لمن ولماذا الآن"
  sections:
    - value_proposition: ["فوائد مختصرة", "USP (نتيجة+زمن+قيد)"]
    - proof_layers: ["تقييمات", "أرقام موثقة", "دراسة حالة بحرينية"]
    - plan_pricing: ["خطط بالـBHD", "تفاصيل شفافة"]
    - faq: ["3–5 أسئلة شائعة"]
  cta_primary: "ابدأ مجانًا / احجز ديمو"
  compliance: ["#إعلان إذا لزم", "خصوصية البحرين"]
  naming: "LP_v{n}_{OfferID}"
```

---

## **قناة: UGC Ads**

```json
{
  "channel": "UGC",
  "tone": "شخصي وغير مصقول",
  "script": {
    "intro": "كنت متردد…",
    "experience": "بعد أسبوع…",
    "result": "وفّر عليّ…",
    "cta": "نسخة تجريبية الآن"
  },
  "disclosure": "#إعلان",
  "naming": "UGC_v{n}_{Persona}"
}
```

---

## **قناة: WhatsApp / SMS**

```json
{
  "channel": "WhatsApp_SMS",
  "text_≤100": "رسالة قصيرة جدًا مع قيمة + CTA + رابط قصير",
  "naming": "WA_v{n}_{OfferID}"
}
```

---

## **قناة: Radio/Podcast**

```json
{
  "channel": "Radio_Podcast",
  "duration": "15|30",
  "script": {
    "hook": "",
    "value": "",
    "proof": "",
    "cta": ""
  },
  "naming": "Audio_v{n}_{Duration}"
}
```

---

## **قناة: OOH/Print**

```json
{
  "channel": "OOH",
  "headline_≤5_words": "",
  "subline": "",
  "visual_idea": "",
  "cta_short": "",
  "naming": "OOH_v{n}_{Location}"
}
```

---

## **قناة: App Store (إن وُجد منتج تطبيقي)**

```json
{
  "channel": "AppStore",
  "short_desc_≤80": "",
  "full_desc_≤4000": "",
  "keywords": [],
  "screenshots_notes": ["ترتيب بصري 1→2→3", "تعريب كامل", "RTL عند اللزوم"],
  "naming": "ASO_v{n}_{Locale}"
}
```

---

## **حالات استخدام عملية للقنوات الرئيسية (بحرين 2025)**

| القناة | الأبعاد/النسبة الموصى بها | مثال نصي متوافق (AR/RTL، BHD، #إعلان) | ملاحظات تشغيلية |
| --- | --- | --- | --- |
| Meta Feed (صورة) | ‎1080×1350‎ (4:5) | «#إعلان هل ما زالت نسخك تأخذ ساعات؟ خلال أسبوع العروض في سيتي سنتر، CMIS حضّر ٨ نسخ وخفّض الـCPA إلى ‎14.8‎ BHD خلال ٧ أيام. ابدأ التجربة المجانية الآن.» | استخدم CTA زر «ابدأ»؛ أضف Overlay ≤ 8 كلمات؛ فيديو بديل ‎1080×1920‎ (9:16) للـReels مع نفس النص الافتتاحي. |
| Google_RSA | عناوين ≤ ‎30‎ حرفًا، أوصاف ≤ ‎90‎، صور إضافية ‎1200×1200‎ | عناوين: «#إعلان نسخ جاهزة خلال ١٠ دقائق»، «خطة تبدأ من ‎49‎ BHD». أوصاف: «اختبر ٣ زوايا اليوم — دعم بحريني 24/7.» | استخدم مسار `copy/bahrain`; تأكد من تطابق صفحة الهبوط وذكر الأسعار بالـBHD. |
| TikTok 9:16 فيديو | ‎1080×1920‎، 6–12 ثانية | Overlay: «#إعلان ٣ دقائق تكفي؟». VO: «من المنامة جرّبنا CMIS، وطلع معنا ٣ سيناريوهات خلال ١٠ دقائق، وخلال أسبوع نزل الـCPA ٢٢٪.» CTA على الشاشة: «اشترك بخطة مرنة بالـBHD». | موسيقى إيقاع خفيف خليجي، نصوص RTL، تأكد من الإفصاح صوتيًا خلال أول 3 ثوانٍ. |
| LinkedIn Sponsored Content | صورة ‎1200×1200‎ أو ‎1200×627‎، نص 3 فقرات | «#إعلان فرق الأداء في البحرين التي اعتمدت CMIS بالربع الأخير 2024 خفّضت كلفة العميل حتى ٢٢٪. ٣ خطوات واضحة، دعم بالعربية، خطط تبدأ من ‎49‎ BHD. احجز ديمو قصير (١٥ دقيقة).» | أضف سطر بيانات يحتوي نطاق الأداء وتاريخ 2024/2025؛ التزم بنبرة مهنية. |
| Email (نشرة/حملة) | عرض تصميم 600px، صور ‎1200×800‎ مضغوطة | Subject: «#إعلان نسخ رمضانية جاهزة خلال ١٠ دقائق». Body: «مرحبًا {{الاسم}}، في البحرين وفرّنا ٦٠٪ من وقت الكتابة خلال موسم رمضان 2024. الخطط تبدأ من ‎49‎ BHD مع ضمان 14 يومًا.» CTA زر: «ابدأ الآن». | أضف تذييل امتثال وقائمة إلغاء الاشتراك؛ تنسيق الأرقام عربي (`١٠`). |
| WhatsApp_SMS | نص ≤ ‎100‎ حرفًا | «#إعلان CMIS جهّز ٣ زوايا خلال ١٠ دقايق. جرّبه مجانًا اليوم، الخطة من ‎49‎ BHD: cmis.bh/demo» | استخدم رابط مختصر .bh؛ تجنب الرموز التعبيرية المكررة؛ أرسل ضمن أوقات العمل المحلية. |
| OOH لوحة طريق | ‎6×3‎ م (دقة تصميم ‎14400×7200‎) | «#إعلان نسخك الجاهزة خلال ١٠ دقائق. خطط تبدأ من ‎49‎ BHD. CMIS البحرين.» | نص ≤ 5 كلمات أساسية، شعار واضح يمين اللوحة، استخدم خط «Cairo» عريض مع تباين ≥4.5. |
| Landing Page | عرض تصميم ‎1440‎ px، Above-the-fold ‎960‎ px، صور hero ‎1920×1080‎ | H1: «#إعلان حضّر ٨ نسخ بالعربية خلال ١٠ دقائق». Subhead: «خطة تبدأ من ‎49‎ BHD، ضمان ١٤ يومًا، دعم بحريني مباشر». CTA: «ابدأ التجربة المجانية الآن». | أضف جدول أسعار بالـBHD، تضمين تقييم 4.7/5 (آخر 90 يومًا)، وضع الإفصاح في مقدمة المحتوى الإعلاني. |

---

## **توليد الحِزم (Bundles)**

```
bundle:
  meta: ["Feed_v1","Story_v2","Reel_v3"]
  tiktok: ["Script_v1","Script_v2"]
  google: ["RSA_v1","RSA_v2"]
  linkedin: ["Post_v1","LeadGen_v2"]
  email: ["Newsletter_v1","Drip_v2"]
  landing: ["LP_v1"]
  naming: "Bundle_{Market}_{Objective}_{Date}"
```

---

## **التحقق الآلي (Validators)**

```
validators:
  check_length: true
  check_rtl: true
  check_disclosure: "#إعلان في البداية"
  check_guardrails: ["CTA واحد", "لا شراء للبارد", "لا مطلقات"]
  output: "pass|fail + سبب عند الفشل"
```

---

## **ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **قنوات مفعّلة وتنوّعات:** …

* **التزام الحدود/الحواجز/الإفصاح:** …

* **الأصول المولّدة للتسليم:** قائمة أسماء وفق التسمية المعيارية.

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

## **افتراضات التوطين — البحرين (افتراضي)**

```
localization:
  market: "Bahrain"
  currency: "BHD"
  language: "AR"
  direction: "RTL"
  seasons: ["رمضان", "العيد", "اليوم الوطني 16–17 ديسمبر", "مواسم التخفيضات", "العودة للمدارس"]
  hashtags_default: ["#البحرين", "#تسويق", "#إعلان"]
  style_hints:
    phrasing: ["قبل الدوام", "بعد الفطور", "نهاية الأسبوع"]
    numerals: "ar"
    disclosure: "#إعلان" # يظهر في البداية للمواد المرعية
```

---

## **حواجز الحراسة (Guardrails)**

* Voice ثابت؛ Tone متغيرة حسب القناة/المرحلة.

* لا CTA شرائي لجمهور بارد؛ استخدم CTA تجريبي/استكشافي.

* لا مطلقات: «مضمون/فوري/الأفضل».

* زر/CTA واحد لكل أصل.

* التزام `#إعلان` في بداية المواد المرعية.

* احترام حدود الطول والقوالب أدناه حرفيًا.

---

## **حدود الطول حسب القناة**

```
limits:
  Meta:
    primary_text_lines: 4
    headline_chars: 40
    description_chars: 90
  TikTok:
    video_seconds: [6,12]
    on_screen_words_max: 8
    scenes_max: 4
  Google_RSA:
    headlines: [10,20]
    headline_chars: 30
    descriptions: [5,10]
    description_chars: 90
  LinkedIn:
    paragraphs: [2,4]
    data_line: true
  Email:
    subject_chars: 50
    preheader_chars: 80
  Landing:
    h1_chars: 70
    subhead_chars: 140
    sections_max: 8
  WhatsApp_SMS:
    total_chars: 100
  Radio_Podcast:
    seconds: [15,30]
  OOH:
    words_max: 5
  AppStore:
    short_desc_chars: 80
    full_desc_chars: 4000
```

---

## **مواصفات بصرية/سمعية (RTL/LTR-aware)**

```
visual_audio_specs:
  direction: "RTL"
  palette: ["#0F172A", "#16A34A", "#2563EB", "#F59E0B"] # قابلة للتبديل بهوية العلامة
  fonts_ar: ["IBM Plex Arabic", "Cairo", "Tajawal"]
  iconography: "بسيطة، دلالات محلية عند اللزوم"
  photography: "تمثيل معاصر، احترام الخصوصية"
  contrast_ratio_min: 4.5
  focal_point: "عنصر بصري مهيمن واحد"
  motion: "انتقالات ناعمة ≤ 300ms"
```

---

## **قناة: Meta (Facebook/Instagram)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Meta",
  "placement": "Feed|Story|Reel|Carousel",
  "tone": "",
  "awareness_stage": "",
  "assets": {
    "primary_text": "≤4 أسطر، السطر الأول Hook",
    "headline": "",
    "description": "",
    "media": {
      "type": "image|video|carousel",
      "ratio": "1:1|4:5|9:16",
      "overlay_text": "≤8 كلمات",
      "visual_idea": ""
    }
  },
  "cta": "جرّب الآن|اطّلع على الخطط|احجز ديمو",
  "disclosure": "#إعلان",
  "length_check": "auto",
  "naming": "Ad_v{n}_Meta_{Placement}_{Len}_{HookID}"
}
```

### **تنويعات سريعة (≤3)**

* v1: PAS (Problem/Agitation/Solution) — CTA تجريبي.

* v2: AIDA (Hook رقمي/نتيجة) — CTA استكشافي.

* v3 (اختياري Conversion): PAS→AIDA — CTA تسعير/Demo.

---

## **قناة: TikTok/Reels**

### **سكربت قصير (6–12 ثانية)**

```json
{
  "channel": "TikTok",
  "tone": "مرحة|حوارية",
  "script": {
    "S1_hook_0_2": { "on_screen": "≤8 كلمات", "vo": "", "visual": "" },
    "S2_problem_2_5": { "on_screen": "", "vo": "", "visual": "" },
    "S3_solution_proof_5_9": { "on_screen": "", "vo": "", "visual": "" },
    "S4_cta_9_12": { "on_screen": "CTA مختصر", "vo": "", "visual": "" }
  },
  "music": "محايد/محلي غير طاغٍ",
  "captions": "سطران كحد أقصى (RTL)",
  "disclosure": "#إعلان",
  "naming": "Ad_v{n}_TikTok_{HookID}"
}
```

---

## **قناة: Google Search (Responsive Search Ads)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Google_RSA",
  "tone": "مباشرة",
  "headlines_≤30": [
    "{{result}} خلال {{time}}",
    "خطة تبدأ من {{price}} BHD",
    "{{feature}} → {{benefit}}"
  ],
  "descriptions_≤90": [
    "اختبر 2–3 زوايا اليوم — إعداد 3 دقائق.",
    "ضمان 14 يومًا، تقييم {{rating}}/5 (آخر 90 يومًا)."
  ],
  "path": "category/bahrain",
  "assets": { "sitelinks": [], "callouts": [], "price_extension": true },
  "naming": "Ad_v{n}_Google_RSA_{Intent}"
}
```

---

## **قناة: LinkedIn (Sponsored Post/Lead Gen)**

### **قالب إخراج (JSON)**

```json
{
  "channel": "LinkedIn",
  "tone": "مهني متوازن",
  "framework": "PASTOR|StoryBrand",
  "post": {
    "paragraphs": [
      "سطر استراتيجي بالأرقام/الأثر.",
      "كيف يعمل الحل مختصرًا.",
      "دليل مختصر (رقم/شعار/شهادة)."
    ],
    "data_line": "رقم/نطاق زمني موثّق أو [افتراض]",
    "cta": "احجز ديمو قصير (15 دقيقة)"
  },
  "lead_gen_form": {
    "headline": "CTA + قيمة",
    "fields": ["الاسم","البريد","الهاتف","الشركة"],
    "consent": "صياغة موافقة واضحة (Bahrain)"
  },
  "naming": "Ad_v{n}_LinkedIn_{Objective}"
}
```

---

## **قناة: Email**

### **قالب إخراج (JSON)**

```json
{
  "channel": "Email",
  "tone": "تعليمي|مقنع",
  "subject_≤50": "",
  "preheader_≤80": "",
  "body": {
    "opening_≤25w": "",
    "value": "{{usp}} + {{proof_snippet}}",
    "bullets": ["ميزة → منفعة → دليل", "ميزة → منفعة → دليل"],
    "cta_button": "واحد فقط"
  },
  "footer": {
    "disclosure": "#إعلان عند اللزوم",
    "unsubscribe": "صياغة إلغاء الاشتراك المتوافقة"
  },
  "naming": "Email_v{n}_{Goal}"
}
```

---

## **قناة: Landing Page**

### **بنية مقترحة**

```
landing:
  h1: "وعد واضح بالنتيجة"
  subhead: "سطر داعم يحدد لمن ولماذا الآن"
  sections:
    - value_proposition: ["فوائد مختصرة", "USP (نتيجة+زمن+قيد)"]
    - proof_layers: ["تقييمات", "أرقام موثقة", "دراسة حالة بحرينية"]
    - plan_pricing: ["خطط بالـBHD", "تفاصيل شفافة"]
    - faq: ["3–5 أسئلة شائعة"]
  cta_primary: "ابدأ مجانًا / احجز ديمو"
  compliance: ["#إعلان إذا لزم", "خصوصية البحرين"]
  naming: "LP_v{n}_{OfferID}"
```

---

## **قناة: UGC Ads**

```json
{
  "channel": "UGC",
  "tone": "شخصي وغير مصقول",
  "script": {
    "intro": "كنت متردد…",
    "experience": "بعد أسبوع…",
    "result": "وفّر عليّ…",
    "cta": "نسخة تجريبية الآن"
  },
  "disclosure": "#إعلان",
  "naming": "UGC_v{n}_{Persona}"
}
```

---

## **قناة: WhatsApp / SMS**

```json
{
  "channel": "WhatsApp_SMS",
  "text_≤100": "رسالة قصيرة جدًا مع قيمة + CTA + رابط قصير",
  "naming": "WA_v{n}_{OfferID}"
}
```

---

## **قناة: Radio/Podcast**

```json
{
  "channel": "Radio_Podcast",
  "duration": "15|30",
  "script": {
    "hook": "",
    "value": "",
    "proof": "",
    "cta": ""
  },
  "naming": "Audio_v{n}_{Duration}"
}
```

---

## **قناة: OOH/Print**

```json
{
  "channel": "OOH",
  "headline_≤5_words": "",
  "subline": "",
  "visual_idea": "",
  "cta_short": "",
  "naming": "OOH_v{n}_{Location}"
}
```

---

## **قناة: App Store (إن وُجد منتج تطبيقي)**

```json
{
  "channel": "AppStore",
  "short_desc_≤80": "",
  "full_desc_≤4000": "",
  "keywords": [],
  "screenshots_notes": ["ترتيب بصري 1→2→3", "تعريب كامل", "RTL عند اللزوم"],
  "naming": "ASO_v{n}_{Locale}"
}
```

---

## **حالات استخدام عملية للقنوات الرئيسية (بحرين 2025)**

| القناة | الأبعاد/النسبة الموصى بها | مثال نصي متوافق (AR/RTL، BHD، #إعلان) | ملاحظات تشغيلية |
| --- | --- | --- | --- |
| Meta Feed (صورة) | ‎1080×1350‎ (4:5) | «#إعلان هل ما زالت نسخك تأخذ ساعات؟ خلال أسبوع العروض في سيتي سنتر، CMIS حضّر ٨ نسخ وخفّض الـCPA إلى ‎14.8‎ BHD خلال ٧ أيام. ابدأ التجربة المجانية الآن.» | استخدم CTA زر «ابدأ»؛ أضف Overlay ≤ 8 كلمات؛ فيديو بديل ‎1080×1920‎ (9:16) للـReels مع نفس النص الافتتاحي. |
| Google_RSA | عناوين ≤ ‎30‎ حرفًا، أوصاف ≤ ‎90‎، صور إضافية ‎1200×1200‎ | عناوين: «#إعلان نسخ جاهزة خلال ١٠ دقائق»، «خطة تبدأ من ‎49‎ BHD». أوصاف: «اختبر ٣ زوايا اليوم — دعم بحريني 24/7.» | استخدم مسار `copy/bahrain`; تأكد من تطابق صفحة الهبوط وذكر الأسعار بالـBHD. |
| TikTok 9:16 فيديو | ‎1080×1920‎، 6–12 ثانية | Overlay: «#إعلان ٣ دقائق تكفي؟». VO: «من المنامة جرّبنا CMIS، وطلع معنا ٣ سيناريوهات خلال ١٠ دقائق، وخلال أسبوع نزل الـCPA ٢٢٪.» CTA على الشاشة: «اشترك بخطة مرنة بالـBHD». | موسيقى إيقاع خفيف خليجي، نصوص RTL، تأكد من الإفصاح صوتيًا خلال أول 3 ثوانٍ. |
| LinkedIn Sponsored Content | صورة ‎1200×1200‎ أو ‎1200×627‎، نص 3 فقرات | «#إعلان فرق الأداء في البحرين التي اعتمدت CMIS بالربع الأخير 2024 خفّضت كلفة العميل حتى ٢٢٪. ٣ خطوات واضحة، دعم بالعربية، خطط تبدأ من ‎49‎ BHD. احجز ديمو قصير (١٥ دقيقة).» | أضف سطر بيانات يحتوي نطاق الأداء وتاريخ 2024/2025؛ التزم بنبرة مهنية. |
| Email (نشرة/حملة) | عرض تصميم 600px، صور ‎1200×800‎ مضغوطة | Subject: «#إعلان نسخ رمضانية جاهزة خلال ١٠ دقائق». Body: «مرحبًا {{الاسم}}، في البحرين وفرّنا ٦٠٪ من وقت الكتابة خلال موسم رمضان 2024. الخطط تبدأ من ‎49‎ BHD مع ضمان 14 يومًا.» CTA زر: «ابدأ الآن». | أضف تذييل امتثال وقائمة إلغاء الاشتراك؛ تنسيق الأرقام عربي (`١٠`). |
| WhatsApp_SMS | نص ≤ ‎100‎ حرفًا | «#إعلان CMIS جهّز ٣ زوايا خلال ١٠ دقايق. جرّبه مجانًا اليوم، الخطة من ‎49‎ BHD: cmis.bh/demo» | استخدم رابط مختصر .bh؛ تجنب الرموز التعبيرية المكررة؛ أرسل ضمن أوقات العمل المحلية. |
| OOH لوحة طريق | ‎6×3‎ م (دقة تصميم ‎14400×7200‎) | «#إعلان نسخك الجاهزة خلال ١٠ دقائق. خطط تبدأ من ‎49‎ BHD. CMIS البحرين.» | نص ≤ 5 كلمات أساسية، شعار واضح يمين اللوحة، استخدم خط «Cairo» عريض مع تباين ≥4.5. |
| Landing Page | عرض تصميم ‎1440‎ px، Above-the-fold ‎960‎ px، صور hero ‎1920×1080‎ | H1: «#إعلان حضّر ٨ نسخ بالعربية خلال ١٠ دقائق». Subhead: «خطة تبدأ من ‎49‎ BHD، ضمان ١٤ يومًا، دعم بحريني مباشر». CTA: «ابدأ التجربة المجانية الآن». | أضف جدول أسعار بالـBHD، تضمين تقييم 4.7/5 (آخر 90 يومًا)، وضع الإفصاح في مقدمة المحتوى الإعلاني. |

---

## **توليد الحِزم (Bundles)**

```
bundle:
  meta: ["Feed_v1","Story_v2","Reel_v3"]
  tiktok: ["Script_v1","Script_v2"]
  google: ["RSA_v1","RSA_v2"]
  linkedin: ["Post_v1","LeadGen_v2"]
  email: ["Newsletter_v1","Drip_v2"]
  landing: ["LP_v1"]
  naming: "Bundle_{Market}_{Objective}_{Date}"
```

---

## **التحقق الآلي (Validators)**

```
validators:
  check_length: true
  check_rtl: true
  check_disclosure: "#إعلان في البداية"
  check_guardrails: ["CTA واحد", "لا شراء للبارد", "لا مطلقات"]
  output: "pass|fail + سبب عند الفشل"
```

---

## **ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **قنوات مفعّلة وتنوّعات:** …

* **التزام الحدود/الحواجز/الإفصاح:** …

* **الأصول المولّدة للتسليم:** قائمة أسماء وفق التسمية المعيارية.

<!-- CMIS:END::EXAMPLES -->

<!-- CMIS:START::OUTPUT -->

## المخرجات (JSON)

```json
{
  "deliverable": "strategy_pack|ads|video_scenario|content_plan|report",
  "content": {},
  "compliance_report": {
    "ad_disclosure": "present|missing",
    "currency": "BHD",
    "claims": "no absolutes",
    "rtl": true,
    "cta_single": true
  },
  "sources": ["[مصدر: Deloitte]", "[مصدر: Firework]"]
}
```

<!-- CMIS:END::OUTPUT -->

<!-- CMIS:START::STATUS -->

## ملخص حالة (3 أسطر)

* ما الذي أُنجز؟
* أي افتراضات؟
* ملاحظات الامتثال؟

<!-- CMIS:END::STATUS -->
