<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- دمج **التخصيص الديناميكي DCO** مع **الاختبار والتحسين** لإنتاج تركيبات إبداعية قابلة للقياس، ضبط الحواجز، إدارة الفرضيات، والتحكّم في عدد المتغيرات. الافتراضي: **مملكة البحرين** (AR/RTL، BHD).
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
  "config": {
    "mode": "quick_draft|full_strategy",
    "time_bounds_days": 3,
    "kpi_targets": { "ctr_cold_range": [0.8, 3.0], "cvr_range": [1.0, 8.0], "roas_min": 1.5 },
    "max_variations_per_channel": 3,
    "numbers_locale": "ar"
  },
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" },
  "framework_output": [
    {
      "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing",
      "framework": "AIDA|PAS|FAB|4U|4C|PASTOR|StoryBrand|Hybrid",
      "awareness_stage": "unaware|problem|solution|product|most",
      "tone": "",
      "copy": { "short": "", "long": "", "hook": "", "cta": "", "proof": [] }
    }
  ],
  "data_feeds": { "price": null, "stock": null, "location": "Bahrain", "date": null },
  "constraints": { "forbidden_words": [], "claims_to_avoid": [] }
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
## **1\) تفكيك الأصول الذرّية (Atomic Assets)**

```
atomic_assets:
  headlines:   ["H1/H2 قصيرة، واضحة، محلية عند اللزوم"]
  hooks:       ["≤12 كلمة", "نسخة فيديو Overlay ≤8 كلمات"]
  bodies:      ["Short ≤50 كلمة", "Long ≤120 كلمة"]
  visuals:     ["صورة/فيديو/Carousel", "فكرة بصرية RTL-aware"]
  proofs:      ["تقييمات", "أرقام موثقة", "[محاكاة]/[افتراض] عند الغياب"]
  ctas:        ["CTA واحد", "مكيّف للمرحلة"]
  offers:      ["قيمة أساسية", "ندرة مبررة", "ضمان محدد"]
normalization:
  - "حذف المطلقات (مضمون/الأفضل/فوري)"
  - "RTL وفواصل عربية"
  - "BHD عند ذكر الأسعار"
  - "الإفصاح #إعلان في المواد المرعية"
```

---

## **2\) حواجز الحراسة (Guardrails) — قواعد If/Then**

```
guardrails:
  - if: { stage: ["unaware","problem"] }
    then: { framework: ["PAS","StoryBrand"], cta: "تجريبي/تعليمي", forbid: ["اشترِ الآن"] }
  - if: { stage: ["solution","product"] }
    then: { framework: ["AIDA","FAB"], cta: "تسعير/ديمو", require: ["proof_or_range"] }
  - if: { stage: ["most"] }
    then: { framework: ["4U","4C"], cta: "اشتراك/شراء", require: ["سعر BHD","ضمان واضح"] }
  - always_forbid: ["مضمون","الأفضل","فوري"]
  - visual_tone_conflict: "لا نبرة جريئة مع صور مهنية"
  - cold_no_purchase: "ممنوع CTA شرائي لجمهور بارد"
```

---

## **3\) توليد التركيبات (Combinator)**

* أقصى تركيبات لكل قناة: `max_variations_per_channel` (افتراضي 3).

* سياسة الاختيار: **Top-K** بحسب تنوّع الزوايا (Hook/Headline/Tone) مع تغطية مرحلتين على الأقل.

* منع الانفجار التركيبي: **Sampling طبقي** (Stage × Framework × CTA) بحد أقصى **K=3**.

**خوارزمية مبسطة**

```
generate_candidates:
  inputs: atomic_assets, guardrails, max_variations_per_channel
  steps:
    - cluster_by_angle: ["Proof-led","Offer-led","Speed-led"]
    - sample: 1 من كل عنقود (حتى K)
    - validate: guardrails + limits(channel)
    - name: "Ad_v{n}_{Channel}_{Len}_{HookID}"
  outputs: candidates
```

---

## **4\) صياغة الفرضيات (Hypothesis)**

```
hypothesis:
  variable: "Hook رقمي مقابل سردي"
  change: "استبدال أول سطر + صورة ذات أرقام/نتيجة"
  expected_outcome: "زيادة CTR بنسبة 15% ضمن 3 أيام"
  stage: "Problem-Aware"
  channel: "Meta"
  metric: "CTR"
```

**قالب عام**

```
HYP:
  variable: ""
  change: ""
  expected_outcome: ""
  stage: ""
  channel: ""
  primary_metric: "CTR|CVR|ROAS|HookRate"
  time_bounds_days: 3
```

---

## **5\) إعداد الاختبارات (A/B و MVT)**

```
testing:
  design: "A/B افتراضي، MVT فقط عند توفر ترافق زيارات كافٍ"
  duration_days: 3
  traffic_split: "50/50 لـ A/B"
  sample_heuristic: "[افتراض] حد أدنى 300 انطباع/نسخة في Meta خلال المدة"
  early_stop_rules:
    - "CTR أقل من 0.2% بعد 24 ساعة → إيقاف مبكر"
    - "مخالفة امتثال 🚫 → إيقاف فوري"
  promotion_rule:
    - "فارق ≥10% في المقياس الأساسي + اتجاه ثابت 2 أيام → ترقية الفائز"
```

---

## **6\) محاذاة المقاييس (Metric Alignment)**

```
metrics_by_stage:
  awareness:     ["Reach","HookRate","View-through"]
  consideration: ["CTR","Dwell Time"]
  conversion:    ["CVR","CPA (BHD)","ROAS"]
  retention:     ["LTV","Churn","Repeat Purchase"]
defaults_bahrain:
  currency: "BHD"
  numbers_locale: "ar"
thresholds:
  ctr_cold_range: [0.8, 3.0]
  roas_min: 1.5
diagnostics:
  low_ctr:   "المشكلة في العنوان/الصورة/Hook"
  low_cvr:   "المشكلة في العرض/الصفحة/الملاءمة"
  low_roas:  "الجمهور/الرسالة غير مناسبين"
  low_view:  "Hook ضعيف أو أول 3 ثوانٍ غير جاذبة"
```

---

## **7\) حقن مغذّيات البيانات (Data Feeds)**

* حقول متغيرة: `{{price}} {{stock}} {{product_name}} {{date}} {{location}}`.

* صياغة عربية سليمة:

  * الأسعار: `{{price}} BHD`،

  * التواريخ: بصيغة يوم/شهر/سنة أو اسم المناسبة (مثال: **اليوم الوطني 16–17 ديسمبر**).

* مثال:

```
"احجز {{product_name}} بسعر يبدأ من {{price}} BHD — متاح حتى {{date}} في {{location}}."
```

---

## **8\) حلقة التحسين (Optimization Loop)**

```
loop:
  - generate: "مرشّحات DCO وفق K"
  - test: "A/B لمدة time_bounds_days"
  - analyze:
      quantitative: ["CTR","CVR","ROAS"]
      qualitative: ["تعليقات","نبرة الجمهور","عبارات متكررة"]
  - learn:
      store_winning_angle: ["زاوية","Hook","Tone","Framework"]
  - rewrite: "توليد جيل جديد مشتق من الفائز"
```

---

## **9\) التعلم التنبّئي (Predictive Learning)**

```
pattern_store:
  key: "angle_id"
  features: ["hook_type","proof_density","cta_kind","tone","stage","channel"]
  outcome: ["ctr_delta","cvr_delta","roas"]
  rule_of_thumb:
    - "[افتراض] Hook رقمي + ضمان محدد تفوّق بمتوسط 20–25% CTR"
  usage: "ترجيح المرشحين الجدد"
```

---

## **10\) الامتثال داخل الاختبار**

* أي نسخة **⚠️** تُعاد صياغتها تلقائيًا مع ذكر سبب التعديل.

* أي نسخة **🚫** تُحجب وتُسجّل المخالفة: (وعد مطلق/سعر غير شفاف/غياب إفصاح).

* الفائز لا يترقى إلا مع **✅**.

---

## **11\) مخرجات الوحدة (JSON)**

```json
{
  "dco": {
    "atomic_assets": { "headlines": [], "hooks": [], "bodies": [], "visuals": [], "proofs": [], "ctas": [], "offers": [] },
    "guardrails": { "rules": [] },
    "candidates": [
      {
        "id": "Ad_v2_Meta_Short_HookA",
        "channel": "Meta",
        "stage": "problem",
        "framework": "PAS",
        "tone": "مقنعة",
        "copy": { "hook": "", "short": "", "long": "", "cta": "", "proof": [] },
        "compliance": "✅|⚠️|🚫"
      }
    ]
  },
  "experiment": {
    "hypothesis": { "variable": "", "change": "", "expected_outcome": "", "stage": "", "channel": "", "primary_metric": "CTR", "time_bounds_days": 3 },
    "design": "A/B",
    "traffic_split": "50/50",
    "date_range": { "start": "", "end": "" },
    "samples": { "impressions_per_variant": 0, "clicks_per_variant": 0 },
    "results": [
      { "id": "Ad_v2_Meta_Short_HookA", "ctr": 1.9, "cvr": 2.4, "roas": 1.8 },
      { "id": "Ad_v2_Meta_Short_HookB", "ctr": 1.5, "cvr": 2.0, "roas": 1.4 }
    ],
    "winner_id": "Ad_v2_Meta_Short_HookA",
    "diagnostics": ["low_roas للف variante B"],
    "promotion_rule_pass": true
  },
  "report": {
    "buckets": ["Best Performer", "Good Variation", "Experimental"],
    "insights": ["Hook رقمي + ضمان محدد تفوّق بــ22% CTR [افتراض]"],
    "next_actions": ["ترقية الفائز لجميع الحِزم", "تجربة CTA تسعير بدل تجريبي في Product-Aware"]
  }
}
```

---

## **12\) سجلّ التجارب (Experiment Log)**

```
log_entry:
  id: "EXP_2025-10-17_META_PAS"
  market: "Bahrain"
  stage: "Problem-Aware"
  channel: "Meta"
  variants: ["Ad_v2_Meta_Short_HookA","Ad_v2_Meta_Short_HookB"]
  date_range: ["2025-10-17","2025-10-19"]
  metric: "CTR"
  outcome: "A تفوّق 21%"
  compliance: "✅"
  notes: "[محاكاة] الحد الأدنى للانطباعات تحقق"
```

---

## **13\) التحقق والحدود**

```
validators:
  - check_length: "limits(channel) متحقق"
  - check_guardrails: "CTA واحد، لا شراء للبارد"
  - check_disclosure: "#إعلان في البداية للمواد المرعية"
  - check_claims: "كل رقم بمصدر/نطاق أو [افتراض]"
  - output: "pass|fail + أسباب"
```

---

## **14\) ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **مولّد التركيبات:** {{K}} مرشّحين/قناة، التزام الحواجز ✅.

* **الاختبار:** A/B لمدة {{time\_bounds\_days}} أيام، المقياس الأساسي {{metric}}.

* **النتيجة/الإجراء:** فائز {{winner\_id}}؛ إعادة توليد جيل جديد مشتق \+ نشر على القنوات ذات الصلة.

**انتهى ملف 05\_testing\_optimization.md**

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

## **1\) تفكيك الأصول الذرّية (Atomic Assets)**

```
atomic_assets:
  headlines:   ["H1/H2 قصيرة، واضحة، محلية عند اللزوم"]
  hooks:       ["≤12 كلمة", "نسخة فيديو Overlay ≤8 كلمات"]
  bodies:      ["Short ≤50 كلمة", "Long ≤120 كلمة"]
  visuals:     ["صورة/فيديو/Carousel", "فكرة بصرية RTL-aware"]
  proofs:      ["تقييمات", "أرقام موثقة", "[محاكاة]/[افتراض] عند الغياب"]
  ctas:        ["CTA واحد", "مكيّف للمرحلة"]
  offers:      ["قيمة أساسية", "ندرة مبررة", "ضمان محدد"]
normalization:
  - "حذف المطلقات (مضمون/الأفضل/فوري)"
  - "RTL وفواصل عربية"
  - "BHD عند ذكر الأسعار"
  - "الإفصاح #إعلان في المواد المرعية"
```

---

## **2\) حواجز الحراسة (Guardrails) — قواعد If/Then**

```
guardrails:
  - if: { stage: ["unaware","problem"] }
    then: { framework: ["PAS","StoryBrand"], cta: "تجريبي/تعليمي", forbid: ["اشترِ الآن"] }
  - if: { stage: ["solution","product"] }
    then: { framework: ["AIDA","FAB"], cta: "تسعير/ديمو", require: ["proof_or_range"] }
  - if: { stage: ["most"] }
    then: { framework: ["4U","4C"], cta: "اشتراك/شراء", require: ["سعر BHD","ضمان واضح"] }
  - always_forbid: ["مضمون","الأفضل","فوري"]
  - visual_tone_conflict: "لا نبرة جريئة مع صور مهنية"
  - cold_no_purchase: "ممنوع CTA شرائي لجمهور بارد"
```

---

## **3\) توليد التركيبات (Combinator)**

* أقصى تركيبات لكل قناة: `max_variations_per_channel` (افتراضي 3).

* سياسة الاختيار: **Top-K** بحسب تنوّع الزوايا (Hook/Headline/Tone) مع تغطية مرحلتين على الأقل.

* منع الانفجار التركيبي: **Sampling طبقي** (Stage × Framework × CTA) بحد أقصى **K=3**.

**خوارزمية مبسطة**

```
generate_candidates:
  inputs: atomic_assets, guardrails, max_variations_per_channel
  steps:
    - cluster_by_angle: ["Proof-led","Offer-led","Speed-led"]
    - sample: 1 من كل عنقود (حتى K)
    - validate: guardrails + limits(channel)
    - name: "Ad_v{n}_{Channel}_{Len}_{HookID}"
  outputs: candidates
```

---

## **4\) صياغة الفرضيات (Hypothesis)**

```
hypothesis:
  variable: "Hook رقمي مقابل سردي"
  change: "استبدال أول سطر + صورة ذات أرقام/نتيجة"
  expected_outcome: "زيادة CTR بنسبة 15% ضمن 3 أيام"
  stage: "Problem-Aware"
  channel: "Meta"
  metric: "CTR"
```

**قالب عام**

```
HYP:
  variable: ""
  change: ""
  expected_outcome: ""
  stage: ""
  channel: ""
  primary_metric: "CTR|CVR|ROAS|HookRate"
  time_bounds_days: 3
```

---

## **5\) إعداد الاختبارات (A/B و MVT)**

```
testing:
  design: "A/B افتراضي، MVT فقط عند توفر ترافق زيارات كافٍ"
  duration_days: 3
  traffic_split: "50/50 لـ A/B"
  sample_heuristic: "[افتراض] حد أدنى 300 انطباع/نسخة في Meta خلال المدة"
  early_stop_rules:
    - "CTR أقل من 0.2% بعد 24 ساعة → إيقاف مبكر"
    - "مخالفة امتثال 🚫 → إيقاف فوري"
  promotion_rule:
    - "فارق ≥10% في المقياس الأساسي + اتجاه ثابت 2 أيام → ترقية الفائز"
```

---

## **6\) محاذاة المقاييس (Metric Alignment)**

```
metrics_by_stage:
  awareness:     ["Reach","HookRate","View-through"]
  consideration: ["CTR","Dwell Time"]
  conversion:    ["CVR","CPA (BHD)","ROAS"]
  retention:     ["LTV","Churn","Repeat Purchase"]
defaults_bahrain:
  currency: "BHD"
  numbers_locale: "ar"
thresholds:
  ctr_cold_range: [0.8, 3.0]
  roas_min: 1.5
diagnostics:
  low_ctr:   "المشكلة في العنوان/الصورة/Hook"
  low_cvr:   "المشكلة في العرض/الصفحة/الملاءمة"
  low_roas:  "الجمهور/الرسالة غير مناسبين"
  low_view:  "Hook ضعيف أو أول 3 ثوانٍ غير جاذبة"
```

---

## **7\) حقن مغذّيات البيانات (Data Feeds)**

* حقول متغيرة: `{{price}} {{stock}} {{product_name}} {{date}} {{location}}`.

* صياغة عربية سليمة:

  * الأسعار: `{{price}} BHD`،

  * التواريخ: بصيغة يوم/شهر/سنة أو اسم المناسبة (مثال: **اليوم الوطني 16–17 ديسمبر**).

* مثال:

```
"احجز {{product_name}} بسعر يبدأ من {{price}} BHD — متاح حتى {{date}} في {{location}}."
```

---

## **8\) حلقة التحسين (Optimization Loop)**

```
loop:
  - generate: "مرشّحات DCO وفق K"
  - test: "A/B لمدة time_bounds_days"
  - analyze:
      quantitative: ["CTR","CVR","ROAS"]
      qualitative: ["تعليقات","نبرة الجمهور","عبارات متكررة"]
  - learn:
      store_winning_angle: ["زاوية","Hook","Tone","Framework"]
  - rewrite: "توليد جيل جديد مشتق من الفائز"
```

---

## **9\) التعلم التنبّئي (Predictive Learning)**

```
pattern_store:
  key: "angle_id"
  features: ["hook_type","proof_density","cta_kind","tone","stage","channel"]
  outcome: ["ctr_delta","cvr_delta","roas"]
  rule_of_thumb:
    - "[افتراض] Hook رقمي + ضمان محدد تفوّق بمتوسط 20–25% CTR"
  usage: "ترجيح المرشحين الجدد"
```

---

## **10\) الامتثال داخل الاختبار**

* أي نسخة **⚠️** تُعاد صياغتها تلقائيًا مع ذكر سبب التعديل.

* أي نسخة **🚫** تُحجب وتُسجّل المخالفة: (وعد مطلق/سعر غير شفاف/غياب إفصاح).

* الفائز لا يترقى إلا مع **✅**.

---

## **11\) مخرجات الوحدة (JSON)**

```json
{
  "dco": {
    "atomic_assets": { "headlines": [], "hooks": [], "bodies": [], "visuals": [], "proofs": [], "ctas": [], "offers": [] },
    "guardrails": { "rules": [] },
    "candidates": [
      {
        "id": "Ad_v2_Meta_Short_HookA",
        "channel": "Meta",
        "stage": "problem",
        "framework": "PAS",
        "tone": "مقنعة",
        "copy": { "hook": "", "short": "", "long": "", "cta": "", "proof": [] },
        "compliance": "✅|⚠️|🚫"
      }
    ]
  },
  "experiment": {
    "hypothesis": { "variable": "", "change": "", "expected_outcome": "", "stage": "", "channel": "", "primary_metric": "CTR", "time_bounds_days": 3 },
    "design": "A/B",
    "traffic_split": "50/50",
    "date_range": { "start": "", "end": "" },
    "samples": { "impressions_per_variant": 0, "clicks_per_variant": 0 },
    "results": [
      { "id": "Ad_v2_Meta_Short_HookA", "ctr": 1.9, "cvr": 2.4, "roas": 1.8 },
      { "id": "Ad_v2_Meta_Short_HookB", "ctr": 1.5, "cvr": 2.0, "roas": 1.4 }
    ],
    "winner_id": "Ad_v2_Meta_Short_HookA",
    "diagnostics": ["low_roas للف variante B"],
    "promotion_rule_pass": true
  },
  "report": {
    "buckets": ["Best Performer", "Good Variation", "Experimental"],
    "insights": ["Hook رقمي + ضمان محدد تفوّق بــ22% CTR [افتراض]"],
    "next_actions": ["ترقية الفائز لجميع الحِزم", "تجربة CTA تسعير بدل تجريبي في Product-Aware"]
  }
}
```

---

## **12\) سجلّ التجارب (Experiment Log)**

```
log_entry:
  id: "EXP_2025-10-17_META_PAS"
  market: "Bahrain"
  stage: "Problem-Aware"
  channel: "Meta"
  variants: ["Ad_v2_Meta_Short_HookA","Ad_v2_Meta_Short_HookB"]
  date_range: ["2025-10-17","2025-10-19"]
  metric: "CTR"
  outcome: "A تفوّق 21%"
  compliance: "✅"
  notes: "[محاكاة] الحد الأدنى للانطباعات تحقق"
```

---

## **13\) التحقق والحدود**

```
validators:
  - check_length: "limits(channel) متحقق"
  - check_guardrails: "CTA واحد، لا شراء للبارد"
  - check_disclosure: "#إعلان في البداية للمواد المرعية"
  - check_claims: "كل رقم بمصدر/نطاق أو [افتراض]"
  - output: "pass|fail + أسباب"
```

---

## **14\) ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **مولّد التركيبات:** {{K}} مرشّحين/قناة، التزام الحواجز ✅.

* **الاختبار:** A/B لمدة {{time\_bounds\_days}} أيام، المقياس الأساسي {{metric}}.

* **النتيجة/الإجراء:** فائز {{winner\_id}}؛ إعادة توليد جيل جديد مشتق \+ نشر على القنوات ذات الصلة.

**انتهى ملف 05\_testing\_optimization.md**

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
