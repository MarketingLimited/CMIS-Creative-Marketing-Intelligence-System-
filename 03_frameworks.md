# **03\_frameworks.md**

## **الغرض**

اختيار/مزج الأطر التسويقية لإنتاج نسخ إعلانية قابلة للاختبار عبر القنوات، مع افتراضي **نسختين مختلفتين** لكل أصل، ونسخة **هجينة اختيارية** عند الحاجة. توطين افتراضي: **مملكة البحرين (BHD, AR, RTL)**.

---

## **المدخلات المتوقعة**

```json
{
  "strategy_core": {
    "jtbd": "",
    "usp": "",
    "awareness_stage": "unaware|problem|solution|product|most",
    "personas": { "primary": "", "alt": "" },
    "offer": { "core_value": "", "scarcity": "", "guarantee": "", "proof": [] }
  },
  "persuasion": {
    "headlines": [],
    "hooks": [],
    "stories_bab": [],
    "bullets_fab": [],
    "ctas": [],
    "objection_ladder": {}
  },
  "channels": ["Meta", "Google", "TikTok", "LinkedIn", "Email", "Landing"],
  "objective": "awareness|conversion|retention",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" },
  "max_variations": 2
}
```

---

## **مبدأ الاختيار**

* المرحلة تحدد الإطار الأساسي، والقناة تضبط الشكل.

* الإخراج الافتراضي \= **نسختان** مبنيّتان على الإطار الأنسب؛ **الهجينة** تُنتج فقط إن كان الهدف **conversion** أو المرحلة **Product/Most-Aware**.

### **مصفوفة المرحلة ← الإطار**

| المرحلة | الإطار الأساسي | بديل | هجينة اختيارية |
| ----- | ----- | ----- | ----- |
| Unaware | StoryBrand / AIDA | ACCA | BAB→AIDA |
| Problem-Aware | PAS | AIDA | PAS→AIDA |
| Solution-Aware | AIDA / FAB | StoryBrand | FAB→4U |
| Product-Aware | FAB / 4C | AIDA | PAS→AIDA أو FAB→4U |
| Most-Aware | 4U / 4C | BAB | 4C→AIDA |

### **مصفوفة القناة ← تفضيل الإطار**

* **Meta/TikTok**: AIDA أو PAS (Hook سريع)؛ هجينة PAS→AIDA عند التحويل.

* **Google RSA**: 4U \+ FAB.

* **LinkedIn**: PASTOR أو StoryBrand (قيمة تحليلية \+ Proof).

* **Email**: 4U أو ACCA أو PAS حسب الهدف.

* **Landing**: 4C أو PASTOR بترتيب منطقي وإثباتات.

---

## **خوارزمية القرار (مبسطة)**

```
if objective == "conversion" or strategy_core.awareness_stage in ["product","most"]:
  hybrid_enabled: true
else:
  hybrid_enabled: false

primary_fw := choose_by_stage(strategy_core.awareness_stage)
secondary_fw := choose_alt(primary_fw, channel)

variations := 2
if hybrid_enabled: variations := min(3, max_variations + 1)
```

---

## **حدود الطول (تلزم عند التوليد)**

* **Google RSA**: عناوين ≤ 30 حرفًا، أوصاف ≤ 90 حرفًا.

* **Meta**: نص رئيسي ≤ 4 أسطر، Hook في السطر الأول، CTA واحد.

* **TikTok/Reels**: 6–12 ثانية، نص شاشة ≤ 8 كلمات، 4 مشاهد كحد أقصى.

* **LinkedIn**: 2–4 فقرات قصيرة \+ سطر بيانات/Proof.

* **Email**: Subject ≤ 50، بداية ≤ 25 كلمة، CTA واحد.

* **Landing**: H1 واضح \+ Subhead \+ أقسام قصيرة بعناوين فرعية.

---

## **قوالب تطبيق الأطر حسب القناة**

### **A) Meta Ad — AIDA / PAS / PAS→AIDA**

**قالب AIDA**

```
[Hook/Attention]: {{hook}}
[Interest]: {{pain_or_insight}} 
[Desire]: {{usp}} | {{proof_snippet}}
[Action]: {{cta}}  (BHD, RTL, #إعلان)
```

**قالب PAS**

```
Problem: {{pain_in_client_voice}}
Agitation: {{risk_of_inaction}}
Solution: {{usp}} + {{offer_snippet}} + {{guarantee}}
CTA: {{cta}}
```

**هجينة PAS→AIDA**: Problem→Agitation→\[Attention/Hook\]→Interest→Desire→Action.

---

### **B) TikTok Script (6–12s) — AIDA / PAS**

```
S1 (0–2s) [Hook/Attention]: {{on_screen_1}} | VO: "{{vo_1}}"
S2 (2–5s) [Problem/Interest]: {{on_screen_2}} | VO: "{{vo_2}}"
S3 (5–9s) [Desire/Solution+Proof]: {{on_screen_3}} | VO: "{{vo_3}}"
S4 (9–12s) [Action]: {{cta_text}} | VO: "{{cta_vo}}" (BHD/RTL/#إعلان)
```

---

### **C) Google RSA — 4U \+ FAB**

**عناوين (10–20) ≤ 30 حرفًا**  
 أمثلة قوالب:

* «{{result}} خلال {{time}}»

* «من {{old\_price}} إلى {{new\_price}} BHD»

* «{{feature}} → {{benefit}}»

**أوصاف (5–10) ≤ 90 حرفًا**

* «اختبر ٢–٣ زوايا اليوم — إعداد ٣ دقائق.»

* «ضمان ١٤ يومًا، تقييم {{rating}}/٥ (آخر ٩٠ يومًا).»

**مسارات اختيارية:** `/{category}/{bahrain}`

---

### **D) LinkedIn Sponsored Post — PASTOR / StoryBrand**

**PASTOR**

```
Problem: {{strategic_problem_in_numbers}}
Amplify: {{business_risk}}
Story: {{mini_case_bahrain}}
Transformation: {{result_range}} خلال {{time}}
Offer: {{plan_or_demo}}
Response (CTA): {{cta_b2b}}
```

**StoryBrand**

```
Character: {{persona_role}}
Problem: {{pain_point}}
Guide: {{brand_as_guide}} + {{credibility_line}}
Plan: {{simple_steps_2or3}}
Success: {{business_outcome}}
CTA: {{cta_b2b}}
```

---

### **E) Email — 4U / ACCA / PAS**

**4U (Subject/Body مختصر)**

```
Subject: {{useful}} | {{urgent}} | {{ultra_specific}}
Body: 
- سطر افتتاحي: {{hook_line}}
- قيمة مختصرة: {{usp}} + {{proof_snippet}}
- CTA: {{cta}}
```

**ACCA**

```
Awareness: {{problem_stmt}}
Comprehension: {{how_it_works}}
Conviction: {{proof_layers}}
Action: {{cta}}
```

---

### **F) Landing Page — 4C / PASTOR**

**4C**

```
Clear: H1 {{promise_headline}}
Concise: Subhead {{support_line}}
Compelling: {{benefits_list}} + {{proof}}
Credible: {{logos/testimonials}} + {{guarantee}}
CTA: {{cta_primary}} (BHD)
```

---

## **توطين البحرين (تلقائي)**

* العملة: **BHD** داخل العناوين/الأوصاف عند ذكر الأسعار.

* الاستعارات المحلية عند الحاجة: «قبل الدوام/بعد الفطور/نهاية الأسبوع».

* الإفصاح يبدأ بـ **\#إعلان** في المواد المرعية.

---

## **قواعد امتثال مضمنة**

* حظر «مضمون/الأفضل/فوري».

* أي رقم بلا مصدر يُوسم **\[افتراض\]** أو **\[محاكاة\]**.

* زر واحد لكل إعلان.

* لا CTA شرائي لجمهور بارد؛ استخدم CTA تجريبي/استكشافي.

---

## **ناتج الوحدة (JSON قياسي لكل قناة/نسخة)**

```json
{
  "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing",
  "framework": "AIDA|PAS|FAB|4U|4C|PASTOR|StoryBrand|Hybrid",
  "awareness_stage": "unaware|problem|solution|product|most",
  "variant_id": "v1|v2|hybrid",
  "tone": "…",
  "copy": {
    "short": "",
    "long": "",
    "hook": "",
    "cta": "",
    "proof": []
  },
  "length_check": "pass|fail",
  "guardrails_check": "pass|fail",
  "reasoning_note": "لماذا تم اختيار الإطار لهذه القناة والمرحلة",
  "compliance": "✅|⚠️|🚫"
}
```

---

## **مثال مُخرجات مختصر (Meta — PAS و AIDA)**

```json
[
  {
    "channel": "Meta",
    "framework": "PAS",
    "awareness_stage": "problem",
    "variant_id": "v1",
    "tone": "مقنعة",
    "copy": {
      "hook": "كل إعلان غير مختبَر = ميزانية مهدورة.",
      "short": "تكلفة الاكتساب ترتفع؟ الحل: نسخ قابلة للاختبار خلال ١٠ دقائق.",
      "long": "تكتب إعلانات ولا ترى تحويلًا؟ حرّك العجلة باختبار زوايا سريعة بلغة البحرين. CMIS يجهّز لك ٨ نسخ في ١٠ دقائق مع إثبات ٤.٧/٥ وضمان ١٤ يومًا.",
      "cta": "ابدأ التجربة المجانية الآن — بدون بطاقة.",
      "proof": ["[محاكاة] تقييم ٤.٧/٥ (٩٠ يومًا)"]
    },
    "length_check": "pass",
    "guardrails_check": "pass",
    "reasoning_note": "Problem-Aware على Meta يناسبه PAS مع Hook رقمي.",
    "compliance": "✅"
  },
  {
    "channel": "Meta",
    "framework": "AIDA",
    "awareness_stage": "solution",
    "variant_id": "v2",
    "tone": "ودية",
    "copy": {
      "hook": "قبل: كتابة مرهقة — بعد: ٨ نسخ في ١٠ دقائق.",
      "short": "جرّب CMIS — نسخ سريعة، إثبات واضح، CTA واحد.",
      "long": "انتباه: انسخ جاهزة للاختبار خلال ١٠ دقائق. اهتمام: خرائط رسائل وفق الوعي. رغبة: تقليل الوقت ٦٠٪ [افتراض]. فعل: اطّلع على الخطط بالـBHD.",
      "cta": "اطّلع على الخطط بالـBHD.",
      "proof": ["[افتراض] تقليل الوقت ٦٠٪"]
    },
    "length_check": "pass",
    "guardrails_check": "pass",
    "reasoning_note": "Solution-Aware على Meta يناسبه AIDA لبناء رغبة ثم فعل.",
    "compliance": "⚠️"
  }
]
```

---

## **ملخّص حالة (3 أسطر — يُولَّد تلقائيًا)**

* **إطارات مُختارة:** {{primary\_fw}} و{{secondary\_fw}}؛ هجينة {{hybrid?}}.

* **التزام الطول/الحواجز:** {{checks\_summary}}.

* **تمرير للمرحلة التالية:** `04_adaptation_distribution.md` مع قنوات مختارة.

**انتهى ملف 03\_frameworks.md**

