# **07\_output.md**

## **الغرض**

إخراج النتائج النهائية بصيغ منظّمة وجاهزة للعرض/النسخ/التصدير، مع قوالب تقارير ومخططات JSON، وتسميات تصديرية موحّدة. سوق افتراضي: **مملكة البحرين** (AR/RTL، عملة **BHD**).

---

## **مدخلات الوحدة**

```json
{
  "config": {
    "mode": "quick_draft|full_strategy",
    "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" },
    "numbers_locale": "ar",
    "disclosure_hashtag": "#إعلان"
  },
  "strategy_core": {
    "customer_language": { "pains": [], "desires": [], "objections": [], "drivers": [] },
    "jtbd": "",
    "personas": { "primary": "", "alt": "" },
    "usp": "",
    "awareness_messages": {},
    "offer": { "core_value": "", "scarcity": "", "guarantee": "", "proof": [] }
  },
  "framework_output": [
    {
      "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing|UGC|WhatsApp_SMS|Radio_Podcast|OOH|AppStore",
      "framework": "AIDA|PAS|FAB|4U|4C|PASTOR|StoryBrand|Hybrid",
      "awareness_stage": "unaware|problem|solution|product|most",
      "tone": "",
      "copy": { "short": "", "long": "", "hook": "", "cta": "", "proof": [] },
      "compliance": "✅|⚠️|🚫"
    }
  ],
  "dco": { "candidates": [], "experiment": {}, "report": {} },
  "compliance_reports": []
}
```

---

## **أقسام الإخراج الأساسية**

### **(أ) خلاصة استراتيجية (فقرتان)**

```
strategy_summary:
  audience: "من المستهدف ولماذا الآن (بحرين)"
  core_message: "رسالة محورية + USP (نتيجة + زمن + قيد)"
  offer: "العرض + الندرة + الضمان + أدلة"
  channels_why: "القنوات الموصى بها ولماذا"
  market: "Bahrain | BHD | RTL | مواسم ذات صلة"
```

### **(ب) الإعلانات النهائية حسب القناة**

* لكل قناة: **نسختان افتراضًا** \+ **هجينة اختيارية** (عند الحاجة Conversion/Product/Most-Aware).

* لكل نسخة: **Short ≤ 50 كلمة**، **Long ≤ 120 كلمة**، **Hook**، **CTA واحد**، **Proof**، **Metric أساسي**، **وسم امتثال**.

**قالب عنصر إعلان**

```json
{
  "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing|UGC|WhatsApp_SMS|Radio_Podcast|OOH|AppStore",
  "awareness_stage": "unaware|problem|solution|product|most",
  "framework": "AIDA|PAS|FAB|4U|4C|PASTOR|StoryBrand|Hybrid",
  "variant_id": "v1|v2|hybrid",
  "tone": "…",
  "copy": {
    "hook": "",
    "short": "",
    "long": "",
    "cta": "",
    "proof": []
  },
  "primary_metric": "CTR|CVR|ROAS|HookRate",
  "naming": "Ad_v{n}_{Channel}_{Len}_{HookID}",
  "compliance": "✅|⚠️|🚫",
  "notes": "لماذا هذا الإطار/هذه النبرة لهذه المرحلة"
}
```

### **(ج) توصيات التحسين المستقبلية**

```
improvement_recommendations:
  repeat:  ["زاوية/نبرة/قناة ناجحة"]
  refine:  ["عنصر يحتاج ضبط (CTA/ضمان/عنوان)"]
  remove:  ["زاوية/صياغة ضعيفة أو مخالفة"]
```

---

## **ملف تسليم موحّد (Unified Delivery File)**

```json
{
  "delivery": {
    "meta": {
      "project": "",
      "date": "{{YYYY-MM-DD}}",
      "market": "Bahrain",
      "currency": "BHD",
      "mode": "quick_draft|full_strategy"
    },
    "strategy_summary": {
      "audience": "",
      "core_message": "",
      "offer": { "core_value": "", "scarcity": "", "guarantee": "", "proof": [] },
      "channels_why": "",
      "market_context": { "direction": "RTL", "seasons": ["رمضان","العيد","اليوم الوطني 16–17 ديسمبر","التخفيضات","العودة للمدارس"] }
    },
    "ads": [
      {
        "channel": "Meta",
        "framework": "PAS",
        "awareness_stage": "problem",
        "variant_id": "v1",
        "tone": "مقنعة",
        "copy": {
          "hook": "كل إعلان غير مختبَر = ميزانية مهدورة.",
          "short": "تكلفة الاكتساب ترتفع؟ اختبر 2–3 زوايا خلال 10 دقائق.",
          "long": "تكتب إعلانات ولا ترى تحويلًا؟ CMIS يولّد 8 نسخ قابلة للاختبار بالعربية (RTL) مع إثبات وتضمين BHD. ابدأ الآن بنسخة تجريبية.",
          "cta": "ابدأ التجربة المجانية الآن — بدون بطاقة.",
          "proof": ["[محاكاة] تقييم 4.7/5 خلال 90 يومًا"]
        },
        "primary_metric": "CTR",
        "naming": "Ad_v2_Meta_Short_HookA",
        "compliance": "✅",
        "notes": "PAS لمرحلة Problem على Meta لرفع الانتباه بسرعة."
      }
    ],
    "dco": {
      "candidates": [],
      "experiment": {},
      "report": {}
    },
    "compliance_reports": [],
    "improvement_recommendations": { "repeat": [], "refine": [], "remove": [] }
  }
}
```

---

## **مخطط الإخراج — JSON برمجي (قابل للتصدير)**

```json
{
  "strategy": {
    "summary": "",
    "message_map": [
      { "phase": "Problem-Aware", "audience": "primary", "channel": "Meta", "angle": "هدر الميزانية", "offer": "تجربة مجانية 7 أيام", "cta": "ابدأ التجربة" }
    ]
  },
  "ads": [
    {
      "channel": "Google_RSA",
      "framework": "4U+FAB",
      "awareness_stage": "solution",
      "variant_id": "v1",
      "tone": "مباشرة",
      "copy": {
        "hook": "",
        "short": "عناوين ≤30/أوصاف ≤90 — نية بحث واضحة.",
        "long": "اختبر 2–3 زوايا، إعداد 3 دقائق، ضمان 14 يومًا.",
        "cta": "تعرّف على الأسعار بالـBHD",
        "proof": ["[افتراض] تقييم 4.7/5 (90 يومًا)"]
      },
      "primary_metric": "CTR",
      "naming": "Ad_v1_Google_RSA_IntentX",
      "compliance": "⚠️",
      "notes": "4U+FAB يوضّح الفائدة ويعالج الاعتراضات بسرعة."
    }
  ],
  "dco": {
    "atomic_assets": { "headlines": [], "bodies": [], "ctas": [], "proofs": [] }
  },
  "report": {
    "winners": ["Ad_v2_Meta_Short_HookA"],
    "insights": ["Hook رقمي + ضمان محدد رفع CTR ~22% [افتراض]"],
    "next_actions": ["نسخة هجينة PAS→AIDA لمرحلة Product-Aware"]
  }
}
```

---

## **قوالب التقارير**

### **1\) تقرير الأداء (Performance Report)**

```
performance_report:
  date_range: ["{{start}}","{{end}}"]
  tested_ads: {{N}}
  best_channel: "Meta|Google|TikTok|LinkedIn|Email|Landing"
  top_kpis:
    ctr_max: "{{%}}"
    cvr_max: "{{%}}"
    roas_max: "{{x}}"
  insights:
    - "الإعلانات التعليمية تفوقت على الترفيهية بنسبة {{%}}."
    - "Hook رقمي يتفوق على السردي في البحرين."
  recommendations:
    repeat:  ["زاوية الإثبات الرقمي"]
    refine:  ["صياغة الضمان بوضوح أكثر"]
    remove:  ["المقارنة الساخرة على LinkedIn"]
```

### **2\) تقرير الزوايا الإبداعية (Creative Angles Report)**

```
creative_angles_report:
  winning_angles:
    - name: "إثبات اجتماعي رقمي"
      why: "يبني ثقة سريعة مع رقم حديث"
      where: ["Meta","Landing"]
    - name: "سرعة الإنجاز"
      why: "تلاؤم مع ضغط المواسم"
      where: ["TikTok","Google"]
```

### **3\) تقرير اللغة والنبرة (Tone & Messaging Report)**

```
tone_messaging_report:
  b2b_linkedin: { tone: "مهني", performance: "CTR أعلى 12%" }
  b2c_meta:     { tone: "عاطفي مباشر", performance: "HookRate أعلى 18%" }
```

---

## **قوالب التسميات (Naming Conventions)**

```
naming:
  ad:        "Ad_v{n}_{Channel}_{Len}_{HookID}"
  bundle:    "Bundle_{Market}_{Objective}_{Date}"
  landing:   "LP_v{n}_{OfferID}"
  email:     "Email_v{n}_{Goal}"
  experiment:"EXP_{Date}_{Channel}_{Framework}"
```

---

## **حِزم التصدير (Bundles)**

```
export_bundles:
  meta:     ["Ad_v1_Meta_Feed_Short_HookA","Ad_v2_Meta_Story_Short_HookB"]
  tiktok:   ["Ad_v1_TikTok_ScriptA","Ad_v2_TikTok_ScriptB"]
  google:   ["Ad_v1_Google_RSA_IntentX","Ad_v2_Google_RSA_IntentY"]
  linkedin: ["Ad_v1_LinkedIn_Post","Ad_v2_LinkedIn_LeadGen"]
  email:    ["Email_v1_Conversion","Email_v2_Awareness"]
  landing:  ["LP_v1_OfferA"]
  naming:   "Bundle_Bahrain_{Objective}_{YYYYMMDD}"
```

---

## **مُلحق قوالب جاهزة للنسخ**

### **قالب صفحة هبوط (مُختصر)**

```
landing_template:
  h1: "{{promise_headline}}"
  subhead: "{{support_line}}"
  sections:
    - value: ["ميزة → منفعة", "USP: {{result}} خلال {{time}} بدون {{constraint}}"]
    - proof: ["تقييم {{rating}}/5 (آخر 90 يومًا)","دراسة حالة بحرينية"]
    - plans: ["{{plan1}} BHD","{{plan2}} BHD"]
    - faq: ["س/ج × 4"]
  cta: "ابدأ الآن — مجانًا"
```

### **قالب بريد (ACCA)**

```
email_acca:
  subject: "{{مفيد}} | {{محدد جدًا}}"
  preheader: "{{ملخص القيمة}}"
  body:
    awareness: "{{problem_stmt}}"
    comprehension: "{{how_it_works}}"
    conviction: "{{proof_layers}}"
    action: "{{cta}}"
```

---

## **مدقّق الإخراج (Self-Checks)**

```
self_checks:
  - "RTL سليم وفواصل عربية"
  - "CTA واحد لكل أصل"
  - "لا مطلقات؛ كل رقم مصدر/نطاق/[افتراض]"
  - "طول مطابق لحدود القناة"
  - "وسم #إعلان في بداية المواد المرعية"
  - "BHD عند ذكر أسعار"
```

---

## **حقل تعاريف عامة (Glossary مختصر)**

```
glossary:
  USP: "عرض قيمة فريد: نتيجة + زمن + قيد"
  JTBD: "الوظائف المطلوب إنجازها"
  DCO: "التخصيص الديناميكي للإبداع"
  Proof Layers: "Light/Medium/Heavy"
```

---

## **ملخص حالة (3 أسطر — يُولَّد تلقائيًا)**

* **التجهيز للتسليم:** {{ads\_count}} أصل عبر {{channels\_count}} قنوات (Bahrain/BHD/RTL).

* **الامتثال:** {{ok\_pct}}% ✅ | {{warn}} ⚠️ | {{block}} 🚫.

* **الخطوة التالية الداخلية:** أرشفة النسخ وتسليم الحِزمة: `{{bundle_name}}`.

