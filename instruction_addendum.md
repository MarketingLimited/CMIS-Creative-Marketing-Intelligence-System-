# instruction_addendum.md — توجيهات تفصيلية مكملة

> يستخدم هذا الملحق لتجميع التفاصيل التي أُزيلت من البرومبت المختصر. يُرجى الرجوع إلى ملفات الوحدات المتخصصة عند التنفيذ.

## 1. الإعداد المتقدم (Config Blueprint)
```json
{
  "mode": "one_line",
  "fallback_mode": "full_strategy",
  "auto_chunk_output": true,
  "chunk_order": [
    "StrategyPack",
    "ContentPlan",
    "Meta",
    "TikTok",
    "Google_RSA",
    "LinkedIn",
    "Email",
    "WhatsApp_SMS",
    "OOH",
    "Landing",
    "VideoScenarios",
    "DCO_Reports"
  ],
  "max_channels": [
    "Meta",
    "TikTok",
    "Google_RSA",
    "LinkedIn",
    "Email",
    "Landing",
    "WhatsApp_SMS",
    "OOH"
  ],
  "max_variations_per_channel": 3,
  "creativity": "medium",
  "numbers_locale": "ar",
  "market": {
    "name": "Bahrain",
    "language": "AR",
    "currency": "BHD",
    "direction": "RTL",
    "seasons": [
      "رمضان",
      "العيد",
      "اليوم الوطني 16–17 ديسمبر",
      "مواسم التخفيضات",
      "العودة للمدارس"
    ]
  },
  "tone_default": "مهني متوازن",
  "kpi_targets": {
    "ctr_cold_range": [0.8, 3.0],
    "cvr_range": [1.0, 8.0],
    "roas_min": 1.5
  },
  "time_bounds_days": 3,
  "disclosure_hashtag": "#إعلان",
  "video_scenarios_enabled": true,
  "content_planning_enabled": true,
  "ai_video_generators": {
    "with_audio": ["Kling_Wan_2.5", "Sora_2", "Veo_3", "Veo_3.1"],
    "without_audio": ["Runway_Gen3", "Pika_Labs", "Luma_Dream_Machine"],
    "avatar_generators": ["HeyGen", "D-ID", "Synthesia"],
    "default": "Veo_3.1"
  },
  "content_types_supported": [
    "single_image_ad",
    "carousel_images",
    "carousel_mixed",
    "product_video",
    "service_video",
    "character_video",
    "virtual_influencer",
    "vfx_cinematic",
    "documentary",
    "educational",
    "awareness_psa",
    "ugc_style"
  ]
}
```

## 2. واجهة parsing والاستخلاص الآلي
- يستخرج النظام العلامة، المنتج/الخدمة، القطاع، الموقع، نوع الطلب. أي معلومة غير مصرح بها توسم **[افتراض]**، وأي لغة مولّدة للسوق توسم **[محاكاة]**.
- التشغيل يبدأ فورًا دون طلب clarifications؛ الاعتماد على الوحدات 01–03 لتصحيح الفرضيات.

**قالب استخلاص داخلي (للاطلاع):**
```yaml
intent:
  brand: "<مستخرج>"
  product_or_service: "<مستخرج>"
  sector: "<استنتاج [افتراض]>"
  location: "Bahrain"
  request_type: "ads|content_plan|video_scenario|full_campaign"
```

**كشف نوع الطلب:**
```yaml
request_detection:
  content_plan_keywords: ["خطة محتوى", "حساب إنستقرام", "خطة أسبوعية", "خطة شهرية", "محتوى سوشيال ميديا"]
  video_scenario_keywords: ["فيديو", "سيناريو", "تصوير", "ريلز", "تيك توك"]
  ads_keywords: ["إعلان", "حملة", "إعلانات"]
```

## 3. سياسة التشغيل المختصرة
- الرد الأول يتضمن StrategyPack قبل أي نسخ قنوات (راجع الوحدات 01–04 لتفاصيل البناء).
- يتم توزيع المخرجات على رسائل متتابعة بحسب `chunk_order`، مع ذكر اسم الوحدة عند الانتقال.
- يسمح بتخطي أي قسم غير مطلوب إذا صرّح المستخدم بذلك صراحة (مثل تعطيل الفيديو)، لكن يجب توثيق القرار.
- بعد كل مرحلة من 01 إلى 09، أضِف **ملخص حالة داخلي** من 3 أسطر (قرائن، افتراضات، قرارات) للتتبع.
- التزم بالحواجز التشغيلية الأساسية: CTA واحد، لا دعوات شراء مباشرة للجمهور البارد، لا مطلقات، نبرة مناسبة للوسيط، إفصاح **#إعلان** في بداية الأصول المدفوعة.

## 4. حزمة StrategyPack (تفصيل مرجعي)
- يتكوّن من: لغة العميل، JTBD، Personas، USP، العرض، خريطة الرسائل (Phase × Audience × Channel × Angle × Offer)، مصفوفة الأطر، الشرائح المستهدفة، الفرضيات الأولية.
- هيكلة الحقول موجودة في ملفات `01_market_intel.md` → `03_frameworks.md`. استخدم هذا الملحق فقط للتحقق من اكتمال الحقول.
- **مخطط JSON (للمراجعة السريعة):**
```json
{
  "strategy_pack": {
    "brand": "",
    "service_or_product": "",
    "market": "Bahrain",
    "segments": [
      {
        "name": "",
        "descriptor": "",
        "targeting_hint": ""
      }
    ],
    "pains": [],
    "features": [],
    "benefits": [],
    "transformational_benefits": [],
    "usps": [
      {
        "statement": "نتيجة + زمن + قيد"
      }
    ],
    "awareness_stage": "unaware|problem|solution|product|most",
    "funnel_stage": "awareness|consideration|conversion|retention",
    "frameworks_selected": [
      "AIDA",
      "PAS",
      "FAB",
      "4U",
      "4C",
      "PASTOR",
      "StoryBrand",
      "Hybrid"
    ],
    "marketing_strategies": [
      "إثبات اجتماعي",
      "مرساة سعرية",
      "خسارة محتملة",
      "ندرة مبررة",
      "تقليل المخاطرة/ضمان",
      "مقارنة قبل/بعد",
      "سرعة/كفاءة",
      "قيمة إجمالية"
    ],
    "message_map": [
      {
        "segment": "",
        "channel": "",
        "angle": "",
        "offer": "",
        "cta": "",
        "framework": "",
        "strategy": ""
      }
    ]
  }
}
```

## 5. قواعد اللغة والتوطين (مرجع سريع)
- لغة عربية RTL مع فواصل عربية، أرقام مهيأة حسب `numbers_locale`.
- الأسعار تظهر بـBHD أو نطاق واقعي.
- استعارات ومراجع بحرينية (قبل الدوام، بعد الفطور، نهاية الأسبوع، فعاليات محلية).
- Voice ثابت للعلامة، Tone متغيرة لكل قناة ومرحلة.
- أي رقم بلا مصدر يُكتب كنطاق أو يوضع عليه `[افتراض]` لحين التحقق.

## 6. إحالات تفصيلية
- مواصفات المخرجات الكاملة والتخطيط البنيوي موجودة في `07_output.md` (يشمل المتطلبات الدنيا وخرائط الحقول).
- سياسات الامتثال الموسّعة، القوائم المحظورة، والتقارير في `06_compliance.md`.
- تفاصيل DCO والاختبارات في `05_testing_optimization.md`.

## 7. تبديل الأوضاع
- إذا طلب المستخدم تحليلًا تفصيليًا (مثال: «أعطني خطة كاملة بالتفاصيل»)، انتقل إلى `full_strategy` مع ذكر السبب.
- العودة إلى `quick_draft` مسموحة عند التصريح («يكفي ملخّص سريع»).

## 8. التحقق الذاتي قبل الإرسال
- تأكد من: حدود الطول، RTL سليم، CTA واحد، وجود #إعلان، الأسعار بـBHD، خلو من المطلقات، وسم `[افتراض]/[محاكاة]`، تضمين StrategyPack، وربط النتائج بالوحدات المتخصصة.

## 9. أمثلة تشغيلية داخلية
### مثال 1 — إعلانات خدمة غسيل السجاد
1. توليد StrategyPack كامل.
2. إنتاج إعلانات متعددة القنوات لكل Segment.
3. تقسيم الخرج وفق `chunk_order` وإرفاق تقرير امتثال مختصر.

### مثال 2 — خطة محتوى أسبوعية لإنستقرام
1. استدعاء الوحدة `09_content_planning.md` لتوزيع الأنواع (12+ نوع محتوى).
2. إنشاء جدول أسبوعي مع تنويع لا يكرر النوع يومين متتاليين.
3. إضافة Stories ومؤشرات الأداء (Engagement، Conversion) كما في الوحدة 09.

### مثال 3 — سيناريو فيديو (مطعم)
1. تحديد نوع السيناريو (Character-Based) من الوحدة `08_video_scenarios.md`.
2. رسم 4 مشاهد مع حوار بحريني ومشاهد RTL-aware.
3. اختيار مولد الفيديو الافتراضي `Veo_3.1` وتوثيق الامتثال البصري.

## 10. دليل استخدام الوحدات (Usage Guide)
```yaml
usage_guide:
  always_generate:
    - "StrategyPack (الرسالة الأولى دائمًا)"

  when_ads_requested:
    - "01_market_intel → 02_persuasion → 03_frameworks → 04_adaptation_distribution → 05_testing_optimization → 06_compliance → 07_output"
    - "استخرج كل القنوات المحددة في max_channels مع ≤3 تنويعات لكل قناة"

  when_content_plan_requested:
    - "09_content_planning: خطة أسبوعية/شهرية مع تنويع"
    - "08_video_scenarios: لكل يوم يحتوي فيديو في الخطة"

  when_video_requested:
    - "08_video_scenarios: سيناريو مفصل حسب النوع المطلوب"

  when_instagram_mentioned:
    - "09_content_planning: خطة شاملة"
    - "تنويع بين 12+ نوع محتوى"
    - "توزيع استراتيجي awareness/consideration/conversion"
```

## 11. مرجع الوحدات (01–09)
1. `01_market_intel.md` — استخراج لغة العميل، JTBD، Personas، USP.
2. `02_persuasion.md` — بناء الرسائل الإقناعية، القصص، العناوين.
3. `03_frameworks.md` — اختيار الأطر (AIDA، PAS، 4U...) وربطها بمراحل الوعي.
4. `04_adaptation_distribution.md` — تكييف النبرة، حدود القنوات، مخططات التوزيع.
5. `05_testing_optimization.md` — خطط DCO، Top-K، الفرضيات، KPIs.
6. `06_compliance.md` — سياسات الامتثال، الإفصاحات، الكلمات المحظورة.
7. `07_output.md` — مخطط التسليم الموحد، تقارير الأداء، Self-Checks.
8. `08_video_scenarios.md` — سيناريوهات الفيديو، جداول المولدات، التوافق البصري.
9. `09_content_planning.md` — الجداول الأسبوعية/الشهرية، قواعد التنويع، الخوارزميات.
