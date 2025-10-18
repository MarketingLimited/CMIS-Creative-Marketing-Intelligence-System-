<!-- CMIS:START::MODULE_05_06 -->
# وحدتا 05 و06 — الاختبار والتحسين + الامتثال

<!-- CMIS:START::MODULE_05 -->
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
  "objective": "awareness|conversion|retention",
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

### مثال موحد: ربط الهدف التسويقي بمراحل الوعي والقُمع
> | الهدف التسويقي | مرحلة الوعي المرجحة | موقع القُمع | CTA مقترح |
> | --- | --- | --- | --- |
> | awareness | from unaware → problem-aware | TOFU | «تعرّف أكثر» أو «اكتشف القصة» |
> | conversion | from solution-aware → product-aware | MOFU/BOFU | «احجز تجربة» أو «اطلب العرض» |
> | retention | most-aware (عملاء حاليون) | Loyalty/Post-Purchase | «جدّد اشتراكك» أو «شارك مزاياك» |

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب.
2. إن وُجد `trend_research` فعّل آلية البحث وادمج الملخص والمصدر في المخرجات.
3. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات…).
4. إنتاج المخرجات وفق القالب أدناه.
5. عنون كل مخرج بحزمة **Metadata** (`knowledge_tags`, `retrieval_handles`, `version`) لتكون قابلة للاستدعاء الفوري عبر تدفقات **Gems** و**GPTs**.

<!-- CMIS:START::MIXER_STEP -->
- بعد تلخيص المدخلات، ابنِ **مصفوفات** من الحقول (تدعم تعدد القيم لكل حقل + افتراضات عند الحاجة)،
  وولّد **3 تنويعات أساسية** (v1–v3) تغطي Pain/PAS، Benefit/AIDA، Proof/FAB مع اختلاف ≥3 محاور (trigger, framework, strategy, tone, awareness/funnel).
  - إذا فُعّل وضع DCO Expansion (طلبات صريحة أو قنوات ديناميكية)، أضف مجموعة توسعة (v4+) حتى 6–12 تنويعًا مع توثيق قرار التوسعة في سجل المراجعة.
  لكل نموذج: اطبع `used_fields` و`design_description` و`compliance`.
<!-- CMIS:END::MIXER_STEP -->

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

**انتهى قسم MODULE_05 (المحتوى مدمج ضمن 05_06_testing_and_compliance.md)**

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

### مثال 1: Fintech — تحويل المدفوعات للشركات الناشئة

#### المدخلات المختصرة
```json
{
  "brand": "LuminaPay",
  "product_or_service": "منصة مدفوعات سحابية للشركات الناشئة",
  "objective": "conversion",
  "target_audience": "مديرو المالية في الشركات التقنية المبكرة",
  "channels": ["Meta", "LinkedIn", "Email"],
  "budget_bhd": 6500,
  "trend_research": {
    "topic": "B2B SaaS payments MENA",
    "language": "ar",
    "depth": "summary"
  }
}
```

#### مصفوفة الأصول الذرّية (بعد التطبيع)
```
atomic_assets:
  headlines:   ["حوّل مدفوعات شركتك الناشئة دون أكواد إضافية", "منصة دفع موحدة لفرق المالية السريعة"]
  hooks:       ["أتمتة الفوترة في 5 دقائق", "ربط Stripe وBenefitPay في لوحة واحدة"]
  bodies:      [
                  "فعّل التكامل مع BenefitPay واحصل على رؤية نقدية لحظية.",
                  "منصة LuminaPay تربط قنوات الدفع وتُخرج تقارير BHD تلقائية للمدير المالي."
               ]
  visuals:     ["Dashboard RTL مع مخطط نمو نقدي", "Video Overlay ≤8 كلمات يشرح التدفق"]
  proofs:      ["تقييم 4.8/5 خلال آخر 90 يومًا", "شراكة مصدّقة مع CBB Sandbox"]
  ctas:        ["احجز جلسة إعداد", "اطلب تجربة تجريبية"]
  offers:      ["خصم إطلاق 15% لأول 3 أشهر", "دعم توصيل API مجاني"]
normalization:
  - "إزالة المطلقات، استبدالها بنطاقات واقعية"
  - "تأكيد BHD عند أي ذكر للسعر"
  - "#إعلان في افتتاح كل أصل مدفوع"
```

#### تصميم الحواجز الحارسة واختيار الأطر
```
guardrails:
  - if: { stage: ["problem"] }
    then: { framework: ["PAS"], cta: "تجريبي", require: ["proof_layers.medium"] }
  - if: { stage: ["solution","product"] }
    then: { framework: ["AIDA","FAB"], cta: "تسعير/ديمو", require: ["pricing_terms"] }
  - always_forbid: ["مضمون", "الأفضل", "فوري"]
  - cold_no_purchase: "لا CTA شرائي لجمهور Meta البارد"
```

#### متغيرات DCO — ثلاث تنويعات أساسية + توسعة
```
dco_candidates:
  - id: "Ad_v1_Meta_Short_Pain"
    stage: "problem"
    framework: "PAS"
    hook: "#إعلان | أتمتة الفوترة في 5 دقائق"
    angle: "Pain / عبء العمل اليدوي"
    copy_short: "أوقف الجداول اليدوية. LuminaPay تجمع BenefitPay وStripe في لوحة واحدة للفرق المالية السريعة."
    cta: "اطلب تجربة تجريبية"
    proof: ["شراكة مصدّقة مع CBB Sandbox"]
    compliance: "✅"
  - id: "Ad_v2_LinkedIn_Long_Benefit"
    stage: "solution"
    framework: "AIDA"
    hook: "#إعلان | لوحة تحكم نقدية موحدة"
    angle: "Benefit / كفاءة مالية"
    copy_long: "فعّل LuminaPay لتقارير BHD فورية، تسوية تلقائية، وتنبيهات ذكية للمدير المالي. متوسط توفير الوقت 32% خلال أول شهر."
    cta: "احجز جلسة إعداد"
    proof: ["تقييم 4.8/5 خلال آخر 90 يومًا"]
    compliance: "✅"
  - id: "Ad_v3_Email_Long_Proof"
    stage: "product"
    framework: "FAB"
    hook: "#إعلان | خصم إطلاق 15%"
    angle: "Proof / ROI"
    copy_long: "اربط أنظمة الدفع دون هندسة إضافية. العملاء النشطون حققوا ROAS 1.9x بعد 45 يومًا بفضل التدفقات المؤتمتة."
    cta: "احجز جلسة إعداد"
    proof: ["تقييم 4.8/5", "ROAS 1.9x (افتراض يُستبدل بتقرير)"]
    compliance: "⚠️ يتطلب توثيق ROAS"
  - id: "Ad_v4_Meta_Short_Expansion"
    stage: "solution"
    framework: "StoryBrand"
    angle: "Expansion / Narrative"
    copy_short: "#إعلان | تخيّل لوحة دفع واحدة لكل عميلك. LuminaPay ينسّق المدفوعات ويغلق الفوترة المتأخرة."
    cta: "اطلب تجربة تجريبية"
    proof: ["متوسط زمن التحصيل 5 أيام (افتراض)"]
    compliance: "⚠️ استبدل الافتراض بدليل"
```

#### خطة التجربة واختبارات الترقي
```
experiment:
  hypothesis:
    variable: "Hook رقمي مقابل سردي"
    change: "استبدال hook رقمي بنبرة قصصية على Meta"
    expected_outcome: "زيادة CTR بنسبة 18% خلال 3 أيام"
    stage: "problem"
    channel: "Meta"
    primary_metric: "CTR"
  design: "A/B"
  traffic_split: "50/50"
  duration_days: 3
  sample_min: 300 impressions/variant
  early_stop_rules:
    - "CTR أقل من 0.25% بعد 24 ساعة → إيقاف"
    - "🚫 الامتثال → إيقاف فوري"
  promotion_rule: "فارق ≥12% CTR بثقة اتجاه يومين"
```

#### سجل الامتثال الآلي
```
compliance_log:
  - variant_id: "Ad_v3_Email_Long_Proof"
    status: "⚠️"
    issue: "إشارة ROAS بحاجة إلى مصدر موثق"
    auto_fix: "أضف نطاق 1.4x–1.9x مع [افتراض] واضح"
  - variant_id: "Ad_v4_Meta_Short_Expansion"
    status: "⚠️"
    issue: "Hook قصصي بلا دليل رقمي"
    recommendation: "أضف إثبات اجتماعي أو دراسة حالة"
summary_label:
  status: "✅ جزئي"
  notes: "تم تمرير الحواجز النصية والخصوصية، بانتظار مستند ROAS"
  timestamp: "2025-01-18T10:15:00+03:00"
```

### مثال 2: Hospitality — حملة ولاء فندقي

*المدخلات المختصرة:* برنامج ولاء لفنادق فاخرة يستهدف عملاء متكررين (stage = most-aware)، القنوات Email + WhatsApp.

*مقتطف DCO:* توليد رسالتين Email (`FAB` و`4U`) مع CTA واحد «جدّد اشتراكك الآن»، وضمان «إقامة ثالثة بنصف السعر» مع إثبات «متوسط تقييم 4.9/5 (آخر 60 يومًا)».

*اختبار مقترح:* MVT محدود (CTA wording × Proof snippet) بشرط تجاوز 8,000 مستلم نشط، مع قاعدة إيقاف عند CTR < 1.2%.

*الامتثال:* تذكير بضرورة إدراج رابط إلغاء الاشتراك العربي، والتأكيد على حماية بيانات برنامج الولاء وفق سياسة الخصوصية أعلاه.

**انتهى قسم MODULE_05 (المحتوى مدمج ضمن 05_06_testing_and_compliance.md)**
<!-- CMIS:START::REFS_QUALITY -->
### مراجع الجودة والامتثال
- راجع `support_and_templates.md §QUALITY_AND_VARIATIONS` قبل الإخراج النهائي.
- طبّق قواعد `support_and_templates.md §QUALITY_AND_VARIATIONS` عند توليد تنويعات.
<!-- CMIS:END::REFS_QUALITY -->
<!-- CMIS:END::MODULE_05 -->

<!-- CMIS:START::MODULE_06 -->
<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- طبقة امتثال وأمان تُراجع كل أصل إعلاني نصيًا وبصريًا قبل التسليم، بسوق افتراضي **مملكة البحرين** (AR/RTL، عملة BHD)، مع تقارير ✅/⚠️/🚫 قابلة للنسخ.
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
  "asset": {
    "channel": "Meta|Google|TikTok|LinkedIn|Email|Landing|OOH|UGC|WhatsApp_SMS|Radio_Podcast|AppStore",
    "awareness_stage": "unaware|problem|solution|product|most",
    "text": { "hook": "", "short": "", "long": "", "cta": "", "proof": [] },
    "visuals": { "type": "image|video|carousel", "overlay": "", "notes": "" },
    "pricing": { "currency": "BHD", "price": null, "terms": "" },
    "disclosure": "#إعلان"
  },
  "constraints": { "forbidden_words": [], "claims_to_avoid": [] }
}
```
<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب.
2. إن وُجد `trend_research` فعّل آلية البحث وادمج الملخص والمصدر في المخرجات.
3. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات…).
4. عند طلب أصل إعلاني مرئي يتضمن فيديو (`asset.visuals.type = "video"` أو أي تسليم فيديو)، فعّل وحدة `08_09_video_and_content.md §MODULE_08` والتزم بكل تعليماتها الخاصة بالمشاهد، السرد، الامتثال، وميثاق الصوت.
5. إنتاج المخرجات وفق القالب أدناه.
6. أرفق نتيجة المراجعة بحقول **Metadata موحدة** (`knowledge_tags`, `retrieval_handles`, `decision_owner`) لضمان ظهورها في مكتبة **Gems/GPTs** ضمن لحظة الطلب.

### المحتوى الأصلي الكامل (منسوخ حرفيًا)
## **مبادئ أساسية**

* صدق ووضوح، لا وعود مطلقة: **ممنوع** «مضمون/فوري/الأفضل/الأرخص» دون دليل مستقل وحديث.

* شفافية سعر/مدّة/شروط العرض عند الذكر (بالـBHD).

* خصوصية: موافقة صريحة، غرض محدد، حق الإلغاء، عدم مشاركة دون إذن.

* إفصاح **\#إعلان** في البداية للنشر المدفوع والـUGC برعاية.

* CTA واحد، لا شراء مباشر لجمهور بارد.

* RTL سليم، فواصل عربية، احترام الأعراف الثقافية (تمثيل معاصر غير نمطي).

---

## **سياسة الخصوصية والبيانات — البحرين**

```
privacy:
  lawful_basis: ["موافقة صريحة","تنفيذ عقد","مصلحة مشروعة مُبرّرة"]
  consent:
    wording: "بتسجيلك، توافق على استلام تحديثات تسويقية ويمكنك إلغاء الاشتراك في أي وقت."
    capture: "Checkbox غير مُؤشر مسبقًا"
  retention: "حدد مدة الاحتفاظ بالبيانات"
  rights: ["سحب الموافقة","الوصول","التصحيح","المحو"]
  minors: "عدم استهداف دون 13 عامًا؛ تحقّق عمر واضح"
  email_sms:
    unsubscribe: "رابط/تعليمات إلغاء سهلة ومرئية"
```

---

## **الإفصاحات (Disclosures)**

```
disclosures:
  paid: "#إعلان" في أول السطر/أول 3 ثوانٍ فيديو (نص+صوت)
  affiliate: "#رابط_تسويقي" عند اقتسام عمولة
  health_finance: "إخلاء مسؤولية واقعي: النتائج قد تختلف"
```

---

## **سياسة الادّعاءات (Claims)**

* أي رقم/نسبة/مدة \= **مصدر** أو **نطاق** أو **\[افتراض\]** موسوم يستبدل لاحقًا بدليل.

* أمثلة صياغات مقبولة: «عادةً خلال 7 أيام»، «في أغلب الحالات»، «متوسط تقييم 4.7/5 خلال آخر 90 يومًا».

* **محظور:** «100% مضمون»، «نتائج فورية»، «الأفضل بلا منازع»… إلخ.

### **طبقات البرهان (Proof Layers)**

```
proof_layers:
  light:   "اقتباس عميل/UGC"
  medium:  "رقم موثق/لقطة شاشة/تقييم بتاريخ حديث"
  heavy:   "دراسة حالة/شهادة اعتماد/تقرير مستقل"
```

---

## **قطاعات حساسة — صيغ مقيّدة**

```
sensitive:
  finance:
    do:   ["نطاق عوائد/مخاطر","تحذير: النتائج تختلف"]
    dont: ["عائد مضمون","نسب ثابتة بلا مصدر"]
  health_nutrition:
    do:   ["مصادر طبية معترف بها","لا ادعاءات علاجية"]
    dont: ["شفاء فوري","مقارنات علاجية مضللة"]
  employment_real_estate:
    do:   ["لغة غير تمييزية","شروط واضحة"]
    dont: ["وعود توظيف مضمونة","تفضيل تمييزي"]
  minors:
    do:   ["استبعاد دون 13","عدم جمع بيانات دون إذن ولي الأمر"]
    dont: ["استمالة مباشرة للأطفال"]
```

---

## **معايير بصرية/تصويرية — البحرين**

* تمثيل معاصر غير نمطي، احترام الخصوصية والملابس الملائمة للسياق.

* لا إيحاءات أو صور صادمة؛ لا استغلال ديني/وطني.

* تباين لوني ≥ 4.5:1؛ نص Overlay ≤ 8 كلمات؛ نقطة تركيز واحدة.

---

## **حواجز الحراسة النصية (Regex مبسّط)**

```
text_sanitizer:
  forbidden_exact: ["مضمون","فوري","الأفضل","الأرخص","مضمون 100%","نتائج فورية"]
  replace_rules:
    - find: "\\b(مضمون|مكفول)\\b"
      replace: "ضمن الضمان المحدد"
    - find: "\\b(فوري|حالاً)\\b"
      replace: "عادةً خلال {{range}}"
    - find: "\\b(الأفضل|الأرخص)\\b"
      replace: "ضمن الأفضل في الفئة وفق مراجعة مستقلة [مصدر]"
```

---

## **سياسات المنصات (ملخّص عملي)**

```
platforms:
  Meta:
    must: ["#إعلان في البداية","لا نصوص مضللة","زر واحد"]
    ban:  ["ادعاءات صحية مبالغ فيها","قبل/بعد صادم","خصائص شخصية حساسة"]
  Google_Ads:
    must: ["شفافية الأسعار والشروط","مطابقة صفحة الهبوط","علامات ترقيم سليمة"]
    ban:  ["Clickbait","مبالغات غير قابلة للتحقق","علامات ترقيم مبالغ فيها !!!"]
  TikTok:
    must: ["إفصاح واضح","عدم تضليل","صوت/نص مفهوم دون ضجيج"]
    ban:  ["محتوى بالغ/صادم","أدوية/أسلحة","ادعاءات نتائج فورية"]
  LinkedIn:
    must: ["نبرة مهنية","قيمة أعمال واضحة","مصادر"]
    ban:  ["استفزاز شخصي","مقارنات جارحة"]
```

---

## **التحقق الآلي (Validators)**

```
validators:
  check_disclosure: "وجود #إعلان في البداية للمواد المرعية"
  check_length: "مطابقة حدود القناة"
  check_claims: "مصدر/نطاق/وَسم [افتراض] لأي رقم"
  check_guardrails: ["CTA واحد","لا شراء للبارد","ممنوع المطلقات"]
  check_privacy: "وجود نص موافقة واضح عند جمع بيانات"
  check_visual: "تباين ≥ 4.5, Overlay ≤ 8 كلمات, تمثيل غير نمطي"
```

---

## **تقرير الامتثال (JSON Schema)**

```json
{
  "compliance_report": {
    "market": "Bahrain",
    "channel": "Meta",
    "status": "✅|⚠️|🚫",
    "issues": [
      { "type": "disclosure", "message": "أضف #إعلان في البداية" },
      { "type": "claim", "message": "استبدل 'فوري' بـ 'عادةً خلال 7 أيام'" }
    ],
    "fix_suggestions": [
      "CTA واحد بدل زرين",
      "أضف نطاق زمني للنتيجة"
    ],
    "sanitized_copy": { "hook": "", "short": "", "long": "", "cta": "" },
    "proof_required": ["تقييم آخر 90 يومًا", "سعر BHD واضح"],
    "privacy": { "consent_text": "بتسجيلك، توافق على استلام تحديثات تسويقية ويمكنك الإلغاء في أي وقت." },
    "final_mark": "✅"
  }
}
```

---

## **معالجات فورية (Auto-Fixes)**

```
auto_fixes:
  - rule: "غياب #إعلان"
    action: "إضافة الوسم أول النص/الفيديو"
  - rule: "CTAان أو أكثر"
    action: "اختيار الأقوى وفق المرحلة والاحتفاظ بواحد"
  - rule: "مطلقات محظورة"
    action: "استبدال تلقائي وفق text_sanitizer.replace_rules"
  - rule: "سعر بلا عملة"
    action: "إضافة BHD وتوضيح الشروط"
```

---

## **إخراج مختصر للبطاقة (Label)**

```
label:
  status: "✅"
  notes: "مطابق للبحرين/RTL/CTA واحد/دليل كافٍ"
  timestamp: "{{iso_date}}"
```

---

## **ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **الحالة:** {{status}}؛ المخالفات: {{n}} بنود.

* **الإصلاحات المطبقة:** {{auto\_fixes\_applied}}.

* **متطلبات الدليل المتبقية:** {{proof\_required}}.

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

### مثال: تدقيق أصل مرئي لحملة عقارية فاخرة

#### ملخص الطلب
- **العلامة:** "Sama Residences" — شقق فاخرة في المنامة.
- **القناة:** Meta Reels (فيديو 20 ثانية).
- **الهدف:** Conversion — حجز جولة افتراضية.
- **الجمهور:** مستثمرون من الخليج (stage = solution-aware).

#### فحص الامتثال النصي
```
original_copy:
  hook: "نتائج فورية مع أفضل عوائد في البحرين!"
  body: "استثمر الآن لتحصل على أرباح مضمونة بنسبة 12%"
  cta: "احجز وحدتك"
checks:
  - rule: "مطلقات محظورة"
    status: "🚫"
    action: "استبدال 'نتائج فورية' بـ 'نتائج متوقعة خلال 12–18 شهرًا'"
  - rule: "CTA واحد مناسب للمرحلة"
    status: "⚠️"
    action: "تحويل CTA إلى 'احجز جولة افتراضية'"
  - rule: "إفصاح #إعلان"
    status: "⚠️"
    action: "إضافة الوسم في أول 2 ثانية مع تعليق صوتي"
```

#### فحص الامتثال البصري
```
visual_review:
  type: "video"
  overlay_words: 11
  contrast_ratio: 4.8
  findings:
    - "خفض نص الـOverlay إلى ≤8 كلمات"
    - "تبديل المشهد الذي يُظهر وعود العائد بخط عريض إلى جرافيك يحتوي نطاق 8%–12% مع مصدر Deloitte"
    - "تأكيد ظهور إفصاح #إعلان نصيًا وصوتيًا عند الثانية الأولى"
  video_action: "فعّل وحدة MODULE_08 لإعادة بناء اللقطات وتوزيع الزوايا"
```

#### مخرجات المراجعة (مقتطف JSON)
```json
{
  "status": "⚠️",
  "issues": [
    { "type": "claim", "message": "أزل عبارة 'مضمونة' وأضف نطاقًا موثقًا" },
    { "type": "cta", "message": "استبدل CTA بشرط عدم الشراء المباشر" },
    { "type": "disclosure", "message": "أضف #إعلان في أول الشاشة" }
  ],
  "sanitized_copy": {
    "hook": "#إعلان | نطاق عوائد 8–12% مع عقار فاخر في المنامة",
    "body": "انضم إلى جولة افتراضية واكتشف كيف تدير Sama Residences الإيجارات عبر منصة ذكية",
    "cta": "احجز جولة افتراضية"
  },
  "proof_required": ["تقرير تقييم مستقل خلال آخر 6 أشهر"],
  "promotion_ready": false
}
```

#### توصيات لاحقة للمسوق
- ربط الحملة بتجربة MVT صغيرة (CTA بصيغة «استكشف خيارات التمويل» مقابل «احجز جولة افتراضية» بعد التصحيح).
- مزامنة النص المعدّل مع قوالب البريد الإلكتروني وصفحة الهبوط لضمان اتساق الوعد التسويقي.
- أرشفة المراجعة في `Experiment Log` مع وسم القطاع = `employment_real_estate` لتغذية التعلّم التنبّئي.

**انتهى قسم MODULE_06 (المحتوى مدمج ضمن 05_06_testing_and_compliance.md)**
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
  "metadata": {
    "knowledge_tags": ["module_05_06", "dco", "compliance"],
    "retrieval_handles": ["gems::dco_testing", "gpt::compliance_guard"],
    "version": "05_06.v1"
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

<!-- CMIS:START::REFS_QUALITY -->
### مراجع الجودة والامتثال
- راجع `support_and_templates.md §QUALITY_AND_VARIATIONS` قبل الإخراج النهائي.
- طبّق قواعد `support_and_templates.md §QUALITY_AND_VARIATIONS` عند توليد تنويعات.
<!-- CMIS:END::REFS_QUALITY -->
<!-- CMIS:END::MODULE_06 -->

<!-- CMIS:END::MODULE_05_06 -->
