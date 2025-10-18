<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- اختيار/مزج الأطر التسويقية لإنتاج نسخ إعلانية قابلة للاختبار عبر القنوات، مع افتراضي **نسختين مختلفتين** لكل أصل، ونسخة **هجينة اختيارية** عند الحاجة. توطين افتراضي: **مملكة البحرين (BHD, AR, RTL)**.
- تهيئة المخرجات للتكامل السلس مع طبقات **Gems & GPTs** بحيث يمكن استدعاؤها آليًا عند طلب المحتوى أو خطط التسويق بجميع أنواعها.
<!-- CMIS:END::PURPOSE -->

<!-- CMIS:START::INPUTS -->
## المدخلات (JSON)
```json
{
  "brand": "",
  "product_or_service": "",
  "objective": "awareness|conversion|retention",
  "target_audience": "",
  "channels": [],
  "budget_bhd": "",
  "max_variations": 3,
  "dco_request": false,
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
  "channels": ["Meta", "Google_RSA", "TikTok", "LinkedIn", "Email", "Landing"],
  "objective": "awareness|conversion|retention",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" },
  "max_variations": 2
}
```
<!-- CMIS:END::INPUTS -->

### مثال موحد: ربط الهدف التسويقي بمراحل الوعي والقُمع
> | الهدف التسويقي | مرحلة الوعي المرجحة | موقع القُمع | CTA مقترح |
> | --- | --- | --- | --- |
> | awareness | from unaware → problem-aware | TOFU | «تعرّف أكثر» أو «اكتشف القصة» |
> | conversion | from solution-aware → product-aware | MOFU/BOFU | «احجز تجربة» أو «اطلب العرض» |
> | retention | most-aware (عملاء حاليون) | Loyalty/Post-Purchase | «جدّد اشتراكك» أو «شارك مزاياك» |

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب وربط الهدف/الجمهور بالقناة والمرحلة، مع حفظ القيم الأولية في `request_snapshot` ليستدعيها **Gem Manager** لاحقًا.
2. إن وُجد `trend_research` فعّل آلية البحث، وادمج الملخص والمصدر داخل كل تنويع في حقول `proof` و`reasoning_note`.
3. شغّل روتين `prepare_secondary_fields` (راجع الملحق Stage B) لتكوين **مصفوفة used_fields** تغطي Pain/PAS، Benefit/AIDA، Proof/FAB مع اختلاف ≥ 3 محاور (trigger/framework/strategy/tone/awareness/funnel).
4. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات، إلزام الميتاداتا).
5. إنتاج المخرجات وفق القالب أدناه، مع تمرير `unit_output` إلى طبقة **Gems & GPTs** باستخدام المفتاح `framework_gem_contract` الموضّح في قسم التكامل.

<!-- CMIS:START::MIXER_STEP -->
- بعد تلخيص المدخلات، ابنِ **مصفوفات** من الحقول (تدعم تعدد القيم لكل حقل + افتراضات عند الحاجة)،
  وولّد **3 تنويعات أساسية** (v1–v3) تغطي Pain/PAS، Benefit/AIDA، Proof/FAB مع اختلاف ≥3 محاور (trigger, framework, strategy, tone, awareness/funnel).
  - عند تفعيل وضع DCO Expansion (إشارات Stage B أو طلب صريح)، أنشئ مجموعة توسعة (v4+) ترفع الإجمالي إلى 6–12 تنويعًا مع توثيق سبب التفعيل.
  لكل نموذج: اطبع `used_fields` و`design_description` و`compliance`.
<!-- CMIS:END::MIXER_STEP -->

### طبقة التكامل مع Gems & GPTs
- هيكل التسليم الآلي:
  ```json
  {
    "framework_gem_contract": {
      "request_snapshot": { ... },
      "used_fields": { ... },
      "variants": [ { ... } ],
      "handoff": {
        "next_module": "04_adaptation_distribution.md",
        "priority": "core|expansion",
        "automation_tags": ["frameworks", "ads", "bahrain_rtl"]
      }
    }
  }
  ```
- `request_snapshot` يعكس المدخلات بعد دمج الافتراضات، ويجب أن يتضمن `objective`, `channels`, `awareness_stage`, `max_variations`, `dco_request`.
- عند توليد كل تنويع، اكتب `automation_tags` إضافية (`pain_angle`, `benefit_angle`, `proof_angle`, `hybrid`) ليتمكن Gem من توجيه النسخ إلى نماذج التخصيص أو الترجمة.
- حافظ على اتساق أسماء المتغيرات (`variant_id`, `channel`, `framework`) مع باقي الوحدات لتجنّب التعارض داخل نظام الأوركسترا.
- أي تعارض في القيم (مثل اختلاف إطار عن جدول المرحلة) يُسجّل في `compliance` مع شرح مختصر في `reasoning_note`، ويُرسل مؤشر خطأ (`⚠️ أو 🚫`) ليتمكن Gem من إرجاعه للمراجعة البشرية.

### المحتوى الأصلي الكامل (منسوخ حرفيًا)
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
  "automation_tags": [],
  "copy": {
    "short": "",
    "long": "",
    "hook": "",
    "cta": "",
    "proof": []
  },
  "design_description": {
    "composition": "",
    "background": "",
    "colors": "",
    "element_positions": "",
    "lighting": "",
    "ratio": "",
    "motion": ""
  },
  "used_fields": {},
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

**انتهى ملف `03_frameworks.md`**

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

### مثال 1 — SaaS B2B (Meta + LinkedIn)

```json
{
  "request_snapshot": {
    "brand": "FlowMetrics",
    "product_or_service": "منصة تحليلات اشتراكية",
    "objective": "conversion",
    "target_audience": "مديرو التسويق في شركات SaaS الخليجية",
    "channels": ["Meta", "LinkedIn"],
    "budget_bhd": 2800,
    "max_variations": 3,
    "dco_request": false,
    "awareness_stage": "solution"
  }
}
```

| variant_id | channel  | framework | strategy    | awareness/funnel | triggers                                |
|------------|----------|-----------|-------------|------------------|-----------------------------------------|
| v1         | Meta     | PAS       | Offer-led   | problem → MOFU   | ضيق الوقت، دعم مباشر 24/7، CTA تجريبي  |
| v2         | Meta     | AIDA      | UGC         | solution → MOFU  | طموح، دراسة حالة SaaS بحرينية، RTL    |
| v3         | LinkedIn | PASTOR    | Educational | solution → BOFU  | أرقام churn، ضمان 14 يومًا، CTA Demo   |
| hybrid     | Meta     | PAS→AIDA  | Social Proof | product → BOFU   | ندرة، [افتراض] تقليل الوقت 55٪، ضمان  |

```json
{
  "framework_gem_contract": {
    "used_fields": {
      "v1": {
        "segments": ["مديرو تسويق SaaS"],
        "pains": ["ضيق الوقت", "تشتت بيانات الاشتراك"],
        "marketing_framework": "PAS",
        "marketing_strategy": "Offer-led",
        "tones": ["مقنعة"],
        "message_map": ["Hook ألم", "حل سريع", "CTA تجربة"],
        "proofs": ["شهادة جهة جودة"]
      },
      "v2": {
        "segments": ["فرق النمو"],
        "pains": ["انخفاض التحويل التجريبي"],
        "marketing_framework": "AIDA",
        "marketing_strategy": "UGC",
        "tones": ["مشوقة"],
        "message_map": ["Hook فيديو قصير", "خطوات ثلاث", "CTA خطة"],
        "proofs": ["[مصدر: Deloitte]"]
      }
    },
    "variants": [
      {
        "variant_id": "v1",
        "channel": "Meta",
        "automation_tags": ["frameworks", "ads", "pain_angle"],
        "design_description": {
          "composition": "لقطة شاشة لوحة مؤشرات مع يد تشير إلى KPI أحمر يتحول إلى أخضر",
          "background": "مكتب حديث بإضاءة نهارية",
          "colors": "#005C8A, #F5F0E6",
          "element_positions": "لوغو أعلى يمين، هاشتاق #إعلان أعلى يسار، CTA زر سفلي",
          "ratio": "4:5",
          "motion": "نسخة ثابتة مع انتقال CTA متوهج"
        }
      }
    ],
    "handoff": {
      "next_module": "04_adaptation_distribution.md",
      "priority": "core",
      "automation_tags": ["frameworks", "ads", "bahrain_rtl"]
    }
  }
}
```

**ملاحظات تكامل:**
- `automation_tags` تُستخدم لتوجيه Gems نحو مولدات الصور (زاوية Pain) أو فرق النسخ (LinkedIn Thought Leadership).
- `reasoning_note` لكل تنويع يربط بين الجدول أعلاه وقاعدة المرحلة/القناة لضمان الشفافية عند المراجعة البشرية.
- عند تمرير الحزمة إلى الوحدة 04، يظل `request_snapshot` متاحًا لإعادة الاستخدام في خطط التوزيع أو تخصيص الرسائل.

### مثال 2 — (المثال الأصلي Meta — PAS و AIDA)

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

**ملخّص حالة (3 أسطر — يُولَّد تلقائيًا)**

* **إطارات مُختارة:** {{primary_fw}} و{{secondary_fw}}؛ هجينة {{hybrid?}}.
* **التزام الطول/الحواجز:** {{checks_summary}}.
* **تمرير للمرحلة التالية:** `04_adaptation_distribution.md` مع قنوات مختارة.

**انتهى ملف `03_frameworks.md`**

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

<!-- CMIS:START::OUTPUT_SCHEMA_HINT -->
{
  "variations": [
    {
      "id": "v1",
      "channel": "Instagram",
      "framework": "AIDA",
      "copy": { "hook": "", "short": "", "long": "", "cta": "", "proof": [] },
      "design_description": {
        "composition": "", "background": "", "lighting": "",
        "colors": "", "highlight": "", "de_emphasize": "",
        "element_positions": "", "ratio": "9:16", "motion": ""
      },
      "used_fields": {
        "marketing_objective": "", "emotional_triggers": [], "channels": [],
        "segments": [], "pains": [], "marketing_frameworks": [], "marketing_strategies": [],
        "tones": [], "features": [], "benefits": [], "transformational_benefits": [],
        "usps": [], "message_map": [], "proofs": []
      },
      "compliance": "✅"
    }
  ]
}
<!-- CMIS:END::OUTPUT_SCHEMA_HINT -->

<!-- CMIS:START::STATUS -->

## ملخص حالة (3 أسطر)

* ما الذي أُنجز؟
* أي افتراضات؟
* ملاحظات الامتثال؟

<!-- CMIS:END::STATUS -->

<!-- CMIS:START::REFS_QUALITY -->
### مراجع الجودة والامتثال
- راجع `support_and_templates.md §QUALITY_AND_VARIATIONS` قبل الإخراج النهائي.
- طبّق قواعد `support_and_templates.md §QUALITY_AND_VARIATIONS` عند توليد تنويعات.
<!-- CMIS:END::REFS_QUALITY -->
