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
