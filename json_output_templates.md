<!-- CMIS:START::JSON_TEMPLATES -->
# قوالب JSON
<!-- CMIS:START::JSON_TEMPLATES_2025 -->
### Strategy Pack Template 2025
```json
{
  "brand": "",
  "objective": "",
  "primary_kpi": "",
  "segments": [
    {"name": "", "insight": "", "priority": 1}
  ],
  "value_proposition": "",
  "key_messages": [
    {"stage": "awareness", "message": ""}
  ],
  "offer_details": {"type": "", "value": ""},
  "channels": ["Meta", "TikTok"],
  "timeline_weeks": 4,
  "trend_insights": ["AI_personalization", "shoppable_video"]
}
```

### Ad Output Template 2025
```json
{
  "channel": "Meta",
  "format": "video",
  "media_type": "reel_9x16|static_4x5|carousel|story",
  "hook": "",
  "body_copy": "",
  "cta": "",
  "disclosure": "#إعلان",
  "offer": {"value": "", "currency": "BHD"},
  "marketing_framework": "PAS|AIDA|FAB|4U|StoryBrand|PASTOR",
  "marketing_strategy": ["UGC", "Offer-led"],
  "awareness_stage": "unaware|problem|solution|product|most",
  "funnel_stage": "TOFU|MOFU|BOFU",
  "transformational_benefit": "",
  "usp_reference": "",
  "message_map": {
    "hook": "",
    "body": "",
    "proof": "",
    "cta": ""
  },
  "design_trend": "Bold_Minimalism",
  "audio_trend": "Interactive_Audio",
  "design_description": {
    "composition": "",
    "background": "",
    "lighting": "",
    "colors": [],
    "focus": "",
    "de_emphasize": "",
    "element_positions": {
      "logo": "",
      "headline": "",
      "supporting_copy": "",
      "cta": "",
      "price": "",
      "text_overlay": ""
    },
    "ratio": "1:1|4:5|9:16",
    "motion": "static|subtle|dynamic"
  },
  "compliance": {
    "status": "✅|⚠️|🚫",
    "disclosure_hashtag": true,
    "rtl_layout": true,
    "single_cta": true,
    "currency_format": "BHD",
    "text_overlay_words": 0,
    "claims_clean": true,
    "notes": ""
  }
}
```

### Video Scenario Template 2025
```json
{
  "template_id": "product_showcase_basic",
  "duration_seconds": 15,
  "scenes": [
    {"order": 1, "visual_prompt": "", "overlay_text": "", "sfx": ""}
  ],
  "voiceover_ar": "#إعلان ...",
  "cta_text": "",
  "interaction_elements": [
    {"type": "link", "label": "اطلب الآن", "url": "https://"}
  ]
}
```

### Content Plan Template 2025 (Weekly)
```json
{
  "plan_type": "weekly",
  "brand": "",
  "goal": "",
  "weeks": [
    {
      "week_number": 1,
      "themes": [""],
      "posts": [
        {
          "day": "Sunday",
          "channel": "Instagram",
          "format": "Reel",
          "objective": "awareness",
          "platform_specific_guidelines": "استخدم نص شاشة RTL مختصر"
        }
      ]
    }
  ]
}
```

### Content Plan Template 2025 (Monthly)
```json
{
  "plan_type": "monthly",
  "brand": "",
  "goal": "",
  "months": [
    {
      "month": "March",
      "focus": "Ramadan Readiness",
      "campaigns": [
        {
          "name": "Seasonal Offers",
          "channels": ["Meta", "TikTok"],
          "platform_specific_guidelines": "أضف #إعلان صوتياً وبصرياً في أول 3 ثوانٍ"
        }
      ]
    }
  ]
}
```
<!-- CMIS:END::JSON_TEMPLATES_2025 -->

<!-- CMIS:START::JSON_TEMPLATES_QA_2025 -->
### إضافات مرحلة 3 (جودة/تنويع/امتثال)
```json
{
  "variation_metadata": {
    "hook_id": "H-###",
    "framework": "PAS|AIDA|FAB|4U|PASTOR",
    "angle": "pain|benefit|proof|offer|story",
    "tone": "urgent|positive|confident|educational",
    "visual_style": "bold_minimalism|metallics|grain|neo_classic_futurism|motion",
    "audio_variant": "voice_gender/accent/music_sfx",
    "community_type": "ugc|egc|brand",
    "interactivity": "direct_cta|question|shop",
    "media_type": "static_1x1|static_4x5|reel_9x16|carousel|story",
    "marketing_strategy": "UGC|Offer-led|Educational|Social_proof",
    "awareness_stage": "unaware|problem|solution|product|most",
    "funnel_stage": "TOFU|MOFU|BOFU",
    "transformational_benefit": "",
    "usp_reference": "",
    "message_map": "Hook>Body>Proof>CTA",
    "distinct_axes": ["framework", "tone", "visual_style"]
  },
  "compliance_report_schema_ref": "support_and_templates.md §QUALITY_AND_VARIATIONS — مخطط تقرير الامتثال (JSON)"
}
```

<!-- CMIS:END::JSON_TEMPLATES_QA_2025 -->
<!-- CMIS:END::JSON_TEMPLATES -->

<!-- CMIS:START::MODULE_07_OUTPUT -->
# الوحدة 07: الإخراج
<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- إخراج النتائج النهائية بصيغ منظّمة وجاهزة للعرض/النسخ/التصدير، مع قوالب تقارير ومخططات JSON، وتسميات تصديرية موحّدة. سوق افتراضي: **مملكة البحرين** (AR/RTL، عملة **BHD**).
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

<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب.
2. إن وُجد `trend_research` فعّل آلية البحث وادمج الملخص والمصدر في المخرجات.
3. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات…).
4. إنتاج المخرجات وفق القالب أدناه.

### المحتوى الأصلي الكامل (منسوخ حرفيًا)
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
      "design_description": {
        "composition": "",
        "background": "",
        "lighting": "",
        "colors": [],
        "focus": "",
        "de_emphasize": "",
        "element_positions": {
          "logo": "",
          "headline": "",
          "supporting_copy": "",
          "cta": "",
          "price": "",
          "text_overlay": ""
        },
        "ratio": "1:1|4:5|9:16",
        "motion": "static|subtle|dynamic"
      },
      "compliance": {
        "status": "✅|⚠️|🚫",
        "disclosure_hashtag": true,
        "rtl_layout": true,
        "single_cta": true,
        "currency_format": "BHD",
        "text_overlay_words": 0,
        "claims_clean": true,
        "notes": ""
      }
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
  "design_description": {
    "composition": "",
    "background": "",
    "lighting": "",
    "colors": [],
    "focus": "",
    "de_emphasize": "",
    "element_positions": {
      "logo": "",
      "headline": "",
      "supporting_copy": "",
      "cta": "",
      "price": "",
      "text_overlay": ""
    },
    "ratio": "1:1|4:5|9:16",
    "motion": "static|subtle|dynamic"
  },
  "primary_metric": "CTR|CVR|ROAS|HookRate",
  "naming": "Ad_v{n}_{Channel}_{Len}_{HookID}",
  "compliance": {
    "status": "✅|⚠️|🚫",
    "disclosure_hashtag": true,
    "rtl_layout": true,
    "single_cta": true,
    "currency_format": "BHD",
    "text_overlay_words": 0,
    "claims_clean": true,
    "notes": "سبب العلامة أو أي استثناء"
  },
  "notes": "لماذا هذا الإطار/هذه النبرة لهذه المرحلة"
}
```

### **متطلبات إضافية لوضع One-Line**

- حد أقصى ثلاث تنويعات لكل قناة (v1/v2/v3 Hybrid عند الحاجة).
- إن وُجدت شرائح متعددة، أخرج نسخة واضحة لكل Segment مع تسمية.
- أرفق وصف التصميم التفصيلي (`design_description`) الذي يشمل: `composition`, `background`, `lighting`, `colors`, `focus`, `de_emphasize`, `element_positions`, `ratio`, `motion`.
- احرص على أن تشمل كل حزمة قناة تقرير امتثال تفصيلي (`compliance`) يغطي الوسم، RTL، CTA واحد، تنسيق العملة، وعدد كلمات النص البصري (≤8 كلمات)، وأي ملاحظات تصحيحية، إضافة إلى نسخة `sanitized_copy` عند التصحيح.
- فعّل متطلبات DCO والاختبارات من `05_testing_optimization.md`: مرشحون K≤3 لكل قناة، فرضية A/B لمدة 3 أيام، مقياس أساسي مع تقرير متابعة.
- التزم بتسمية التصدير `Ad_v{n}_{Channel}_{Len}_{HookID}` لتجميع الحزم وإرسالها.

### **مخطط موسّع لعنصر الإعلان (Mapping كامل)**

```json
{
  "channel": "Meta|TikTok|Google_RSA|LinkedIn|Email|Landing|WhatsApp_SMS|OOH",
  "segment": "",
  "awareness_stage": "",
  "funnel_stage": "",
  "framework": "",
  "marketing_strategy": "",
  "tone": "",
  "copy": {
    "hook": "",
    "short": "",
    "long": "",
    "cta": "",
    "proof": []
  },
  "mapping": {
    "pains": ["…"],
    "features": ["…"],
    "benefits": ["…"],
    "transformational_benefits": ["…"],
    "usp": "…"
  },
  "primary_metric": "CTR|CVR|ROAS|HookRate",
  "design_description": {
    "composition": "",
    "background": "",
    "lighting": "",
    "colors": [],
    "focus": "",
    "de_emphasize": "",
    "element_positions": {
      "logo": "",
      "headline": "",
      "supporting_copy": "",
      "cta": "",
      "price": "",
      "text_overlay": ""
    },
    "ratio": "1:1|4:5|9:16",
    "motion": "static|subtle|dynamic"
  },
  "compliance": {
    "status": "✅|⚠️|🚫",
    "disclosure_hashtag": true,
    "rtl_layout": true,
    "single_cta": true,
    "currency_format": "BHD",
    "text_overlay_words": 0,
    "claims_clean": true,
    "notes": ""
  },
  "naming": "Ad_v{n}_{Channel}_{Len}_{HookID}"
}
```

### **التحقق الذاتي قبل التسليم**

- تأكد من أن كل أصل يبدأ بـ **#إعلان** عند الحاجة وأن الأسعار تظهر بـ **BHD** أو كنطاق موثق.
- راجع حدود الطول الخاصة بكل قناة (≤4 أسطر للنص الرئيسي في Meta/TikTok، حد الأحرف الرسمي لعناوين وأوصاف Google RSA، ≤100 حرف لـWhatsApp/SMS).
- تحقق من وجود CTA واحد فقط لكل أصل وتطابقه مع مرحلة الوعي والقمع المحددة في `strategy_pack`.
- علّم أي بيانات غير مؤكدة بـ`[افتراض]` وأعد صياغة الكلمات المحظورة («مضمون»، «فوري»، «الأفضل»، «الأرخص») قبل تمرير الأصل إلى `06_compliance.md`.
- حافظ على الربط بين كل أصل وشرائحه (`segment` + `pains/features/benefits/transformational/usp`) وسَمِّ الملفات وفق النمط `Ad_v{n}_{Channel}_{Len}_{HookID}` قبل التصدير.


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
          "short": "#إعلان تكلفة الاكتساب ترتفع؟ اختبر 2–3 زوايا خلال 10 دقائق.",
          "long": "#إعلان تكتب إعلانات ولا ترى تحويلًا؟ CMIS يولّد 8 نسخ قابلة للاختبار بالعربية (RTL) مع إثبات وتضمين BHD. ابدأ الآن بنسخة تجريبية.",
          "cta": "ابدأ التجربة المجانية الآن — بدون بطاقة.",
          "proof": ["[محاكاة] تقييم 4.7/5 خلال 90 يومًا"]
        },
        "design_description": {
          "composition": "واجهة منصة CMIS تظهر على لابتوب بيد شخص يعمل من مقهى.",
          "background": "بيئة مقهى مضاءة طبيعيًا مع ضبابية خفيفة.",
          "lighting": "إضاءة دافئة من اليمين تبرز الشاشة.",
          "colors": ["#0B1B3A", "#F5C542", "#FFFFFF"],
          "focus": "شاشة اللابتوب وCTA أسفلها.",
          "de_emphasize": "الرواد في الخلفية بخلفية ضبابية.",
          "element_positions": {
            "logo": "أعلى اليمين مع ظل بسيط.",
            "headline": "منتصف يسار فوق الشاشة.",
            "supporting_copy": "أسفل العنوان بخط أوضح.",
            "cta": "زر ذهبي أسفل الشاشة مباشرةً.",
            "price": "شريط سفلي صغير يعرض 14.9 BHD.",
            "text_overlay": "اختبر 3 زوايا خلال 10 دقائق"
          },
          "ratio": "4:5",
          "motion": "static"
        },
        "primary_metric": "CTR",
        "naming": "Ad_v2_Meta_Short_HookA",
        "compliance": {
          "status": "✅",
          "disclosure_hashtag": true,
          "rtl_layout": true,
          "single_cta": true,
          "currency_format": "BHD",
          "text_overlay_words": 5,
          "claims_clean": true,
          "notes": ""
        },
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

### مجموعة تنويعات اختبار (Stage B Format Check)

- الهدف: التحقق من ملء جميع الحقول الجديدة (`design_description`, `compliance`) مع ضبط نص الشاشة ≤ 8 كلمات.

```json
[
  {
    "variant_id": "v1",
    "channel": "Meta",
    "framework": "AIDA",
    "awareness_stage": "problem",
    "tone": "واثقة",
    "copy": {
      "hook": "#إعلان ميزانيتك الإعلانية تحتاج اختبارًا أسرع.",
      "short": "جرّب CMIS لاختيار 3 زوايا عربية خلال 10 دقائق مع تتبع تلقائي.",
      "long": "#إعلان وفّر الوقت وقلّل الهدر باختبارات CMIS: لوحات RTL، أسعار BHD، ونصوص جاهزة للحملات في يوم واحد.",
      "cta": "ابدأ التجربة المجانية الآن.",
      "proof": ["[افتراض] 500+ حملة خليجية"]
    },
    "design_description": {
      "composition": "لقطة عمودية لمسوّق يستخدم لابتوب مع واجهة CMIS واضحة.",
      "background": "مكتب حديث بألوان محايدة مع نبات أخضر باهت.",
      "lighting": "إضاءة طبيعية من نافذة جانبية تبرز الوجه والشاشة.",
      "colors": ["#0B1B3A", "#F7F4EC", "#F5C542"],
      "focus": "الواجهة على الشاشة وزر CTA.",
      "de_emphasize": "الكماليات المكتبية على اليسار بخلفية ضبابية.",
      "element_positions": {
        "logo": "أعلى اليمين داخل شارة بيضاء.",
        "headline": "منتصف علوي بخط سميك.",
        "supporting_copy": "أسفل العنوان بمحاذاة RTL.",
        "cta": "زر ذهبي أسفل منتصف الشاشة.",
        "price": "يسار الزر بخط أصغر يوضح 14.9 BHD.",
        "text_overlay": "اختبر أسرع خلال دقيقة"
      },
      "ratio": "4:5",
      "motion": "static"
    },
    "primary_metric": "CTR",
    "compliance": {
      "status": "✅",
      "disclosure_hashtag": true,
      "rtl_layout": true,
      "single_cta": true,
      "currency_format": "BHD",
      "text_overlay_words": 4,
      "claims_clean": true,
      "notes": ""
    },
    "notes": "تنويع رئيسي لبداية الحملة." 
  },
  {
    "variant_id": "v2",
    "channel": "TikTok",
    "framework": "StoryBrand",
    "awareness_stage": "solution",
    "tone": "مشوقة",
    "copy": {
      "hook": "#إعلان هل تتكرر أفكارك على TikTok؟",
      "short": "حوّل الأفكار إلى سيناريوهات فيديو بخطوات عربية سهلة ومؤشرات Hook جاهزة.",
      "long": "#إعلان CMIS يبني لك لوحة محتوى TikTok: سيناريوهات RTL، CTA واحد، وتحليل أداء تلقائي خلال 48 ساعة.",
      "cta": "صمّم سيناريو TikTok الآن.",
      "proof": ["[افتراض] رفع معدل المشاهدة 28%"]
    },
    "design_description": {
      "composition": "لقطات متتابعة لمصممة محتوى تمسك الهاتف وتستعرض القصص المصغّرة.",
      "background": "استوديو منزلي بإضاءة RGB خافتة وخلفية بنفسجية.",
      "lighting": "إضاءة حلقية أمامية مع شرائط LED خلفية متحركة.",
      "colors": ["#1B1B3F", "#7A5CFF", "#F9F871"],
      "focus": "الهاتف والشاشة التي تعرض واجهة سيناريو.",
      "de_emphasize": "الأثاث الجانبي مع عزل عمق.",
      "element_positions": {
        "logo": "أعلى اليسار بنسخة شفافة.",
        "headline": "وسط أعلى بخط عريض.",
        "supporting_copy": "سطر واحد تحت العنوان.",
        "cta": "زر نابض في الأسفل يمين.",
        "price": "تمرير نصي سفلي يظهر العرض.",
        "text_overlay": "وفر 30% هذا الأسبوع"
      },
      "ratio": "9:16",
      "motion": "dynamic"
    },
    "primary_metric": "HookRate",
    "compliance": {
      "status": "✅",
      "disclosure_hashtag": true,
      "rtl_layout": true,
      "single_cta": true,
      "currency_format": "BHD",
      "text_overlay_words": 4,
      "claims_clean": true,
      "notes": ""
    },
    "notes": "تنويع فيديو قصير مع حركة مستمرة." 
  }
]
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
      "design_description": {
        "composition": "واجهات لوحية متداخلة تعرض عناوين بحث متعددة.",
        "background": "خلفية فاتحة بنمط نقطي خفيف.",
        "lighting": "إضاءة استديو متوازنة بلا ظلال قاسية.",
        "colors": ["#FFFFFF", "#1B2735", "#0094FF"],
        "focus": "مربعات العناوين الرئيسية في المنتصف.",
        "de_emphasize": "الهوامش الفارغة والديكور الخلفي.",
        "element_positions": {
          "logo": "أعلى اليسار داخل شريط شفاف.",
          "headline": "منتصف أعلى مع محاذاة RTL.",
          "supporting_copy": "أسفل العنوان مباشرةً في عمود واحد.",
          "cta": "زر أزرق في الأسفل بامتداد العرض.",
          "price": "يمين الزر بخط أصغر.",
          "text_overlay": "ضاعف نقراتك الذكية"
        },
        "ratio": "1:1",
        "motion": "static"
      },
      "primary_metric": "CTR",
      "naming": "Ad_v1_Google_RSA_IntentX",
      "compliance": {
        "status": "⚠️",
        "disclosure_hashtag": true,
        "rtl_layout": true,
        "single_cta": true,
        "currency_format": "BHD",
        "text_overlay_words": 3,
        "claims_clean": false,
        "notes": "يجب إرفاق مصدر للتقييم"
      },
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

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

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
      "design_description": {
        "composition": "",
        "background": "",
        "lighting": "",
        "colors": [],
        "focus": "",
        "de_emphasize": "",
        "element_positions": {
          "logo": "",
          "headline": "",
          "supporting_copy": "",
          "cta": "",
          "price": "",
          "text_overlay": ""
        },
        "ratio": "1:1|4:5|9:16",
        "motion": "static|subtle|dynamic"
      },
      "compliance": {
        "status": "✅|⚠️|🚫",
        "disclosure_hashtag": true,
        "rtl_layout": true,
        "single_cta": true,
        "currency_format": "BHD",
        "text_overlay_words": 0,
        "claims_clean": true,
        "notes": ""
      }
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
  "design_description": {
    "composition": "",
    "background": "",
    "lighting": "",
    "colors": [],
    "focus": "",
    "de_emphasize": "",
    "element_positions": {
      "logo": "",
      "headline": "",
      "supporting_copy": "",
      "cta": "",
      "price": "",
      "text_overlay": ""
    },
    "ratio": "1:1|4:5|9:16",
    "motion": "static|subtle|dynamic"
  },
  "primary_metric": "CTR|CVR|ROAS|HookRate",
  "naming": "Ad_v{n}_{Channel}_{Len}_{HookID}",
  "compliance": {
    "status": "✅|⚠️|🚫",
    "disclosure_hashtag": true,
    "rtl_layout": true,
    "single_cta": true,
    "currency_format": "BHD",
    "text_overlay_words": 0,
    "claims_clean": true,
    "notes": "سبب العلامة أو أي استثناء"
  },
  "notes": "لماذا هذا الإطار/هذه النبرة لهذه المرحلة"
}
```

### **متطلبات إضافية لوضع One-Line**

- حد أقصى ثلاث تنويعات لكل قناة (v1/v2/v3 Hybrid عند الحاجة).
- إن وُجدت شرائح متعددة، أخرج نسخة واضحة لكل Segment مع تسمية.
- أرفق وصف التصميم التفصيلي (`design_description`) الذي يشمل: `composition`, `background`, `lighting`, `colors`, `focus`, `de_emphasize`, `element_positions`, `ratio`, `motion`.
- احرص على أن تشمل كل حزمة قناة تقرير امتثال تفصيلي (`compliance`) يغطي الوسم، RTL، CTA واحد، تنسيق العملة، وعدد كلمات النص البصري (≤8 كلمات)، وأي ملاحظات تصحيحية، إضافة إلى نسخة `sanitized_copy` عند التصحيح.
- فعّل متطلبات DCO والاختبارات من `05_testing_optimization.md`: مرشحون K≤3 لكل قناة، فرضية A/B لمدة 3 أيام، مقياس أساسي مع تقرير متابعة.
- التزم بتسمية التصدير `Ad_v{n}_{Channel}_{Len}_{HookID}` لتجميع الحزم وإرسالها.

### **مخطط موسّع لعنصر الإعلان (Mapping كامل)**

```json
{
  "channel": "Meta|TikTok|Google_RSA|LinkedIn|Email|Landing|WhatsApp_SMS|OOH",
  "segment": "",
  "awareness_stage": "",
  "funnel_stage": "",
  "framework": "",
  "marketing_strategy": "",
  "tone": "",
  "copy": {
    "hook": "",
    "short": "",
    "long": "",
    "cta": "",
    "proof": []
  },
  "mapping": {
    "pains": ["…"],
    "features": ["…"],
    "benefits": ["…"],
    "transformational_benefits": ["…"],
    "usp": "…"
  },
  "primary_metric": "CTR|CVR|ROAS|HookRate",
  "design_description": {
    "composition": "",
    "background": "",
    "lighting": "",
    "colors": [],
    "focus": "",
    "de_emphasize": "",
    "element_positions": {
      "logo": "",
      "headline": "",
      "supporting_copy": "",
      "cta": "",
      "price": "",
      "text_overlay": ""
    },
    "ratio": "1:1|4:5|9:16",
    "motion": "static|subtle|dynamic"
  },
  "compliance": {
    "status": "✅|⚠️|🚫",
    "disclosure_hashtag": true,
    "rtl_layout": true,
    "single_cta": true,
    "currency_format": "BHD",
    "text_overlay_words": 0,
    "claims_clean": true,
    "notes": ""
  },
  "naming": "Ad_v{n}_{Channel}_{Len}_{HookID}"
}
```

### **التحقق الذاتي قبل التسليم**

- تأكد من أن كل أصل يبدأ بـ **#إعلان** عند الحاجة وأن الأسعار تظهر بـ **BHD** أو كنطاق موثق.
- راجع حدود الطول الخاصة بكل قناة (≤4 أسطر للنص الرئيسي في Meta/TikTok، حد الأحرف الرسمي لعناوين وأوصاف Google RSA، ≤100 حرف لـWhatsApp/SMS).
- تحقق من وجود CTA واحد فقط لكل أصل وتطابقه مع مرحلة الوعي والقمع المحددة في `strategy_pack`.
- علّم أي بيانات غير مؤكدة بـ`[افتراض]` وأعد صياغة الكلمات المحظورة («مضمون»، «فوري»، «الأفضل»، «الأرخص») قبل تمرير الأصل إلى `06_compliance.md`.
- حافظ على الربط بين كل أصل وشرائحه (`segment` + `pains/features/benefits/transformational/usp`) وسَمِّ الملفات وفق النمط `Ad_v{n}_{Channel}_{Len}_{HookID}` قبل التصدير.


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
          "short": "#إعلان تكلفة الاكتساب ترتفع؟ اختبر 2–3 زوايا خلال 10 دقائق.",
          "long": "#إعلان تكتب إعلانات ولا ترى تحويلًا؟ CMIS يولّد 8 نسخ قابلة للاختبار بالعربية (RTL) مع إثبات وتضمين BHD. ابدأ الآن بنسخة تجريبية.",
          "cta": "ابدأ التجربة المجانية الآن — بدون بطاقة.",
          "proof": ["[محاكاة] تقييم 4.7/5 خلال 90 يومًا"]
        },
        "design_description": {
          "composition": "واجهة منصة CMIS على لابتوب مع يد تشير إلى لوحة النتائج.",
          "background": "مكتب مضاء بضوء النهار مع نافذة ضبابية الخلفية.",
          "lighting": "إضاءة جانبية دافئة تعزز التفاصيل.",
          "colors": ["#0B1B3A", "#F5C542", "#FFFFFF"],
          "focus": "الشاشة التي تعرض مقاييس النجاح.",
          "de_emphasize": "الأشياء الثانوية على الطاولة مثل الدفتر والقهوة.",
          "element_positions": {
            "logo": "أعلى اليمين بخلفية شفافة.",
            "headline": "منتصف علوي بخط سميك.",
            "supporting_copy": "تذييل أسفل العنوان مباشرةً.",
            "cta": "زر بارز وسط أسفل.",
            "price": "يسار الزر مع توضيح 14.9 BHD.",
            "text_overlay": "اختبر 3 زوايا خلال 10 دقائق"
          },
          "ratio": "4:5",
          "motion": "static"
        },
        "primary_metric": "CTR",
        "naming": "Ad_v2_Meta_Short_HookA",
        "compliance": {
          "status": "✅",
          "disclosure_hashtag": true,
          "rtl_layout": true,
          "single_cta": true,
          "currency_format": "BHD",
          "text_overlay_words": 5,
          "claims_clean": true,
          "notes": ""
        },
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
      "design_description": {
        "composition": "بطاقات نصية متحركة تستعرض خيارات العناوين.",
        "background": "خلفية فاتحة بخطوط قطرية باهتة.",
        "lighting": "إضاءة متساوية بلا تباين حاد.",
        "colors": ["#FFFFFF", "#1B2735", "#00AEEF"],
        "focus": "مربع العنوان الرئيسي.",
        "de_emphasize": "الحواف والمساحات البيضاء.",
        "element_positions": {
          "logo": "أعلى اليمين في شريط شفاف.",
          "headline": "مركز أعلى متماسك RTL.",
          "supporting_copy": "تذييل وسط يسار.",
          "cta": "زر أزرق بأسفل يمين.",
          "price": "أسفل الزر بخط صغير.",
          "text_overlay": "ضاعف نقراتك الذكية"
        },
        "ratio": "1:1",
        "motion": "static"
      },
      "primary_metric": "CTR",
      "naming": "Ad_v1_Google_RSA_IntentX",
      "compliance": {
        "status": "⚠️",
        "disclosure_hashtag": true,
        "rtl_layout": true,
        "single_cta": true,
        "currency_format": "BHD",
        "text_overlay_words": 3,
        "claims_clean": false,
        "notes": "يجب إرفاق مصدر للتقييم"
      },
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

<!-- CMIS:START::REFS_QUALITY -->
### مراجع الجودة والامتثال
- راجع `support_and_templates.md §QUALITY_AND_VARIATIONS` قبل الإخراج النهائي.
- طبّق قواعد `support_and_templates.md §QUALITY_AND_VARIATIONS` عند توليد تنويعات.
<!-- CMIS:END::REFS_QUALITY -->
<!-- CMIS:END::MODULE_07_OUTPUT -->
