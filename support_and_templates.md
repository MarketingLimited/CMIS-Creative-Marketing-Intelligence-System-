<!-- CMIS:START::SUPPORT_AND_TEMPLATES_TOC -->
- MEDIA_TEMPLATES
- QUALITY_AND_VARIATIONS
- OPERATIONS_AND_SUPPORT
- USER_AND_TRAINING_GUIDES
<!-- CMIS:END::SUPPORT_AND_TEMPLATES_TOC -->

<!-- CMIS:START::MEDIA_TEMPLATES -->
<!-- CMIS:START::MEDIA_VIDEO -->
# قوالب الفيديو الجاهزة
<!-- CMIS:START::VIDEO_HEADER -->
# 🎬 قوالب الفيديو الجاهزة (10 قوالب)

- كل قالب يضم: تعريف، النطاق الزمني، نسب أبعاد، مشاهد مفصلة، أوصاف مرئية شاملة (موضوع/سطح/كاميرا/عدسة/إضاءة/خلفية/لوحة ألوان/اتجاه فني/حركة)، نصوص شاشة RTL، تعليمات صوت/موسيقى/SFX، كشف #إعلان (صوت/نص)، وتوصيات مولدات.
- اتبع اتجاهات تصميم 2025 عند الملاءمة (Bold Minimalism, Metallics، الحبيبات، المزج الكلاسيكي-المستقبلي) دون فرض إلزامي.
<!-- CMIS:END::VIDEO_HEADER -->

<!-- CMIS:START::VT::product_showcase_basic -->
## product_showcase_basic
- duration_range: "8–30s"
- aspect_ratios: ["9:16", "4:5", "1:1"]
- recommended_generators: ["Veo 3.1", "Runway Gen-3", "Pika", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Hero product on reflective marble, camera slow push-in, 35mm lens, soft diffused lighting, background gradient teal to gold, color palette rich jewel tones, art_direction Bold Minimalism, motion gentle steam wisps",
    "overlay_ar": "#إعلان طاقة يومية",
    "audio": "ambient synth + soft chime + VO (Bahraini dialect if needed)"
  },
  {
    "scene": 2,
    "prompt_en": "Close-up of key feature animation, camera macro sweep, 60mm lens, crisp spotlight, background abstract light trails, color palette metallic highlights, art_direction futuristic elegance, motion dynamic highlight sweep",
    "overlay_ar": "ميزة تبهرك فوراً",
    "audio": "music bed builds + sparkle sfx + VO emphasizes benefit"
  },
  {
    "scene": 3,
    "prompt_en": "Product in real-use context with hand model, camera handheld, 24mm lens, natural window light, background cozy home setup, color palette warm neutrals, art_direction lifestyle minimal, motion subtle handheld movement",
    "overlay_ar": "جربها خلال دقائق",
    "audio": "music resolves + soft whoosh + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 4,
      "prompt_en": "Hero product bottle on reflective marble, camera slow push-in, 35mm lens, soft diffused lighting, background gradient teal to gold, color palette rich jewel tones, art_direction Bold Minimalism, motion gentle steam wisps",
      "overlay_ar": "#إعلان طاقة يومية"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Macro focus on glowing ingredient detail, camera macro sweep, 60mm lens, crisp spotlight, metallic sparks, art_direction futuristic elegance",
      "overlay_ar": "تركيبة تنعشك"
    },
    {
      "scene": 3,
      "duration_s": 4,
      "prompt_en": "Hand opens fridge and grabs product, camera handheld, 24mm lens, warm morning light, art_direction lifestyle minimal",
      "overlay_ar": "جاهز لك"
    }
  ],
  "voiceover_ar": "#إعلان جرّب شراب الطاقة بنكهة البحرين، استمتع بانتعاش سريع ومسؤول.",
  "cta_ar": "اطلب الآن",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Flatlay of product with date fruits, camera top-down slide, 50mm lens, soft daylight, art_direction Bold Minimalism",
      "overlay_ar": "#إعلان انتقاء فاخر"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Animated icon showing quick-chill feature, camera static, 35mm lens, neon edge lighting, art_direction futuristic elegance",
      "overlay_ar": "يبرّد بثواني"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Customer smiling outdoors sipping product, camera steadicam arc, 24mm lens, golden hour light, art_direction lifestyle minimal",
      "overlay_ar": "لحظة انتعاش"
    }
  ],
  "voiceover_ar": "#إعلان طعم جديد معزز بالفيتامينات، مثالي للعملاء المتحركين طوال اليوم.",
  "cta_ar": "تسوق الآن",
  "export": {
    "ratio": "4:5",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::product_showcase_basic -->
<!-- CMIS:START::VT::ugc_testimonial -->
## ugc_testimonial
- duration_range: "10–25s"
- aspect_ratios: ["9:16", "1:1"]
- recommended_generators: ["Runway Gen-3", "Pika", "Veo 3.1", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Selfie-style creator in cozy living room, camera front-facing, 24mm lens, warm lamp lighting, background soft textiles, color palette earthy neutrals, art_direction authentic UGC, motion slight handheld sway",
    "overlay_ar": "#إعلان أحب النتيجة",
    "audio": "lofi beat + room tone + VO conversational"
  },
  {
    "scene": 2,
    "prompt_en": "Insert shot of product in use, camera macro, 50mm lens, natural side light, background wooden table, color palette warm browns, art_direction lifestyle detail, motion slow tilt",
    "overlay_ar": "تجربة مضمونة",
    "audio": "music dip + tactile sfx + VO detail"
  },
  {
    "scene": 3,
    "prompt_en": "Creator pointing to on-screen text, camera selfie, 24mm lens, daylight, background indoor plant, color palette fresh greens, art_direction candid minimal, motion slight zoom",
    "overlay_ar": "وفّر وقتك",
    "audio": "music swell + sparkle sfx + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Pika",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Selfie creator smiles holding skincare serum, camera front-facing, warm lamp lighting",
      "overlay_ar": "#إعلان بشرة رطبة"
    },
    {
      "scene": 2,
      "duration_s": 4,
      "prompt_en": "Macro dropper releasing serum on hand, camera macro, natural light",
      "overlay_ar": "ملمس خفيف"
    },
    {
      "scene": 3,
      "duration_s": 4,
      "prompt_en": "Creator before mirror giving thumbs up, camera selfie, daylight",
      "overlay_ar": "نتيجة فورية"
    }
  ],
  "voiceover_ar": "#إعلان من أول أسبوع حسّيت بالترطيب، أحب كيف يمتص بسرعة بلا لمعان.",
  "cta_ar": "اطلب السيروم",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 4,
      "prompt_en": "Creator unboxes package on table, camera selfie overhead",
      "overlay_ar": "#إعلان فتح الصندوق"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Close shot of applying product, camera macro sweep",
      "overlay_ar": "نضارة واضحة"
    },
    {
      "scene": 3,
      "duration_s": 4,
      "prompt_en": "Creator adds text bubble rating five stars, camera selfie",
      "overlay_ar": "خدمة سريعة"
    }
  ],
  "voiceover_ar": "#إعلان وصلتني الطلبية خلال يومين، التجربة بالكامل سلسة من الطلب حتى الدعم.",
  "cta_ar": "جرّبها الآن",
  "export": {
    "ratio": "1:1",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::ugc_testimonial -->
<!-- CMIS:START::VT::before_after_service -->
## before_after_service
- duration_range: "12–30s"
- aspect_ratios: ["9:16", "16:9", "4:5"]
- recommended_generators: ["Veo 3.1", "Runway Gen-3", "Pika", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Split screen home interior before cleaning, camera static wide, 24mm lens, cool ambient lighting, background cluttered living room, color palette muted grays, art_direction documentary minimal, motion slow dissolve",
    "overlay_ar": "قبل الخدمة",
    "audio": "pulsing bed + subtle hum + VO setup"
  },
  {
    "scene": 2,
    "prompt_en": "Time-lapse cleaning action, camera tripod, 35mm lens, bright daylight, background organized shelves, color palette fresh whites, art_direction hyperlapse tidy, motion time-lapse sweep",
    "overlay_ar": "تحول سريع",
    "audio": "beat uplift + swoosh + VO process"
  },
  {
    "scene": 3,
    "prompt_en": "After shot sparkling interior, camera glide, 24mm lens, warm sunlight, background styled decor, color palette warm neutrals, art_direction hospitality chic, motion smooth dolly",
    "overlay_ar": "بعد 30 دقيقة",
    "audio": "music resolve + sparkle + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Living room clutter split screen before shot, camera static wide",
      "overlay_ar": "#إعلان قبل"
    },
    {
      "scene": 2,
      "duration_s": 6,
      "prompt_en": "Time-lapse crew cleaning surfaces, camera tripod, bright daylight",
      "overlay_ar": "تنظيف محترف"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "After shot sparkling sofa and rug, camera glide forward",
      "overlay_ar": "بيت مرتب"
    }
  ],
  "voiceover_ar": "#إعلان بخدمة زيّنا بيتك عاد مرتب خلال نصف ساعة بدون تعب منك.",
  "cta_ar": "احجز زيارتنا",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Sora (إذا متاح)",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 6,
      "prompt_en": "Exterior facade before repaint, camera drone hover, overcast lighting",
      "overlay_ar": "#إعلان قبل التجميل"
    },
    {
      "scene": 2,
      "duration_s": 6,
      "prompt_en": "Crew applying fresh paint, camera crane move, midday sun",
      "overlay_ar": "فريق متخصص"
    },
    {
      "scene": 3,
      "duration_s": 6,
      "prompt_en": "After shot vibrant facade, camera reveal, golden hour",
      "overlay_ar": "واجهة جديدة"
    }
  ],
  "voiceover_ar": "#إعلان واجهتنا الجديدة خلّت الجيران يسألون عن الخدمة، الألوان ثابتة وتتحمل الرطوبة.",
  "cta_ar": "اطلب عرض السعر",
  "export": {
    "ratio": "16:9",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::before_after_service -->
<!-- CMIS:START::VT::quick_tutorial_5steps -->
## quick_tutorial_5steps
- duration_range: "15–35s"
- aspect_ratios: ["9:16", "4:5", "1:1"]
- recommended_generators: ["Pika", "Runway Gen-3", "Veo 3.1", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Animated checklist intro, camera top-down, 35mm lens, bright studio light, background paper texture, color palette bold primaries, art_direction playful infographic, motion quick pop",
    "overlay_ar": "#إعلان تعلم بخمس خطوات",
    "audio": "upbeat percussion + click sfx + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Step sequence close-ups, camera macro, 50mm lens, cool key light, background neutral desk, color palette clean blues, art_direction instructional minimal, motion snappy cuts",
    "overlay_ar": "خطوة ١: حضّر",
    "audio": "beat ticks + subtle woosh + VO guiding"
  },
  {
    "scene": 3,
    "prompt_en": "Screen capture overlay, camera simulated, art_direction digital clean, motion cursor highlight",
    "overlay_ar": "خطوة ٣: نفّذ",
    "audio": "music steady + tap sfx + VO"
  },
  {
    "scene": 4,
    "prompt_en": "User reaction shot smiling, camera medium, 35mm lens, natural window light, background tidy workspace, color palette warm neutrals, art_direction lifestyle minimal, motion slight dolly",
    "overlay_ar": "خطوة ٥: شارك",
    "audio": "music lift + clap sfx + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Pika",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 4,
      "prompt_en": "Animated checklist intro with icons, bold primaries",
      "overlay_ar": "#إعلان خمس خطوات"
    },
    {
      "scene": 2,
      "duration_s": 4,
      "prompt_en": "Close-up prepping ingredients, camera macro",
      "overlay_ar": "حضّر مكوناتك"
    },
    {
      "scene": 3,
      "duration_s": 4,
      "prompt_en": "Screen capture showing platform dashboard, digital clean",
      "overlay_ar": "نفّذ بسهولة"
    },
    {
      "scene": 4,
      "duration_s": 3,
      "prompt_en": "User celebrates with thumbs up, warm light",
      "overlay_ar": "شارك النتيجة"
    }
  ],
  "voiceover_ar": "#إعلان خمس خطوات بسيطة تضبط حملتك من اختيار الجمهور حتى إطلاق الرسالة.",
  "cta_ar": "حمّل الدليل",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Bold title card with metallic gradient background",
      "overlay_ar": "#إعلان ابدأ الحين"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Macro shot connecting cables, cool lighting",
      "overlay_ar": "خطوة ٢: وصّل"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Screen overlay showing automation workflow, neon accents",
      "overlay_ar": "خطوة ٤: شغّل"
    },
    {
      "scene": 4,
      "duration_s": 4,
      "prompt_en": "Customer high-fives teammate, camera medium",
      "overlay_ar": "نجاح مشترك"
    }
  ],
  "voiceover_ar": "#إعلان كل خطوة مدعومة بقوالب جاهزة، خل فريقك يبدأ بثقة من أول تجربة.",
  "cta_ar": "ابدأ التجربة",
  "export": {
    "ratio": "4:5",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::quick_tutorial_5steps -->
<!-- CMIS:START::VT::virtual_influencer_promo -->
## virtual_influencer_promo
- duration_range: "12–25s"
- aspect_ratios: ["9:16", "1:1"]
- recommended_generators: ["Sora (إذا متاح)", "Runway Gen-3", "Pika", "Veo 3.1"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Virtual influencer appears in metallic cityscape, camera orbit, 35mm lens, neon rim lighting, background futuristic skyline, color palette metallic pastels, art_direction cyber chic, motion slow orbit",
    "overlay_ar": "#إعلان لقاء جديد",
    "audio": "edm pad + cyber sfx + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Close-up virtual influencer showcasing product hologram, camera push-in, 50mm lens, holographic light, art_direction high-tech glam, motion hologram spin",
    "overlay_ar": "تقنية تلهم",
    "audio": "beat drop + shimmer sfx + VO benefit"
  },
  {
    "scene": 3,
    "prompt_en": "Influencer transitions to real-world set, camera dolly, 24mm lens, warm lighting, background lifestyle loft, color palette warm golds, art_direction hybrid realism, motion smooth dolly",
    "overlay_ar": "جسر بين العوالم",
    "audio": "music blend + airy whoosh + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Sora (إذا متاح)",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Virtual host greets audience in neon skyline, camera orbit",
      "overlay_ar": "#إعلان أهلاً"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Holographic product spins beside host, close-up",
      "overlay_ar": "عرض تفاعلي"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Host steps into real studio, blending AR light",
      "overlay_ar": "جرب الواقع"
    }
  ],
  "voiceover_ar": "#إعلان مؤثرتنا الافتراضية تقدّم لك الإصدار الجديد بلمسة واقعية تلائم جمهور البحرين.",
  "cta_ar": "تابع البث",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 6,
      "prompt_en": "CG influencer waves in metallic atrium, camera crane",
      "overlay_ar": "#إعلان اصنع الحدث"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Product hologram transitions to physical item, camera push",
      "overlay_ar": "تفاصيل نابضة"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Influencer invites swipe-up gesture, warm lighting",
      "overlay_ar": "تابعنا الآن"
    }
  ],
  "voiceover_ar": "#إعلان متابعونا يصوتون مباشرة ويختارون الإكسسوارات عبر البث التفاعلي.",
  "cta_ar": "احجز مقعدك",
  "export": {
    "ratio": "1:1",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::virtual_influencer_promo -->
<!-- CMIS:START::VT::shoppable_video -->
## shoppable_video
- duration_range: "10–20s"
- aspect_ratios: ["9:16", "4:5"]
- recommended_generators: ["Runway Gen-3", "Pika", "Veo 3.1", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Dynamic carousel of three products, camera swipe, 24mm lens, bright key light, background seamless gradient, color palette vibrant brights, art_direction Bold Minimalism, motion swipe with UI tags",
    "overlay_ar": "#إعلان تسوق مباشر",
    "audio": "dance beat + tap sfx + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Focus on hero product with clickable hotspot, camera push-in, 35mm lens, spotlight, background subtle grid, color palette electric blues, art_direction digital retail, motion pulse highlight",
    "overlay_ar": "لمسة تشتري",
    "audio": "beat accent + ping sfx + VO benefit"
  },
  {
    "scene": 3,
    "prompt_en": "Checkout confirmation overlay, camera angle on smiling customer, 50mm lens, warm interior light, background cozy setup, color palette warm neutrals, art_direction lifestyle commerce, motion slight nod",
    "overlay_ar": "تم الطلب بسهولة",
    "audio": "music resolve + success chime + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 4,
      "prompt_en": "Three handbags swipe across screen with price tags",
      "overlay_ar": "#إعلان شنطك جاهزة"
    },
    {
      "scene": 2,
      "duration_s": 4,
      "prompt_en": "Hero bag rotates with add-to-cart icon pulse",
      "overlay_ar": "اسحب واشترِ"
    },
    {
      "scene": 3,
      "duration_s": 4,
      "prompt_en": "Customer receives confirmation on mobile, smiles",
      "overlay_ar": "تم الطلب"
    }
  ],
  "voiceover_ar": "#إعلان اختاري شنطتك واضغطي على الوسم مباشرة، الدفع آمن خلال لحظات.",
  "cta_ar": "تسوقي الآن",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Smartwatch lineup spinning with clickable UI tags",
      "overlay_ar": "#إعلان اختر ساعتك"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Close-up on health feature, add-to-cart animation",
      "overlay_ar": "نبضك أوضح"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Order confirmation overlay on laptop screen",
      "overlay_ar": "ختمنا الطلب"
    }
  ],
  "voiceover_ar": "#إعلان تابع نبضك واشترِ الساعة مع خصم خاص بمجرد الضغط على الوسم.",
  "cta_ar": "اشتري الآن",
  "export": {
    "ratio": "4:5",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::shoppable_video -->
<!-- CMIS:START::VT::hyperlocal_story -->
## hyperlocal_story
- duration_range: "15–40s"
- aspect_ratios: ["9:16", "16:9"]
- recommended_generators: ["Veo 3.1", "Runway Gen-3", "Pika", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Drone establishing shot of Manama skyline, camera slow descent, 24mm lens, sunrise lighting, background cityscape, color palette warm golds, art_direction cinematic documentary, motion descending reveal",
    "overlay_ar": "#إعلان من قلب المنامة",
    "audio": "oud fusion + ambient city + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Local shop owner greeting customers, camera handheld, 35mm lens, natural light, background traditional storefront, color palette earthy tones, art_direction authentic storytelling, motion subtle sway",
    "overlay_ar": "قصتنا بحرينية",
    "audio": "music with rhythmic claps + VO narration"
  },
  {
    "scene": 3,
    "prompt_en": "Customer enjoying product near Bahrain Fort, camera gimbal, 28mm lens, golden hour, background heritage landmark, color palette warm sandstone, art_direction cultural pride, motion smooth orbit",
    "overlay_ar": "نكهة تراثية",
    "audio": "music swell + ambient breeze + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 6,
      "prompt_en": "Drone shot sunrise over Bahrain World Trade Center",
      "overlay_ar": "#إعلان صباح المنامة"
    },
    {
      "scene": 2,
      "duration_s": 6,
      "prompt_en": "Baker shaping traditional bread, camera handheld",
      "overlay_ar": "خبزنا بحريني"
    },
    {
      "scene": 3,
      "duration_s": 6,
      "prompt_en": "Family shares breakfast near historic fort, camera gimbal",
      "overlay_ar": "يجمعنا الطعم"
    }
  ],
  "voiceover_ar": "#إعلان من مخبزنا المحلي لبيوتكم، خبز التنور يوصلكم دافئ خلال ساعة داخل المنامة.",
  "cta_ar": "احجز خبزك",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Wide shot of Muharraq alleys at dusk, camera glide",
      "overlay_ar": "#إعلان من المحرق"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Local artisan weaving palm fronds, camera close",
      "overlay_ar": "حرفة أصيلة"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Customer sipping traditional coffee by dhow harbor, camera orbit",
      "overlay_ar": "لحظة بحرينية"
    }
  ],
  "voiceover_ar": "#إعلان ندعم الحرفيين المحليين بقصة كل منتج، زورونا في سوق المحرق اليوم.",
  "cta_ar": "تعرف علينا",
  "export": {
    "ratio": "16:9",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::hyperlocal_story -->
<!-- CMIS:START::VT::longform_vertical -->
## longform_vertical
- duration_range: "45–120s"
- aspect_ratios: ["9:16"]
- recommended_generators: ["Sora (إذا متاح)", "Veo 3.1", "Runway Gen-3", "Pika"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Cold open teaser with bold text, camera handheld, 24mm lens, moody spotlight, background dark studio, color palette deep blues, art_direction cinematic docu, motion quick whip",
    "overlay_ar": "#إعلان تابع القصة",
    "audio": "cinematic pulse + riser + VO hook"
  },
  {
    "scene": 2,
    "prompt_en": "Chaptered interview segments with subtitles, camera tripod, 35mm lens, practical lighting, background branded set, color palette warm ambers, art_direction editorial minimal, motion slow push",
    "overlay_ar": "الفصل الأول",
    "audio": "music bed subdued + VO narrative"
  },
  {
    "scene": 3,
    "prompt_en": "B-roll montage of process, camera mixed shots, 24-50mm lens, natural light, background workplace, color palette neutral tones, art_direction documentary rich, motion montage cuts",
    "overlay_ar": "رحلة الإبداع",
    "audio": "music evolves + foley + VO details"
  },
  {
    "scene": 4,
    "prompt_en": "Data visualization overlay, camera digital composite, art_direction sleek infographic, motion animated stats",
    "overlay_ar": "أرقام موثوقة",
    "audio": "music lift + digital beeps + VO proof"
  },
  {
    "scene": 5,
    "prompt_en": "Closing CTA with team shot, camera wide, 24mm lens, warm backlight, background studio logo, color palette gold accents, art_direction inspiring finish, motion slow zoom",
    "overlay_ar": "انضم للتجربة",
    "audio": "music crescendo + uplifting sfx + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Sora (إذا متاح)",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 8,
      "prompt_en": "Teaser text flashes over founder silhouette, handheld camera",
      "overlay_ar": "#إعلان البداية"
    },
    {
      "scene": 2,
      "duration_s": 12,
      "prompt_en": "Founder interview mid-shot, warm practical lights",
      "overlay_ar": "قصة الفكرة"
    },
    {
      "scene": 3,
      "duration_s": 15,
      "prompt_en": "Montage of product assembly, macro and wide shots",
      "overlay_ar": "من ورشة لنجاح"
    },
    {
      "scene": 4,
      "duration_s": 10,
      "prompt_en": "Animated dashboard stats overlay, sleek graphics",
      "overlay_ar": "أرقام تثق بها"
    },
    {
      "scene": 5,
      "duration_s": 10,
      "prompt_en": "Team celebrates launch, confetti, camera wide",
      "overlay_ar": "جاهز تنضم؟"
    }
  ],
  "voiceover_ar": "#إعلان من فكرة محلية إلى منصة تخدم الخليج، اعرف الرحلة كاملة وابدأ معنا الفصل القادم.",
  "cta_ar": "احجز استشارة",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 7,
      "prompt_en": "Bold text overlays with motion blur intro",
      "overlay_ar": "#إعلان خلف الستار"
    },
    {
      "scene": 2,
      "duration_s": 10,
      "prompt_en": "CMIS analyst speaking in studio, camera push",
      "overlay_ar": "نسمع الخبرة"
    },
    {
      "scene": 3,
      "duration_s": 12,
      "prompt_en": "B-roll of analytics dashboard, hand interactions",
      "overlay_ar": "بيانات واضحة"
    },
    {
      "scene": 4,
      "duration_s": 9,
      "prompt_en": "Infographic bars rising with brand colors",
      "overlay_ar": "أداء مثبت"
    },
    {
      "scene": 5,
      "duration_s": 8,
      "prompt_en": "CTA slate with logo and QR code",
      "overlay_ar": "انطلق معنا"
    }
  ],
  "voiceover_ar": "#إعلان تعرف على حلول CMIS المتقدمة عبر قصة عملائنا وشوف كيف تضاعفت النتائج.",
  "cta_ar": "ابدأ الآن",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::longform_vertical -->
<!-- CMIS:START::VT::behind_the_scenes -->
## behind_the_scenes
- duration_range: "20–45s"
- aspect_ratios: ["9:16", "16:9", "4:5"]
- recommended_generators: ["Runway Gen-3", "Pika", "Veo 3.1", "Sora (إذا متاح)"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Crew prepping set, camera handheld, 24mm lens, tungsten work lights, background studio gear, color palette industrial warm, art_direction documentary raw, motion whip pans",
    "overlay_ar": "#إعلان كواليسنا",
    "audio": "percussive beat + chatter ambience + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Creative review moment around monitor, camera over-shoulder, 35mm lens, practical lighting, background screen glow, color palette warm neutrals, art_direction collaborative, motion slow push",
    "overlay_ar": "فريق متكامل",
    "audio": "music mid tempo + clicks + VO insight"
  },
  {
    "scene": 3,
    "prompt_en": "Product styling close-up, camera macro, 50mm lens, focused spotlight, background dark vignette, color palette metallic accents, art_direction craft focus, motion slow spin",
    "overlay_ar": "تفاصيل دقيقة",
    "audio": "music swell + soft sfx + VO detail"
  },
  {
    "scene": 4,
    "prompt_en": "Wrap celebration, camera gimbal, 24mm lens, confetti burst, background studio set, color palette vibrant mix, art_direction celebratory, motion smooth arc",
    "overlay_ar": "جاهزين للإطلاق",
    "audio": "music peak + cheer sfx + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Runway Gen-3",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 6,
      "prompt_en": "Crew setting lights around product table",
      "overlay_ar": "#إعلان تجهيز"
    },
    {
      "scene": 2,
      "duration_s": 6,
      "prompt_en": "Director and client reviewing monitor, over-shoulder",
      "overlay_ar": "تناغم فريق"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Stylist adjusting metallic accessory, macro",
      "overlay_ar": "تفاصيل ذهبية"
    },
    {
      "scene": 4,
      "duration_s": 5,
      "prompt_en": "Team cheers with confetti, camera gimbal",
      "overlay_ar": "جاهزين للعرض"
    }
  ],
  "voiceover_ar": "#إعلان ورشة CMIS الإنتاجية تضمن كل لقطة مدروسة، من الإضاءة حتى موافقات الامتثال.",
  "cta_ar": "احجز جلسة تصوير",
  "export": {
    "ratio": "16:9",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Pika",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Makeup artist prepping talent, camera handheld",
      "overlay_ar": "#إعلان تحضير"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "DP adjusting camera rig, over-shoulder shot",
      "overlay_ar": "دقة عالية"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Product on rotating table lit by spotlights",
      "overlay_ar": "لمسة إبداع"
    },
    {
      "scene": 4,
      "duration_s": 5,
      "prompt_en": "Final slate clap, team applauds",
      "overlay_ar": "جاهز للبث"
    }
  ],
  "voiceover_ar": "#إعلان نكشف لكم سر خلف كل إعلان ناجح، شوفوا الفريق وهو يضبط التفاصيل.",
  "cta_ar": "تابع الكواليس",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::behind_the_scenes -->
<!-- CMIS:START::VT::ai_human_hybrid -->
## ai_human_hybrid
- duration_range: "18–35s"
- aspect_ratios: ["9:16", "4:5"]
- recommended_generators: ["Veo 3.1", "Sora (إذا متاح)", "Runway Gen-3", "Pika"]
- compliance_checklist:
  - "#إعلان في أول 3 ثوانٍ (صوت/نص)"
  - "BHD عند ذكر سعر"
  - "CTA واحد"
  - "بدون مطلقات"

### المشاهد
```json
[
  {
    "scene": 1,
    "prompt_en": "Split-screen human strategist and AI interface, camera medium, 35mm lens, cool rim lighting, background digital grid, color palette electric blues, art_direction tech-collab, motion mirrored swipe",
    "overlay_ar": "#إعلان فريق مشترك",
    "audio": "hybrid beat + synth swells + VO intro"
  },
  {
    "scene": 2,
    "prompt_en": "Close-up of AI dashboard recommendations, camera macro, 50mm lens, glowing interface, background holographic panels, color palette neon accents, art_direction futuristic clarity, motion data pulses",
    "overlay_ar": "ذكاء فوري",
    "audio": "music pulse + data blips + VO insight"
  },
  {
    "scene": 3,
    "prompt_en": "Human team implementing suggestions on tablet, camera over-shoulder, 35mm lens, natural office light, background collaborative workspace, color palette warm neutrals, art_direction modern workspace, motion dolly slide",
    "overlay_ar": "قرار دقيق",
    "audio": "music rise + tap sfx + VO CTA"
  }
]
```

### مثال 1 كامل (10–15 ثانية)

```json
{
  "generator": "Veo 3.1",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 5,
      "prompt_en": "Strategist reviews screen beside holographic AI avatar",
      "overlay_ar": "#إعلان توازن"
    },
    {
      "scene": 2,
      "duration_s": 5,
      "prompt_en": "Dashboard shows automated insights, neon glow",
      "overlay_ar": "تحليل لحظي"
    },
    {
      "scene": 3,
      "duration_s": 5,
      "prompt_en": "Team nods and approves plan on tablet",
      "overlay_ar": "نفّذ بثقة"
    }
  ],
  "voiceover_ar": "#إعلان اجمع بين ذكاء CMIS وخبرة فريقك، قرارات أسرع ونتائج محسوبة.",
  "cta_ar": "اكتشف التكامل",
  "export": {
    "ratio": "9:16",
    "subtitle": "on"
  }
}
```

### مثال 2 كامل (نسبة أبعاد مختلفة)

```json
{
  "generator": "Sora (إذا متاح)",
  "scenes": [
    {
      "scene": 1,
      "duration_s": 6,
      "prompt_en": "Human marketer and AI hologram brainstorming, camera orbit",
      "overlay_ar": "#إعلان تعاون"
    },
    {
      "scene": 2,
      "duration_s": 6,
      "prompt_en": "Close-up of predictive chart rising, neon interface",
      "overlay_ar": "نتائج متوقعة"
    },
    {
      "scene": 3,
      "duration_s": 6,
      "prompt_en": "Team launches campaign with AR checkmark, camera dolly",
      "overlay_ar": "حملة ناجحة"
    }
  ],
  "voiceover_ar": "#إعلان شفافية البيانات تلتقي بالإبداع البشري، شغل الذكاء وحافظ على لمسنتك البشرية.",
  "cta_ar": "ابدأ التجربة",
  "export": {
    "ratio": "4:5",
    "subtitle": "on"
  }
}
```

<!-- CMIS:END::VT::ai_human_hybrid -->
<!-- CMIS:START::VIDEO_SUMMARY -->
## ملخص القوالب
- إجمالي القوالب: 10
- إجمالي الأمثلة الكاملة: 20
<!-- CMIS:END::VIDEO_SUMMARY -->
<!-- CMIS:END::MEDIA_VIDEO -->

<!-- CMIS:START::MEDIA_AUDIO -->
# قوالب الصوت الجاهزة
<!-- CMIS:START::AUDIO_HEADER -->
# 🎧 قوالب الصوت الجاهزة (5 قوالب)

- تأكد من ذكر #إعلان صوتيًا خلال الثلاث ثواني الأولى، واستخدم لهجات ملائمة للسوق البحريني، واحفظ خصوصية المتصلين عند تخصيص الرسائل.
<!-- CMIS:END::AUDIO_HEADER -->

<!-- CMIS:START::AT::radio_podcast_30_60s -->
## radio_podcast_30_60s
- duration_range: "30–60s"
- voice_spec: {"gender": "female", "age": "30s", "dialect": "Bahraini", "tone": "uplifting", "pace": "moderate"}
- music_sfx: "خلفية ناعمة بإيقاع بحريني مع مؤثرات انتقالية خفيفة"
- disclosure: "#إعلان خلال أول 3 ثوانٍ"
- privacy_ethics: "لا تستخدم بيانات صوتية غير مرخصة، واذكر أن الصوت مُولَّد إن لزم"

### هيكل النص بزمن تقريبي
- 0–3s: Hook
- 3–15s: Problem/Solution
- 15–…s: Proof/Offer
- النهاية: CTA + تذكير #إعلان

### مثال 1 (AR)
```text
#إعلان من CMIS، تخيل أدوات تسويق تفهم جمهورك قبل ما يتكلم. تواجه فرقك حملات مشتتة؟ منصتنا تجمع البيانات، تقترح محتوى، وتذكرك بالامتثال في لحظة. عملاؤنا شاهدوا نمو حقيقي بدون اجتهاد عشوائي. جرّب CMIS اليوم وسجل عرضك الخاص الآن.
```

### مثال 2 (EN/AR Hybrid)

```text
#Ad from CMIS. Need campaigns that adapt fast? منصتنا تربط insights فورية مع فرقك البشرية، وتضمن التزامك باللوائح. Join البحرين businesses leveraging CMIS، واطلب العرض التجريبي الآن.
```

<!-- CMIS:END::AT::radio_podcast_30_60s -->
<!-- CMIS:START::AT::shoppable_audio_15_30s -->
## shoppable_audio_15_30s
- duration_range: "15–30s"
- voice_spec: {"gender": "male", "age": "20s", "dialect": "Gulf", "tone": "energetic", "pace": "fast"}
- music_sfx: "إيقاع إلكتروني خفيف مع نغمات دفع تشبه صوت النقر"
- disclosure: "#إعلان خلال أول 3 ثوانٍ"
- privacy_ethics: "لا تستخدم بيانات صوتية غير مرخصة، واذكر أن الصوت مُولَّد إن لزم"

### هيكل النص بزمن تقريبي
- 0–3s: Hook
- 3–15s: Problem/Solution
- 15–…s: Proof/Offer
- النهاية: CTA + تذكير #إعلان

### مثال 1 (AR)
```text
#إعلان جاهز تطلب بضغطة صوت؟ قول: اطلب عرض CMIS. لحظياً يرسلك لرابط متجرنا، وتوصلك باقة القوالب الذكية.
```

### مثال 2 (EN/AR Hybrid)

```text
#Ad say: shop CMIS bundles now. النظام يرسل لك لينك مخصص، وتتابع بالعربي أو الإنجليزي بدون ما توقف البودكاست.
```

<!-- CMIS:END::AT::shoppable_audio_15_30s -->
<!-- CMIS:START::AT::sonic_logo_intro_outro -->
## sonic_logo_intro_outro
- duration_range: "3–8s"
- voice_spec: {"gender": "female", "age": "20s", "dialect": "Bahraini", "tone": "confident", "pace": "brisk"}
- music_sfx: "توقيع صوتي من ثلاث نغمات معدنية مع صدى قصير"
- disclosure: "#إعلان خلال أول 3 ثوانٍ"
- privacy_ethics: "لا تستخدم بيانات صوتية غير مرخصة، واذكر أن الصوت مُولَّد إن لزم"

### هيكل النص بزمن تقريبي
- 0–3s: Hook
- 3–15s: Problem/Solution
- 15–…s: Proof/Offer
- النهاية: CTA + تذكير #إعلان

### مثال 1 (AR)
```text
#إعلان CMIS حاضر، ثلاث نغمات تختتم كل حملة.
```

### مثال 2 (EN/AR Hybrid)

```text
#Ad CMIS—Future marketing in Bahrain. نغمة وتذكير سريع.
```

<!-- CMIS:END::AT::sonic_logo_intro_outro -->
<!-- CMIS:START::AT::voice_assistant_prompt -->
## voice_assistant_prompt
- duration_range: "8–15s"
- voice_spec: {"gender": "neutral", "age": "adult", "dialect": "Modern Standard", "tone": "helpful", "pace": "steady"}
- music_sfx: "نغمة افتتاحية قصيرة مع خلفية هادئة شبه شفافة"
- disclosure: "#إعلان خلال أول 3 ثوانٍ"
- privacy_ethics: "لا تستخدم بيانات صوتية غير مرخصة، واذكر أن الصوت مُولَّد إن لزم"

### هيكل النص بزمن تقريبي
- 0–3s: Hook
- 3–15s: Problem/Solution
- 15–…s: Proof/Offer
- النهاية: CTA + تذكير #إعلان

### مثال 1 (AR)
```text
#إعلان مرحباً بك، اسألني عن عروض CMIS وأرسل لك خطة سريعة.
```

### مثال 2 (EN/AR Hybrid)

```text
#Ad Hello, ask for CMIS Bahrain updates and receive tailored insights فوراً.
```

<!-- CMIS:END::AT::voice_assistant_prompt -->
<!-- CMIS:START::AT::multilingual_voice_cloning -->
## multilingual_voice_cloning
- duration_range: "20–35s"
- voice_spec: {"gender": "male", "age": "40s", "dialect": "Bahraini", "tone": "reassuring", "pace": "measured"}
- music_sfx: "مزيج أوتار خفيف مع إيقاع إلكتروني بسيط"
- disclosure: "#إعلان خلال أول 3 ثوانٍ"
- privacy_ethics: "لا تستخدم بيانات صوتية غير مرخصة، واذكر أن الصوت مُولَّد إن لزم"

### هيكل النص بزمن تقريبي
- 0–3s: Hook
- 3–15s: Problem/Solution
- 15–…s: Proof/Offer
- النهاية: CTA + تذكير #إعلان

### مثال 1 (AR)
```text
#إعلان صوت CMIS يتكلم بلهجتك ويصون الخصوصية، نعرّف جمهورك بكل لغة يحتاجها.
```

### مثال 2 (EN/AR Hybrid)

```text
#Ad CMIS voice cloning keeps approvals compliant. جرّب النسخة العربية والإنجليزية بنفس الدقة.
```

<!-- CMIS:END::AT::multilingual_voice_cloning -->
<!-- CMIS:START::AUDIO_SUMMARY -->
## ملخص القوالب الصوتية
- إجمالي القوالب: 5
- إجمالي الأمثلة الصوتية: 10
<!-- CMIS:END::AUDIO_SUMMARY -->
<!-- CMIS:END::MEDIA_AUDIO -->
<!-- CMIS:END::MEDIA_TEMPLATES -->

<!-- CMIS:START::QUALITY_AND_VARIATIONS -->
<!-- CMIS:START::QUALITY_CHECKLISTS -->
<!-- CMIS:START::CHECKLISTS_HEADER -->
# ✅ قوائم التحقق الداخلية — 2025 (امتثال وجودة)

- الهدف: ضمان الاتساق والجودة قبل إخراج أي مخرجات (نص/صورة/فيديو/صوت/خطة).
- التنفيذ: تُنفَّذ هذه القوائم داخليًا قبل الإرسال، مع تصحيح تلقائي حيث أمكن.
<!-- CMIS:END::CHECKLISTS_HEADER -->

<!-- CMIS:START::TEXT_COMPLIANCE -->
## نصوص (Text Compliance)
- يبدأ المحتوى المدفوع بـ **#إعلان** في أول سطر.
- الأسعار بعملة **BHD** فقط.
- لا مطلقات: (الأفضل/الأرخص/مضمون 100%) إلا مع دليل واضح؛ وإلا تُوسم **[افتراض]** أو **[محاكاة]**.
- **CTA واحد** واضح ومناسب لمرحلة الوعي.
- العربية RTL سليمة؛ تدقيق لغوي؛ لا تجاوز لغوي مسيء.
- عدم استخدام CTA شرائي مباشر لجمهور **Unaware** (قدّم قيمة/اكتشف أولًا).
<!-- CMIS:END::TEXT_COMPLIANCE -->

<!-- CMIS:START::VISUAL_COMPLIANCE -->
## مرئي/تصميم (Visual Compliance)
- تباين ≥ 4.5:1؛ نص الشاشة ≤ 8 كلمات؛ مساحة أمان للحواف.
- احترام الثقافة المحلية (زيّ/سياق/أماكن) وعدم عرض ما يسيء أو يضلل.
- نسب الأبعاد صحيحة للقناة (1:1/4:5/9:16…).
- حقوق الأصول (صور/خطوط/أيقونات) مُصرَّح بها؛ لا علامات مائية غير مقصودة.
- **وصف التصميم إلزامي**: لكل أصل، أدرج نصًا يحدد التكوين، الخلفية، الإضاءة، الألوان، مواضع العناصر، الملمس، نسبة الأبعاد، والحركة (إن وُجدت) بدقة كافية لتمكين المصمم/المولد من إعادة البناء دون غموض.
- **التزام البرومبت/السيناريو:** تأكد أن كل وصف تصميمي يعيد صياغة المتطلبات المحددة من سيناريو أو برومبت المستخدم دون حذف عناصر إلزامية.
<!-- CMIS:END::VISUAL_COMPLIANCE -->

<!-- CMIS:START::VIDEO_COMPLIANCE -->
## فيديو (Video Compliance)
- **#إعلان** صوتيًا خلال أول 3 ثوانٍ + نصيًا في أول لقطة.
- Hook بصري/لفظي في أول 3 ثوانٍ.
- نصوص شاشة RTL، لا تتجاوز 8 كلمات لكل لقطة.
- صوت واضح متوازن مع الموسيقى والمؤثرات (لا يطغى).
<!-- CMIS:END::VIDEO_COMPLIANCE -->

<!-- CMIS:START::AUDIO_COMPLIANCE -->
## صوت (Audio Compliance)
- #إعلان منطوق خلال 0–3 ثوانٍ.
- مواصفات الصوت: وضوح، سرعة نطق مناسبة، لهجة (بحرينية/خليجية) عند الحاجة.
- لا ادعاءات مطلقة دون مصدر؛ توازن مستويات VO/Music/SFX.
- لا استخدام أصوات/موسيقى بلا ترخيص؛ أشر لذلك إن كان AI VO.
<!-- CMIS:END::AUDIO_COMPLIANCE -->

<!-- CMIS:START::DESIGN_TREND_CHECK -->
## اتجاهات التصميم (Design Trend Checklist)
- عند تطبيق اتجاه: اختر واحدًا واضحًا فقط لكل أصل (Bold Minimalism | Metallics | Grain/Texture | Neo-Classic Futurism | Motion-led Narrative).
- لوحة ألوان متناسقة؛ قابلية قراءة عالية؛ لا ازدحام بصري.
- هذا القسم توجيهي غير إلزامي — يُذكر الاتجاه في المخرجات عند استخدامه.
<!-- CMIS:END::DESIGN_TREND_CHECK -->

<!-- CMIS:START::AI_ETHICS_PRIVACY -->
## أخلاقيات الذكاء الاصطناعي والخصوصية
- شفافية: أعلِن أن المحتوى قد يكون مولدًا (صوت/صورة/فيديو) عند اللزوم.
- ممنوع الانتحال/التزييف أو استخدام شبه المشاهير دون تصريح.
- موافقات الخصوصية لرسائل WhatsApp/Email؛ خيار إلغاء الاشتراك واضح.
<!-- CMIS:END::AI_ETHICS_PRIVACY -->

<!-- CMIS:START::DELIVERY_CHECK -->
## تسليم وإخراج (Delivery Checklist)
- بنية الإخراج: StrategyPack → Ads/Video/Audio → **Compliance Report** → **Self-checks** → **ملخص**.
- تسمية الأصول: `Ad_v{n}_{Channel}_{Len}_{HookID}`.
- توثيق الافتراضات: أي رقم بلا مصدر يُوسم [افتراض]/[محاكاة].
<!-- CMIS:END::DELIVERY_CHECK -->

<!-- CMIS:START::AUTO_FIX -->
## آلية تصحيح تلقائي (Auto-Fix Rules)
- غياب #إعلان → إضافة تلقائية في أول السطر/أول 3 ثوانٍ صوتيًا.
- CTA مزدوج → إبقاء واحد/الأهم وحذف الباقي.
- أرقام بلا مصدر → تحويلها إلى نطاقات مع وسم [افتراض] أو حذف الرقم والاحتفاظ بالمنفعة.
- RTL مفقود → فرض اتجاه RTL وعكس المحاذاة.
<!-- CMIS:END::AUTO_FIX -->

<!-- CMIS:START::COMPLIANCE_JSON -->
## مخطط تقرير الامتثال (JSON)
```json
{
  "ad_disclosure": "present|missing|auto_fixed",
  "currency": "BHD|missing|n/a",
  "absolutes": "none|found|auto_fixed",
  "cta_single": true,
  "rtl": true,
  "visual_accessibility": {"contrast":"ok|low","screen_text_words":"<=8|>8"},
  "video_audio": {"vo_disclosure_0_3s": true, "levels_balanced": true},
  "design_trend": "none|Bold_Minimalism|Metallics|Grain|NeoClassicFuturism|MotionLed",
  "ethics_privacy": {"ai_disclosure": "needed|done|n/a", "consents": "ok|missing"}
}
```

<!-- CMIS:END::COMPLIANCE_JSON -->
<!-- CMIS:END::QUALITY_CHECKLISTS -->

<!-- CMIS:START::VARIATION_STRATEGY -->
<!-- CMIS:START::VAR_RULES -->
# 🔄 استراتيجية التنويع (2025)

## قاعدة أساسية
- كل تنويع يجب أن يختلف في **3 عناصر على الأقل** من: Hook، Framework، Angle، Tone، Visual Style، **Audio (voice/music/SFX)**، **Community (UGC/EGC/Brand)**، **Interactivity (CTA/Question/Shop)**.
- **تنويع الوسائط إلزامي:** في أي حزمة إعلانات/محتوى ≥ 3 أصول يجب تضمين مزيج من صورة ثابتة (أو كاروسيل)، فيديو قصير (Reel/TikTok)، وStory/قصّة تفاعلية أو صيغة فيديو بديلة. دوّن نوع الوسيط بوضوح داخل الميتاداتا (`media_type`) وضمن وصف التصميم.
- **لا تكرار للأفكار:** يمنع إعادة استخدام نفس الحبكة أو المشهد أو ترتيب اللقطات عبر التنويعات؛ يجب ابتكار زوايا سردية/بصرية جديدة بالكامل.
- **العنصر البشري:** في القنوات التي تتطلب تمثيلًا (Reels, TikTok, Stories, UGC, Ads مصورة)، ضمن تواجد شخص/مؤثر/مستخدم فعلي أو تمثيلي في كل تنويع، مع تنويع النوع (ممثل، مؤثر، UGC، فريق داخلي) عبر الحزمة.

## تغييرات إلزامية للثلاثة الرئيسيين
- v1: Pain-focused — **PAS** — زاوية الخسارة — نبرة عاجلة.
- v2: Benefit-focused — **AIDA** — زاوية القيمة — نبرة إيجابية.
- v3: Proof-focused — **FAB/4U** — زاوية الدليل — نبرة واثقة.
- أضف اختلافًا صوتيًا على الأقل في أحد التنويعات (لهجة/موسيقى/إيقاع).
- أضف اختلافًا مجتمعيًا: قصة موظف (EGC) مقابل شهادة عميل (UGC).
- أضف اختلافًا تفاعليًا: CTA مباشر مقابل سؤال/استطلاع.
- اربط كل تنويع بـ `awareness_stage` و`funnel_stage` و`marketing_strategy` داخل حقل الميتاداتا، ووضّح داخل النص كيف يخدم هذا الارتباط (سطر تحليلي قصير).
<!-- CMIS:END::VAR_RULES -->

<!-- CMIS:START::VAR_MATRIX -->
## مصفوفة التنويع حسب القناة
- **Meta**: 2–3 تنويعات (Hook + Framework + Angle + Audio/UGC).  
- **TikTok**: 2 تنويعات (Hook + Visual Style + Short VO).  
- **Google RSA**: 2 مجموعات عناوين/أوصاف (Focus: pain/benefit).  
- **LinkedIn**: 2 تنويعات (Opening + Proof Type + Tone).  
- **Email**: 2 تنويعات (Subject + Body Structure).
<!-- CMIS:END::VAR_MATRIX -->

<!-- CMIS:START::VAR_QUALITY_CHECK -->
## مدقق جودة التنويعات (مفاهيمي)
```text
احسب نقاط الاختلاف بين v1/v2، v1/v3، v2/v3 عبر المحاور: hook, framework, angle, tone, visual, audio, community, interactivity.
- إذا كان مجموع الفروق لكل زوج < 2 → ❌ أعد التوليد.
- مجموع = 2 → ⚠️ مقبول مع تحسين.
- مجموع ≥ 3 → ✅ جيد.
الحد الأدنى للنشر: كل زوج ≥ 3.
تحقق إضافي: لا تكرار للمشاهد أو السرد، والعنصر البشري حاضر في كل أصل قابل للتصوير.
```

### متطلبات الميتاداتا الموسعة
- **لكل تنويع** ضمن أي قناة، يجب أن يتضمّن سجل الميتاداتا الحقول التالية على الأقل: `marketing_framework`, `marketing_strategy`, `awareness_stage`, `funnel_stage`, `transformational_benefit`, `usp_reference`, `message_map`, `media_type`, `design_trend`, `audio_plan`.
- اربط الحقول المذكورة أعلاه بجداول `used_fields` في الإخراج الرئيسي لضمان التتبع؛ أي تناقض يُعد مخالفة جودة.
- أضف ملخصًا تنفيذيًا من جملة واحدة يشرح كيف يخدم هذا المزيج الهدف (مثال: "Framework PAS + Strategy UGC لمعالجة ألم التأخر بالاستلام في مرحلة Problem-aware/MOFU").

<!-- CMIS:END::VAR_QUALITY_CHECK -->
<!-- CMIS:END::VARIATION_STRATEGY -->

<!-- CMIS:START::COMMON_MISTAKES -->
<!-- CMIS:START::MISTAKE_AUDIO_LICENSE -->
## خطأ: موسيقى/VO بدون ترخيص واضح
**❌ خاطئ:**
```text
استخدام مقطع موسيقي غير منسوب/غير مرخّص
```

**✅ صحيح:**

```text
استخدم مكتبة مرخّصة/مفتوحة مع ذكر المصدر؛ إن كان VO مولدًا بالذكاء الاصطناعي فاذكر ذلك في الوصف.
```

<!-- CMIS:END::MISTAKE_AUDIO_LICENSE -->

<!-- CMIS:START::MISTAKE_VISUAL_VAGUE -->

## خطأ: وصف بصري عام ينتج صورة غير متسقة

**❌ خاطئ:** "صورة منتج جميل"
**✅ صحيح:**
"Product on dark stone surface, 45° soft window light, shallow DOF, warm golden palette, 4:5, Bold Minimalism"

<!-- CMIS:END::MISTAKE_VISUAL_VAGUE -->

<!-- CMIS:START::MISTAKE_DISCLOSURE -->

## خطأ: غياب #إعلان صوتيًا

**❌ خاطئ:** إدراج الهاشتاق نصيًا فقط.
**✅ صحيح:** يذكر #إعلان **صوتيًا خلال 0–3 ثوانٍ** إضافة للنص في أول لقطة.

<!-- CMIS:END::MISTAKE_DISCLOSURE -->

<!-- CMIS:START::MISTAKE_CTA_MULTI -->

## خطأ: تعدد الدعوات للإجراء

**❌ خاطئ:** "اشترِ الآن أو تواصل أو احجز"
**✅ صحيح:** CTA واحد واضح "اطلب الآن" + خيارات أخرى تُذكر ثانويًا لاحقًا إن لزم.

<!-- CMIS:END::MISTAKE_CTA_MULTI -->
<!-- CMIS:END::COMMON_MISTAKES -->

<!-- CMIS:START::TESTING_CHECKLIST -->
# قائمة الاختبارات
# Testing Checklist

## Campaign Scenarios

### 1. حملة B2B
- **الهدف:** التأكد من أن المحتوى يستهدف الشركات بوضوح ويلتزم بلوائح الامتثال.
- **خطوات التحقق:**
  1. إنشاء مخرجات الحملة عبر النظام.
  2. مراجعة الرسائل للتأكد من أنها موجهة لقطاع الأعمال وتستخدم مصطلحات مهنية مناسبة.
  3. التحقق من تضمين عروض قيمة واضحة وإجراءات متابعة (CTA) قابلة للتنفيذ.
  4. التأكد من أن تنسيق JSON، إن وُجد، صالح باستخدام أدوات التحقق (مثل `jq`).
  5. مراجعة عناصر الامتثال (إخلاء المسؤولية، سياسات البيانات، الموافقات القانونية).
  6. تقييم ملاءمة الرسائل مع أهداف العميل الصناعي.
- **مقاييس النجاح:**
  ```json
  {
    "json_valid": true,
    "compliance_flags": 0,
    "message_relevance": "high"
  }
  ```
- **قالب الملاحظات:**
  - الملاحظة:
  - الدليل (رابط/لقطة شاشة):
  - الأثر على الحملة:
- **إجراءات المعالجة:**
  1. إخطار فريق الامتثال إذا وُجدت مخالفات.
  2. تعديل الرسائل لتشمل عروض القيمة أو CTA غير الواضحة.
  3. إعادة الاختبار بعد التعديلات وتوثيق النتائج في نظام التذاكر.

### 2. حملة مواسم
- **الهدف:** ضمان انسجام الحملة مع السياق الموسمي وتوافقها مع السياسات المحلية.
- **خطوات التحقق:**
  1. توليد نسخة الحملة لموسم محدد (مثلاً رمضان، العطلات الصيفية).
  2. فحص العناصر البصرية والنصية للتأكد من أنها تعكس الطابع الموسمي المناسب.
  3. التحقق من خلو المحتوى من مراجع حساسة ثقافياً أو دينياً.
  4. التحقق من صحة أي تنسيقات JSON مستخدمة في إعدادات القنوات.
  5. مراجعة الامتثال لتوجيهات المنصات (منصات التواصل الاجتماعي، البريد الإلكتروني).
  6. تقييم مدى ملاءمة الرسالة لجمهور الموسم المستهدف.
- **مقاييس النجاح:**
  ```json
  {
    "json_valid": true,
    "compliance_flags": 0,
    "message_relevance": "seasonal-fit"
  }
  ```
- **قالب الملاحظات:**
  - الملاحظة:
  - القناة:
  - التوقيت:
  - التوصية:
- **إجراءات المعالجة:**
  1. تعديل الرسائل أو العناصر البصرية غير المناسبة ثقافياً.
  2. استشارة فريق التوطين في حال وجود التباس حول العادات المحلية.
  3. تحديث خطة النشر وإعادة اختبار المحتوى عبر المنصات المتأثرة.

### 3. طلب فيديو
- **الهدف:** التأكد من أن سيناريو الفيديو متوافق مع المتطلبات الإبداعية والامتثال.
- **خطوات التحقق:**
  1. إنشاء سيناريو الفيديو باستخدام النظام وتصدير السكربت.
  2. مراجعة التسلسل السردي للتأكد من وضوح الرسالة والهوية البصرية.
  3. التحقق من التزام العناصر المرئية والصوتية بإرشادات العلامة التجارية.
  4. استخدام أداة تحقق JSON لأي ملفات وصف إنتاجية.
  5. مراجعة الامتثال لحقوق الملكية الفكرية والموسيقى والمؤثرات.
  6. تقييم مدى صلة الرسالة بجمهور الفيديو المستهدف.
- **مقاييس النجاح:**
  ```json
  {
    "json_valid": true,
    "compliance_flags": 0,
    "message_relevance": "audience-aligned"
  }
  ```
- **قالب الملاحظات:**
  - المشهد:
  - الملاحظة:
  - فريق الإنتاج المسؤول:
  - الإجراء الموصى به:
- **إجراءات المعالجة:**
  1. التنسيق مع فريق الإنتاج لتعديل المشاهد أو النصوص المخالفة.
  2. رفع التعديلات إلى منصة إدارة الأصول ومراجعة الموافقات.
  3. إعادة التحقق من السيناريو بعد التعديلات وتوثيق الحالة النهائية.

## توثيق عام للحالات
- **نموذج سجل الاختبار:**
  - اسم الحملة/الطلب:
  - التاريخ:
  - المسؤول:
  - الحالة: (ناجح/يتطلب إجراءات)
  - ملخص النتائج:
  - إجراءات المتابعة:

- **قالب خطة المعالجة متعددة المنصات:**
  1. تحديد المنصة المتأثرة (مثلاً: فيسبوك، لينكدإن، يوتيوب).
  2. وصف المشكلة المكتشفة.
  3. تحديد مستوى الأولوية (مرتفع/متوسط/منخفض).
  4. تعيين مسؤول المعالجة وتحديد الموعد النهائي.
  5. تسجيل الإجراءات المتخذة ونتائج إعادة الاختبار.
  6. إغلاق الحالة بعد توثيق الموافقات اللازمة.

<!-- CMIS:START::TEST_OVERVIEW -->
# 🧪 قائمة الاختبار — إطلاق 2025
- الهدف: ضمان جودة وامتثال قبل النشر وبعده (Smoke/Regression/Content QA).
<!-- CMIS:END::TEST_OVERVIEW -->

<!-- CMIS:START::TEST_PRELAUNCH -->
## قبل الإطلاق (Pre-Launch)
- توليد StrategyPack + 3 Ads/Channel (Meta, TikTok, Google, LinkedIn).
- فيديو 9:16 Hook≤3s + نص شاشة ≤8 كلمات.
- صوت: #إعلان منطوق 0–3s + مستويات صوت متوازنة.
- تخصيص: نسخة عامة + نسخة مخصصة (الاسم/الموقع/السلوك).
- ثنائية اللغة: AR→EN ملخص 2–3 أسطر (عند الطلب).
- امتثال: تقرير JSON وفق `support_and_templates.md §QUALITY_AND_VARIATIONS`.
<!-- CMIS:END::TEST_PRELAUNCH -->

<!-- CMIS:START::TEST_POSTLAUNCH -->
## بعد الإطلاق (Post-Launch)
- تحقق من قابلية القراءة/المشاهدة على مختلف الشاشات.
- مراجعة التعليقات/الرفض من المنصات إن وُجد وتصحيح السبب.
- تدوين ملاحظات التنويعات (ما الذي فاز/لماذا).
<!-- CMIS:END::TEST_POSTLAUNCH -->

<!-- CMIS:START::TEST_LONGFORM_VERTICAL -->
## حالات خاصة
- **Long-form Vertical (حتى 5 دقائق)**: فواصل تشويقية كل 20–30s، ملخص في النهاية، CTA واحد.
- **Interactive/Shoppable**: نقاط تفاعل واضحة، تعليمات ربط، ذكر السعر BHD.
<!-- CMIS:END::TEST_LONGFORM_VERTICAL -->
<!-- CMIS:END::TESTING_CHECKLIST -->
<!-- CMIS:END::QUALITY_AND_VARIATIONS -->

<!-- CMIS:START::OPERATIONS_AND_SUPPORT -->
<!-- CMIS:START::RELEASE_AND_SUPPORT -->
<!-- CMIS:START::RELEASE_PLAYBOOK -->
<!-- CMIS:START::RELEASE_PLAYBOOK -->
# 🚀 Playbook الإطلاق
- Go/No-Go: تحقق من (اختبارات ما قبل الإطلاق + الامتثال + طول instruction_prompt).
- خطة التواصل: رسالة إعلان داخلية + سجل تغييرات مختصر.
- خطة تراجع (Rollback): العودة لآخر نسخة مُستقرة عند الحاجة.
<!-- CMIS:END::RELEASE_PLAYBOOK -->
<!-- CMIS:END::RELEASE_PLAYBOOK -->

<!-- CMIS:START::SUPPORT_RUNBOOK -->
<!-- CMIS:START::SUPPORT_RUNBOOK -->
# 🛟 Runbook الدعم
- استقبال الملاحظات: تصنيف (امتثال/جودة/لغة/صوت/فيديو/تنويعات).
- خطوات الاستجابة: إعادة توليد > مراجعة بشرية > توثيق في سجل.
<!-- CMIS:END::SUPPORT_RUNBOOK -->
<!-- CMIS:END::SUPPORT_RUNBOOK -->

<!-- CMIS:START::CONTRIBUTING_2025 -->
<!-- CMIS:START::CONTRIBUTING_2025 -->
# 🤝 المساهمة في CMIS
- لا مجلدات.  
- استخدم محددات `CMIS:START/END`.  
- لا تحذف محتوى أصليًا؛ أضف كتل مُدارة جديدة.  
- رسائل التزام **Conventional Commits**.
<!-- CMIS:END::CONTRIBUTING_2025 -->
<!-- CMIS:END::CONTRIBUTING_2025 -->
<!-- CMIS:END::RELEASE_AND_SUPPORT -->

<!-- CMIS:START::HELP_DOC -->
**Archived** — الوثيقة تخص نسخة أقدم. راجع [instruction_prompt.md](instruction_prompt.md)، [instruction_addendum_and_playbooks.md](instruction_addendum_and_playbooks.md)، و[README.md](README.md) للتعليمات الحالية ودليل التنقل السريع.

للحصول على سيناريوهات تشغيل متقدمة ومُلخّصات الاستخدام، راجع ملف [instruction_addendum_and_playbooks.md](instruction_addendum_and_playbooks.md).

## الأسئلة الشائعة (FAQ)
### كيف أحل مشكلات الإعداد الشائعة؟
- تأكد من أن `instruction_prompt.md` لا يتجاوز 8,000 حرف قبل رفعه إلى المنصة.
- ارفع جميع الملفات ضمن جلسة واحدة، ثم استخدم خيار **Replace** عند تحديث أي ملف لضمان تطابق النسخ.
- إذا رفضت المنصة ملفًا كبيرًا، قسّم الوحدات أو استخدم نسخة مضغوطة ضمن `instruction_addendum_and_playbooks.md`.

### ما حدود المعرفة الحالية للنظام؟
- يعتمد CMIS على الملفات المرفوعة فقط؛ لا توجد قاعدة بيانات خارجية مدمجة.
- يوصى بمراجعة محتوى الوحدات ربع سنويًا لتحديث الأمثلة واللوائح المحلية.

### كيف أستدعي الوحدات الاختيارية؟
- أشر في الطلب إلى الحاجة لوحدة معينة (مثل "فعّل وحدة Video Scenarios") ليتعرف النظام على تفعيلها.
- يمكن تعديل الأهداف (Goals) في GPT أو Gem لتشغيل وضعيات مثل `full_strategy`, `quick_draft`, أو `compliance_only` حسب الحاجة.
<!-- CMIS:END::HELP_DOC -->

<!-- CMIS:START::AGENTS_DOC -->
# Repository Instructions

- The `instruction_prompt.md` file must not exceed 8,000 characters.
- If `instruction_prompt.md` ever exceeds this limit, compress its contents and move any non-essential commands to other appropriate files to bring it back within the limit.
<!-- CMIS:END::AGENTS_DOC -->
<!-- CMIS:END::OPERATIONS_AND_SUPPORT -->

<!-- CMIS:START::USER_AND_TRAINING_GUIDES -->
<!-- CMIS:START::USER_GUIDE_AND_STARTERS -->
<!-- CMIS:START::USER_GUIDE -->
<!-- CMIS:START::UG_HEADER -->
# 🎯 دليل البدء السريع — CMIS (2025)

- الهدف: تمكين أي مستخدم من إنجاز حملة أو محتوى خلال دقائق، مع امتثال كامل (#إعلان/BHD/RTL).
- نِطاق الملفات: instruction_prompt.md + الوحدات 01–10 + المكتبات (hooks/video/audio/industry/json) + الجودة.
<!-- CMIS:END::UG_HEADER -->

<!-- CMIS:START::UG_WORKFLOWS -->
## كيف تستخدم CMIS في 3 خطوات
1) اختر النمط: حملة كاملة | إعلانات سريعة | سيناريو فيديو | رسالة صوت | خطة محتوى | بحث ترند.  
2) قدّم المدخلات الأساسية (brand/product/objective/audience/channels/budget).  
3) استلم: StrategyPack → Ads/Video/Audio → **Compliance Report** → **Next Steps**.

### أمثلة جاهزة (انسخ-ألصق)
```text
- حملة مطعم: #إعلان نبي خطة لأسبوع 17 مارس 2025 لمطعم بحري يقدم وجبات 7.5 BHD مع عروض إفطار عملاء الشركات.
- إعلان خدمة تنظيف: #إعلان جهّز 3 رسائل WhatsApp لتنظيف عميق قبل رمضان لجمهور العائلات العاملة مع أسعار 18/25 BHD.
- فيديو UGC (15s): #إعلان سوّي سيناريو UGC عن تطبيق توصيل ورد في المنامة، ركّز على لحظة unboxing وتوصية صديقة.
- تقرير ترند مختصر: حلّل اتجاهات محتوى TikTok عن السياحة في البحرين ربيع 2025 وقدّم 5 توصيات بسرعة التنفيذ.
```
<!-- CMIS:END::UG_WORKFLOWS -->

<!-- CMIS:START::UG_GUIDES -->

## أدلة استخدام مختصرة حسب الملف

* libraries_and_examples.md: اختيار Hook حسب مرحلة الوعي والقطاع/الموسم مع أمثلة جاهزة.
* support_and_templates.md §MEDIA_TEMPLATES: اختيار قالب الفيديو/الصوت + ملء المتغيرات + الالتزام بالـ 3 ثواني الأولى و#إعلان منطوق.
* json_output_templates.md: قوالب الإخراج الموحدة + الحقول الجديدة للترند/التفاعل.
* support_and_templates.md §QUALITY_AND_VARIATIONS: نفّذ الفحوصات قبل التسليم، احرص على اختلاف ≥3 محاور لكل تنويع، وراجع التصحيحات السريعة.

<!-- CMIS:END::UG_GUIDES -->

<!-- CMIS:START::UG_TIPS -->

## أفضل الممارسات السريعة

* اجعل الـ Hook ≤ 12 كلمة، وابدأ بقيمة واضحة.
* فيديو عمودي 9:16 مع Hook بصري/لفظي في أول 3 ثوانٍ.
* CTA واحد فقط، وأسعار BHD عند ذكر أي سعر.
* للأرقام: مصدر أو وسم [افتراض]/[محاكاة].
* صِف المشهد بصريًا (موضوع/سطح/إضاءة/خلفية/ألوان/حركة).

<!-- CMIS:END::UG_TIPS -->

<!-- CMIS:START::UG_TROUBLESHOOT -->

## حل المشكلات الشائعة

* **المخرجات متشابهة** → بدّل framework/angle/tone/voice/UGC/التفاعل.
* **رفض منصة لإعلان** → راجع ملف support_and_templates.md §QUALITY_AND_VARIATIONS/قسم الامتثال.
* **صوت غير واضح** → خفّض الموسيقى 3–6 dB وارفع VO.
* **طول زائد** → استخدم قوالب JSON المختصرة وقلّل نص الشاشة.

<!-- CMIS:END::UG_TROUBLESHOOT -->

<!-- CMIS:START::UG_GLOSSARY -->

## مسرد مختصر

* UGC/EGC: محتوى يقدمه المستخدم/الموظف لخلق مصداقية سريعة.
* Shoppable Video: فيديو يمكن النقر عليه لشراء المنتج مباشرة مع وسم السعر.
* AI Disclosure: توضيح أن الذكاء الاصطناعي شارك في إنتاج المحتوى.
* CTR/CVR: معدل النقر إلى الظهور/معدل التحويل؛ استخدمهما لمقارنة التنويعات.
* DCO: Dynamic Creative Optimization لتجربة تركيبات النص/الصورة تلقائيًا.
* AI Safety Review: مراجعة أخلاقيات لضبط الحساسية الثقافية والخصوصية.

<!-- CMIS:END::UG_GLOSSARY -->
<!-- CMIS:END::USER_GUIDE -->

<!-- CMIS:START::PROMPT_STARTERS -->
```yaml
# CMIS:START::PROMPT_STARTERS_2025
audio_campaigns:
  - text: "🎧 أريد حملة صوتية (30s) لـ [منتج/خدمة] باللهجة البحرينية مع #إعلان منطوق"
    variables: ["الجمهور", "المنفعة", "CTA"]
  - text: "🎙️ اكتب إعلان بودكاست (60s) لقطاع [X] يشمل إثبات اجتماعي وCTA واحد"
    variables: ["القطاع", "العرض", "الدليل"]
  - text: "📻 حضّر سبوت إذاعي سريع (15s) عن [العرض] مع ذكر السعر BHD والتنويه بالخصوصية"
    variables: ["العرض", "السعر", "قناة_النشر"]
  - text: "🔊 صمّم حزمة رسائل صوتية تفاعلية IVR لـ [الخدمة] تتضمن خيار دعم فوري"
    variables: ["نوع_الخدمة", "شريحة_العملاء", "CTA"]
  - text: "🎼 نحتاج سكربت إعلان صوتي مزدوج اللغة (AR/EN) حول [الحملة] مع توازن موسيقى/VO"
    variables: ["الحملة", "الرسالة", "مستوى_الموسيقى"]
  - text: "🗣️ أعطني 3 افتتاحيات صوتية مختلفة لـ [منتج] تركز على الألم ثم الحل خلال 10 ثوانٍ"
    variables: ["المنتج", "الألم", "الحل"]

trend_research:
  - text: "🔎 أحتاج تقرير اتجاهات محدث حول [موضوع] في 2025 مع 5 توصيات قابلة للتنفيذ"
    variables: ["الموضوع", "القناة"]
  - text: "📈 لخص أحدث أرقام [قناة/صيغة] وطبّقها على سوق البحرين"
    variables: ["القناة", "هدف_الحملة"]
  - text: "🛰️ حلّل ما يقوله المؤثرون في البحرين عن [القطاع] وحدد فرص التعاون السريعة"
    variables: ["القطاع", "نوع_المؤثر"]
  - text: "🗞️ اعطني موجزًا أسبوعيًا لأبرز الترندات الاجتماعية حول [موضوع] مع زوايا محتوى"
    variables: ["الموضوع", "الفترة"]
  - text: "📊 استخرج مؤشرات البحث المحلية لكلمات [X] واقترح إستراتيجية محتوى موسمية"
    variables: ["الكلمات", "الموسم"]
  - text: "🌍 قارِن بين سلوك الجمهور في البحرين والخليج نحو [المنتج] وقدّم توصيات تخصيص"
    variables: ["المنتج", "شرائح_الجمهور"]

interactive_content:
  - text: "🛍 أنشئ سيناريو فيديو تفاعلي قابل للتسوق (15s) لـ [منتج]"
    variables: ["نقاط التفاعل", "السعر BHD", "CTA"]
  - text: "❓ اكتب إعلانًا يتضمن سؤال تفاعلي للجمهور (Meta) مع خيار تصويت"
    variables: ["السؤال", "زاوية الألم/المنفعة"]
  - text: "🎯 صمّم حملة قصص إنستغرام بثلاث شرائح تتضمن ملصقات تصويت حول [العرض]"
    variables: ["العرض", "الجمهور", "CTA"]
  - text: "🧪 ابني لعبة اختيار المسار لمحتوى TikTok عن [الخدمة] مع نهايتين مختلفتين"
    variables: ["الخدمة", "المسارين", "CTA"]
  - text: "🎮 حضّر سيناريو chatbot تسويقي يوجّه المستخدم لشراء [المنتج] مع تحذير امتثال"
    variables: ["المنتج", "سؤال_الافتتاح", "تحذير_الامتثال"]

general:
  - text: "🧩 أريد 3 تنويعات إعلان (PAS/AIDA/4U) لـ [خدمة]"
    variables: ["الجمهور", "القناة"]
  - text: "🎥 اكتب سيناريو UGC (15s) باللهجة البحرينية"
    variables: ["المشكلة", "الحل", "CTA"]
  - text: "📢 صغ حملة متكاملة لقنوات Meta/TikTok/Google عن [العلامة] خلال أسبوع واحد"
    variables: ["العلامة", "الهدف", "الميزانية"]
  - text: "📝 أعطني خطة محتوى أسبوعية (5 أيام) لمدونة [المجال] مع CTA واضح"
    variables: ["المجال", "الجمهور", "CTA"]
  - text: "🚀 حضّر StrategyPack لإطلاق منتج [X] يشمل personas وvalue props وroadmap 30 يوم"
    variables: ["المنتج", "الفترة", "الميزانية"]
  - text: "🧠 اكتب Brief إبداعي سريع لحملة [نوع_الحملة] يوضح الرسالة والعرض ودليل اجتماعي"
    variables: ["نوع_الحملة", "الجمهور", "العرض"]
  - text: "🛡️ أنتج تقرير امتثال مختصر لإعلانات [القناة] مع توصيات الإصلاح"
    variables: ["القناة", "مستوى_المخاطر", "المخرجات"]
# CMIS:END::PROMPT_STARTERS_2025
```
<!-- CMIS:END::PROMPT_STARTERS -->
<!-- CMIS:END::USER_GUIDE_AND_STARTERS -->

<!-- CMIS:START::TRAINING_AND_EVALUATION -->
<!-- CMIS:START::TRAINING_OUTLINE -->
<!-- CMIS:START::TRAINING_OUTLINE -->
# 🧭 برنامج تدريب CMIS — المستخدمون
- المدة: 60–90 دقيقة (وحدات قصيرة).
## الأهداف
- إنتاج حملة متكاملة، استخدام القوالب، ضمان الامتثال.
## المنهج
1) جولة سريعة على الملفات والكتل المُدارة.
2) إنشاء حملة كاملة (Hands-on).
3) فيديو UGC + صوت 30s (#إعلان منطوق).
4) استخدام قوائم الاختبار والتسليم.
## تمارين
- كتابة 2 Hooks مختلفين جذريًا.
- توليد 2 تنويعات بإختلاف ≥3 محاور.
<!-- CMIS:END::TRAINING_OUTLINE -->
<!-- CMIS:END::TRAINING_OUTLINE -->

<!-- CMIS:START::TRAINER_GUIDE -->
<!-- CMIS:START::TRAINER_GUIDE -->
# 🎓 دليل المدرّب — CMIS
- كيفية تحديث المكتبات شهريًا (hooks/video/audio/industry).
- سياسة الأخلاقيات والخصوصية، وكيفية فحص الإفصاحات.
- جمع التغذية الراجعة وتوثيقها، وآلية قبول/رفض التعديلات.
<!-- CMIS:END::TRAINER_GUIDE -->
<!-- CMIS:END::TRAINER_GUIDE -->

<!-- CMIS:START::EVALUATION_RUBRICS -->
<!-- CMIS:START::EVAL_RUBRICS -->
# 🧮 Rubrics التقييم — CMIS
| المحور | ممتاز (3) | جيّد (2) | يحتاج تحسين (1) |
| --- | --- | --- | --- |
| الامتثال | كل الإعلانات تحتوي #إعلان/BHD/خصوصية موثقة | نقص عنصر ثانوي واحد مع خطة إصلاح | مخالفات جوهرية أو غياب تقرير امتثال |
| الإبداع | Hooks مبتكرة، تنويعات ≥3 فروقات واضحة | تنويعات محدودة بنبرات متقاربة | تكرار شبه كامل دون زوايا جديدة |
| الوسائط | فيديو/صوت ملتزم بالمواصفات (9:16، 0–3s) | مخالفة طفيفة قابلة للتعديل | طول أو تنسيق غير صالح للنشر |
| البيانات | استخدام مصادر أو تمييز [افتراض]/[محاكاة] | إشارات عامة دون تأكيد مصدر | ادعاءات مطلقة بلا دليل |
| التسليم | StrategyPack + Next Steps مكتملة | نقص ملف ثانوي (مثلاً Self-Checks) | مخرجات ناقصة تعيق النشر |
<!-- CMIS:END::EVAL_RUBRICS -->
<!-- CMIS:END::EVALUATION_RUBRICS -->
<!-- CMIS:END::TRAINING_AND_EVALUATION -->
<!-- CMIS:END::USER_AND_TRAINING_GUIDES -->
