<!-- CMIS:START::MODULE_08_09 -->
# وحدتا 08 و09 — سيناريوهات الفيديو + تخطيط المحتوى

## نظرة شاملة
- هذه الوثيقة موجهة لخبراء التسويق وصنّاع المحتوى المتقدم، وتُستخدم داخل نظام CMIS لتوجيه **Gem** و**GPT** في إنتاج سيناريوهات فيديو عالية الدقة وخطط محتوى متعددة القنوات.
- جميع الإرشادات تلتزم بالتوطين الافتراضي لمملكة البحرين (لغة عربية RTL، عملة BHD، حساسية ثقافية ومحلية كاملة).
- كل المخرجات الإعلانية تبدأ بـ`#إعلان` عند استخدامها لأغراض ترويجية، وتلتزم بعدم استخدام ادعاءات مطلقة أو شعارات منافسين.

---

<!-- CMIS:START::MODULE_08 -->
# MODULE 08 — Video Scenario Engine

<!-- CMIS:START::PURPOSE -->
## الغرض (≤ سطرين)
- توليد سيناريوهات فيديو احترافية قابلة للتنفيذ على مولدات الفيديو بالذكاء الاصطناعي (Kling Wan 2.5، Veo 3.1، Runway، HeyGen، إلخ) وتغطية **10+ أنواع** محتوى تلبي جميع أهداف التسويق (Awareness، Consideration، Conversion، Retention).
<!-- CMIS:END::PURPOSE -->

### أنواع السيناريوهات المعتمدة (Scenario Type Catalogue)
| الكود | النوع | الهدف التسويقي الأبرز | ملاحظات تكتيكية |
|-------|-------|-----------------------|------------------|
| `character_based` | قصة مع شخصيات | بناء الثقة، التفاعل العاطفي | حوار باللهجة المطلوبة + حكاية مشكلة→حل |
| `product_focused` | عرض المنتج بصرياً | إبراز الخصائص والفائدة | لقطات تفصيلية، حركة كاميرا واضحة |
| `virtual_influencer` | مؤثر افتراضي | توصية شخصية، محتوى متكرر | HeyGen/D-ID/Synthesia؛ حافظ على اتساق الأفاتار |
| `vfx_cinematic` | خدع بصرية وسينمائية | جذب انتباه سريع، Viral | لا تبالغ حتى لا تفقد المصداقية |
| `documentary` | وثائقي/Behind the Scenes | شفافية، بناء الهوية | يُفضل تصوير حقيقي أو واقعي للغاية |
| `educational` | تعليمي/How-To | تثقيف، رفع الوعي | خطوات واضحة، نصوص داعمة |
| `awareness_psa` | رسالة توعوية | CSR، تثبيت القيم | نبرة جادة أو ملهمة، أرقام أو حقائق |
| `ugc_style` | محتوى نمط UGC | مصداقية، حميمية | أسلوب كاميرا هاتف، أخطاء بسيطة مقبولة |
| `mixed_carousel` | كاروسيل صور + فيديو | تنويع القصة | Slide 3 فيديو قصير لجذب الانتباه |
| `experimental` | تخصيص متقدم/DCO | حملات ديناميكية | يُستخدم عند تفعيل DCO Expansion |

> **التوطين الافتراضي:** السوق البحريني (AR/RTL، عملة BHD، لهجة بحرينية/خليجية). يتم ضبط القيم تلقائيًا إذا لم تُزوّد في الطلب.

<!-- CMIS:START::INPUTS -->
## المدخلات (JSON)
```json
{
  "brand": "",
  "product_or_service": "",
  "objective": "awareness|consideration|conversion|retention",
  "target_audience": "",
  "channels": ["TikTok", "Instagram Reels", "YouTube", "TV", "Landing_Page"],
  "budget_bhd": "",
  "scenario_type": "character_based|product_focused|virtual_influencer|vfx_cinematic|documentary|educational|awareness_psa|ugc_style|mixed_carousel|experimental",
  "emotional_trigger": "fear|trust|joy|inspiration|urgency|relief|desire",
  "trend_research": {
    "topic": "",
    "language": "ar",
    "depth": "summary|detailed"
  },
  "dialogue": {
    "required": true,
    "language": "Bahraini_Arabic|Gulf_Arabic|Egyptian_Arabic|English|None",
    "dialect_notes": "",
    "voice_characteristics": "male_warm|female_confident|neutral_calm"
  },
  "technical_specs": {
    "duration_seconds": [6, 8, 10, 15, 30, 60],
    "aspect_ratio": "9:16|16:9|1:1",
    "scenes_max": 4,
    "ai_generator": "Kling_Wan_2.5|Sora_2|Veo_3|Veo_3.1|Runway|Pika|Luma|HeyGen|D-ID|Synthesia|Any",
    "audio_generation": true
  },
  "audio_type": "dialogue_generated|music_sfx_generated|music_only|silent"
}
```

### المدخلات الأصلية (منسوخة حرفيًا)
````````````json
{
  "scenario_type": "character_based|product_focused|virtual_influencer|vfx_cinematic|documentary|educational|awareness_psa|ugc_style|mixed_carousel",
  "product_or_service": "",
  "brand": "",
  "campaign_concept": "",
  "marketing_objective": "awareness|conversion|retention",
  "emotional_trigger": "fear|trust|joy|inspiration|urgency|relief|desire",
  "target_segment": "",
  "framework_output": {
    "channel": "TikTok|Meta_Reels|YouTube|TV|Landing_Page",
    "copy": { "hook": "", "story_bab": "" }
  },
  "dialogue": {
    "required": true,
    "language": "Bahraini_Arabic|Gulf_Arabic|Egyptian_Arabic|English|None",
    "dialect_notes": "لهجة بحرينية حديثة، نبرة ودية",
    "voice_characteristics": "male_warm|female_confident|neutral_calm"
  },
  "technical_specs": {
    "duration_seconds": [6, 8, 10, 15, 30, 60],
    "aspect_ratio": "9:16|16:9|1:1",
    "scenes_max": 4,
    "ai_generator": "Kling_Wan_2.5|Sora_2|Veo_3|Veo_3.1|Runway|Pika|Luma|HeyGen|D-ID|Synthesia|Any",
    "audio_generation": true
  },
  "audio_type": "dialogue_generated|music_sfx_generated|music_only|silent",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" }
}
````````````
<!-- CMIS:END::INPUTS -->

### مواءمة الهدف مع القمع التسويقي
| الهدف التسويقي | مرحلة الوعي المرجّحة | موقع القُمع | CTA مقترح |
| --- | --- | --- | --- |
| Awareness | From unaware → problem-aware | TOFU | «تعرّف أكثر» · «اكتشف القصة» |
| Consideration | Problem-aware → solution-aware | MOFU | «شاهد التفاصيل» · «قارن بين الخيارات» |
| Conversion | Solution-aware → product-aware | BOFU | «اطلب الآن» · «احجز تجربتك» |
| Retention | Most-aware (عملاء حاليون) | Loyalty/Post-Purchase | «جدّد اشتراكك» · «شارك مزاياك» |

<!-- CMIS:START::STEPS -->
## خط الأنابيب التنفيذي (Execution Flow)
1. **تحليل الطلب**: تأكيد توافر الحقول الجوهرية (`brand`, `product_or_service`, `scenario_type`, `objective`).
2. **تهيئة التوطين**: إذا لم يُذكر السوق، استخدم إعداد البحرين (RTL، BHD، الحساسية الثقافية الموضحة في قسم التوطين).
3. **البحث عن التوجهات**: عند وجود `trend_research.topic` نفّذ موجزًا (ملخص + مصدر) وادمجه في قسم `insights.trends`.
4. **مصفوفة الحقول**: أنشئ Matrix تدعم تعدد القيم لكل من (audience_segments، pain_points، triggers، frameworks، tones، channels).
5. **توليد التنويعات**: أخرج على الأقل 3 تنويعات أساسية (v1-v3) تغطي:
   - v1 → Pain/PAS مع Trigger عاطفي قوي (Fear/Relief).
   - v2 → Benefit/AIDA مع تركيز على Proof أو Social Proof.
   - v3 → Proof/FAB مع رسائل أداء أو Testimonials.
   حافظ على اختلاف ≥3 محاور بين كل تنويع (مثلاً trigger، framework، funnel stage، tone، channel).
6. **تفعيل DCO Expansion**: إذا طُلب صراحة أو كان `channels` تحتوي منصات ديناميكية، أضف تنويعات v4-v8 (حتى 12) مع تبرير داخل `used_fields.notes`.
7. **بناء المشاهد**: لكل تنويع أنشئ مشاهد مفصلة (≤ `scenes_max`) تشمل: وصف بصري بالإنجليزية، عناصر الكاميرا، الإضاءة، الصوت، النصوص على الشاشة، عناصر الامتثال.
8. **تقرير الامتثال**: تحقق من (#إعلان، عملة BHD، CTA واحد، لا ادعاءات مطلقة، عدم إظهار مشاهير)، وسجّل الحالة داخل `compliance` لكل تنويع.
9. **مخرجات JSON النهائية**: التزم بالـSchema الموجود في قسم `المخرجات (JSON)` أدناه، وأضف ملخصًا تنفيذيًا من 3 أسطر.
<!-- CMIS:END::STEPS -->

<!-- CMIS:START::MIXER_STEP -->
### Mixer Blueprint
- بعد تلخيص المدخلات، ابنِ **مصفوفات** للحقول المتغيرة (segments، pains، triggers، frameworks، strategies، tones، offers، proof points) ودوّن الافتراضات داخل `used_fields.assumptions`.
- إجبار التنوع في **عناصر المشهد**: غيّر الحركة، الإضاءة، نسبة الألوان، زاوية الكاميرا، التشكيلة الصوتية.
- عند إنشاء توسعة DCO: وزّع التنويعات على قنوات مختلفة (مثلاً Reels، TikTok، YouTube Shorts، Landing Page)، واذكر سبب الاختيار في `distribution_rationale`.
<!-- CMIS:END::MIXER_STEP -->

### سياسة الامتثال والسلامة (شاملة)
````````````yaml
compliance_universal:
  forbidden:
    - "مشاهير أو شخصيات عامة معروفة (إن وُجدت شخصيات)"
    - "أي نصوص داخل اللقطات إلا إذا كانت جزءاً طبيعياً من البيئة (لا لافتات دعائية مصطنعة)"
    - "علامات تجارية منافسة أو شعارات غير مصرح بها"
    - "ادعاءات مطلقة أو مضللة (100% مضمون، الأفضل عالمياً، إلخ)"
    - "محتوى مسيء، تمييزي، أو مهدد للسلامة"
  required:
    - "إظهار #إعلان نصاً أو صوتاً خلال أول 3 ثوانٍ"
    - "استخدام عملة BHD عند ذكر الأسعار"
    - "احترام اتجاه RTL في أي نص عربي"
    - "اتساق بصري في الألوان والإضاءة والملابس"
    - "أزياء وبيئات ملائمة ثقافياً (بحرين/خليج)"
    - "اتباع برومبت كل مولد حرفياً داخل وصف المشهد"
  generator_specific:
    veo3: ["منع النصوص المضافة مباشرة على اللقطة إلا إذا كانت طبيعية", "لا مشاهير"]
    veo3_1: ["أفضل مولد للحوار العربي", "يدعم lip sync تلقائي"]
    runway: ["دعم نصوص محدود", "مناسب للسيناريوهات الحركية السريعة"]
    pika: ["ممتاز للمنتجات الثابتة", "تحريك بسيط"]
    sora: ["سيناريوهات معقدة ممكنة", "يدعم لقطات طويلة"]
    heygen: ["أفاتار جاهز فقط", "لا تخصيص جسدي كامل"]
    d_id: ["Avatar سريع", "خيارات صوت عربية محدودة"]
    synthesia: ["Corporate style", "ممتاز للعروض الرسمية"]
````````````

### قواعد اللغة والتنسيق
- **وصف المشهد**: يُكتب بالإنجليزية مع تفاصيل الكاميرا، الحركة، الإضاءة، البيئة، والأزياء.
- **الحوار**: يُنتج باللهجة المطلوبة مع ذكر النبرة والسرعة لتسهيل التوليف الصوتي.
- **النصوص على الشاشة**: تُذكر كتوجيهات مونتاج، ≤8 كلمات، RTL واضح، تباين ≥4.5:1، وتظهر ضمن `text_overlay`.
- **الصوت**: إذا كان المولد لا يدعم الصوت، أضف توصيات موسيقى/SFX ضمن `post_production.audio_notes`.

### أقواس السرد بحسب النوع
````````````yaml
story_arcs:
  character_based:
    1_attention_hook: "Highlight pain point (2-3s)"
    2_conflict_tension: "تصعيد المشكلة (2-3s)"
    3_solution_intro: "عرض المنتج كحل (3-4s)"
    4_resolution_cta: "طمأنة + CTA واضح (2-3s)"
  product_focused:
    1_product_reveal: "ظهور المنتج بشكل جذاب"
    2_features_showcase: "إبراز المميزات"
    3_benefit_visual: "عرض الفائدة بصرياً"
    4_branding_cta: "هوية العلامة + CTA"
  virtual_influencer:
    1_introduction: "تحية وتعريف الشخصية"
    2_problem_relate: "ذكر المشكلة بنبرة شخصية"
    3_recommendation: "التوصية + دليل"
    4_cta_strong: "CTA قوي ومباشر"
  vfx_cinematic:
    1_wow_moment: "لحظة بصرية مذهلة"
    2_surreal_journey: "رحلة خيالية"
    3_reality_return: "العودة للواقع مع المنتج"
    4_branding: "شعار + CTA"
  educational:
    1_question_hook: "سؤال أو حقيقة صادمة"
    2_steps_tips: "3-5 خطوات واضحة"
    3_recap_benefit: "ملخص الفائدة"
    4_brand_cta: "ربط بالعلامة + CTA"
  awareness_psa:
    1_issue_statement: "طرح المشكلة المجتمعية"
    2_emotional_weight: "إبراز الأثر"
    3_brand_action: "دور العلامة"
    4_invitation: "دعوة للمشاركة أو الالتزام"
  ugc_style:
    1_raw_intro: "افتتاحية عفوية"
    2_problem_story: "موقف شخصي"
    3_solution_reaction: "رد فعل بعد التجربة"
    4cta: "CTA بصيغة محادثة"
````````````

### مكتبة القوالب (Templates)
> استخدم القوالب كنقطة بداية، مع إمكانية التعديل حسب المدخلات.

#### 📦 Template 1 — Product-Focused (6-15s)
```````````markdown
## Product-Focused Video Template
**Best For:** أطعمة، إلكترونيات، أزياء
**AI Generators:** Pika · Runway · Sora 2 · Veo 3
**Audio:** Music + SFX (يُولّد أو يُضاف لاحقاً)
```````````
**Scene Structure (4 Scenes)**
```````````json
[
  {
    "scene_number": "S1",
    "title": "Product Reveal",
    "duration": "2s",
    "visual": {
      "product": "Fresh beef burger on wooden board",
      "camera": "Eye-level, slow dolly-in",
      "lighting": "Warm golden side light",
      "motion": "Gentle steam rising"
    },
    "audio": {
      "music": "Upbeat acoustic guitar (background subtle)",
      "sfx": ["burger sizzle", "steam hiss"],
      "voiceover": null
    },
    "text_overlay": [],
    "technical": {
      "aspect_ratio": "1:1",
      "fps": 24,
      "ai_generator": "Pika"
    }
  },
  {
    "scene_number": "S2",
    "title": "Ingredients Floating",
    "duration": "2s",
    "visual": {
      "product": "Deconstructed burger layers floating mid-air",
      "camera": "Slow 360° orbit",
      "lighting": "Bright studio",
      "effects": "Levitation, sparkle"
    },
    "audio": {
      "sfx": ["soft whoosh"],
      "music": "Continues from S1"
    },
    "text_overlay": [
      {"content": "١٠٠٪ لحم طازج", "language": "AR", "timing": "mid-scene"}
    ],
    "technical": {"fps": 30, "ai_generator": "Runway"}
  },
  {
    "scene_number": "S3",
    "title": "Assembly",
    "duration": "2s",
    "visual": {
      "action": "Top bun lands in slow motion",
      "camera": "Side view static",
      "effects": "Sesame seeds falling"
    },
    "audio": {"sfx": ["soft plop"], "music": "Builds to crescendo"}
  },
  {
    "scene_number": "S4",
    "title": "Branding & CTA",
    "duration": "2s",
    "visual": {
      "product": "Hero shot with steam",
      "camera": "Slight overhead slow zoom-out"
    },
    "audio": {
      "voiceover": {
        "text": "Burger House — طازج، سريع، لذيذ",
        "language": "Bahraini_Arabic",
        "voice": "male_warm"
      },
      "music": "Final uplifting chord"
    },
    "text_overlay": [
      "Burger House",
      "يبدأ من ١.٥ د.ب",
      "#إعلان"
    ],
    "branding": {"logo": "Top-right", "colors": ["gold", "brown", "white"]}
  }
]
```````````
**Post-Generation Notes:** اتساق المنتج، استخدام الموسيقى 60-90BPM، تصدير 1:1 1080p MP4.

#### 🎭 Template 2 — Character-Based (10-30s)
```````````json
[
  {
    "scene_number": "S1",
    "title": "The Problem",
    "duration": "3s",
    "character": {
      "profile": "Male, 26, casual",
      "emotion": "Frustration"
    },
    "environment": "Bahrain apartment, evening light",
    "action": "Opens delivery bag, finds flat burger",
    "dialogue": {
      "language": "Bahraini_Arabic",
      "line": "شنو هالبرجر الممل هذا؟",
      "tone": "frustrated"
    },
    "camera": "Close-up to medium",
    "audio": {"music": "Tense minor", "sfx": ["bag crinkle"]}
  },
  {
    "scene_number": "S2",
    "title": "Discovery",
    "duration": "3s",
    "action": "Scrolling phone, eyes widen",
    "dialogue": {
      "line": "يالله نجرب Burger House...",
      "tone": "curious"
    },
    "audio": {"sfx": ["phone tap", "notification"], "music": "Curious"}
  },
  {
    "scene_number": "S3",
    "title": "Solution",
    "duration": "4s",
    "action": "Opens fresh Burger House bag, bites burger",
    "dialogue": {
      "line": "واو! هذا برجر حقيقي!",
      "tone": "joyful"
    },
    "visual": "Steam, warm lighting"
  },
  {
    "scene_number": "S4",
    "title": "CTA",
    "duration": "2s",
    "text_overlay": ["اطلب الآن", "#إعلان"],
    "audio": {"voiceover": "اطلبه اليوم عبر التطبيق", "tone": "confident"}
  }
]
```````````

#### 🤖 Template 3 — Virtual Influencer (15-25s)
```````````json
{
  "avatar": {
    "name": "Noura",
    "gender": "female",
    "attire": "Modern abaya",
    "voice": "female_confident"
  },
  "scene_flow": [
    {
      "timestamp": "0-3s",
      "script": "مرحبا! أنا نورة...",
      "visual": "Avatar in studio, warm lighting"
    },
    {
      "timestamp": "3-12s",
      "script": "كنت دايماً أدور على برجر طازج...",
      "insert": "Product B-roll cutaways"
    },
    {
      "timestamp": "12-18s",
      "script": "طلبت من Burger House، وش رأيي؟",
      "proof": "4.8★ من 1200 تقييم"
    },
    {
      "timestamp": "18-20s",
      "script": "#إعلان — اطلبه الآن بـ ١.٥ د.ب",
      "cta": "Button overlay: اطلب الآن"
    }
  ],
  "technical": {
    "duration": "20s",
    "aspect_ratio": "9:16",
    "ai_generator": "HeyGen"
  },
  "compliance": ["Avatar consistency", "#إعلان overlay"]
}
```````````

#### 🎆 Template 4 — VFX/Cinematic (15s)
```````````json
[
  {
    "scene": "Explosion",
    "duration": "5s",
    "visual": "Burger explodes in slow motion",
    "camera": "Eye-level zoom-out",
    "effects": ["Energy particles", "Fire sparks"],
    "audio": {"sfx": ["bass drop"], "music": "Epic orchestral"}
  },
  {
    "scene": "Floating",
    "duration": "5s",
    "visual": "Ingredients levitate with golden spotlight",
    "audio": {"sfx": ["magical shimmer"], "music": "Suspenseful strings"}
  },
  {
    "scene": "Reassembly",
    "duration": "3s",
    "visual": "Ingredients snap back magnetically",
    "audio": {"sfx": ["magnetic snap"], "music": "Triumphant"}
  },
  {
    "scene": "Hero Shot",
    "duration": "2s",
    "text_overlay": "Burger House — طازج كل يوم",
    "audio": {"sfx": ["sizzle"], "music": "Final note"},
    "branding": {"logo": "Center", "cta": "اطلب الآن", "disclosure": "#إعلان"}
  }
]
```````````

#### 📚 Template 5 — Educational (40s)
```````````json
{
  "scenes": [
    {
      "label": "Intro",
      "duration": "5s",
      "visual": "Question overlay",
      "text_overlay": "هل تعرف كيف تختار برجر طازج؟",
      "voiceover": "كثير ناس ما يعرفون الفرق..."
    },
    {
      "label": "Step 1",
      "duration": "10s",
      "visual": "Fresh vs old meat split screen",
      "voiceover": "اللحم الطازج لونه بني غامق..."
    },
    {
      "label": "Step 2",
      "duration": "10s",
      "visual": "Steam rising, juicy shot",
      "voiceover": "البرجر الصح يطلع منه بخار..."
    },
    {
      "label": "Step 3",
      "duration": "10s",
      "visual": "Customer smiling",
      "voiceover": "دايم اختبر الخبز..."
    },
    {
      "label": "CTA",
      "duration": "5s",
      "text_overlay": "#إعلان — اطلب الآن",
      "cta": "Swipe Up"
    }
  ],
  "audio": {
    "music": "Calm educational",
    "voiceover_language": "Bahraini_Arabic"
  }
}
```````````

#### 📢 Template 6 — Awareness/PSA (20s)
```````````json
{
  "message": "قلّل الهدر الغذائي",
  "structure": [
    {"time": "0-4s", "visual": "Food waste montage", "stat": "1/3 من الطعام يهدر"},
    {"time": "4-12s", "visual": "Kitchen staff donating meals", "voiceover": "#إعلان — Burger House يتبرع يومياً"},
    {"time": "12-18s", "visual": "Customer receiving meal", "cta": "شاركنا — اطلب وجبتك وتبرع"},
    {"time": "18-20s", "visual": "Logo + #إعلان", "audio": "Inspiring crescendo"}
  ],
  "tone": "Inspirational"
}
```````````

#### 📱 Template 7 — UGC Style (15s)
```````````json
{
  "recording_style": "Vertical phone, handheld",
  "script": [
    "0-3s: Hey جماعة! شوفوا شنو وصلني!",
    "3-10s: Unboxing + reaction (wow steam)",
    "10-15s: Honest verdict + CTA: اطلبوه قبل ما يخلص العرض"
  ],
  "audio": {
    "dialogue_language": "Bahraini_Arabic",
    "background": "Ambient home sounds"
  },
  "compliance": "#إعلان overlay + verbal mention"
}
```````````

#### 🎞️ Template 8 — Documentary (45s)
```````````json
{
  "opening": "Kitchen door opens, camera enters",
  "process": [
    {"time": "5-15s", "visual": "Chef selects fresh meat", "voiceover": "كل صباح نستلم لحم طازج ١٠٠٪"},
    {"time": "15-25s", "visual": "Hand-press patties", "sfx": "Sizzle"},
    {"time": "25-35s", "visual": "Assembling burger", "voiceover": "نضيف خضار محلية"}
  ],
  "closing": {
    "visual": "Burger handed to customer",
    "text_overlay": "طازج. صادق. لذيذ.",
    "cta": "اطلب الآن",
    "disclosure": "#إعلان"
  }
}
```````````

#### 🔀 Template 9 — Mixed Carousel (5 Slides)
```````````json
{
  "slides": [
    {"index": 1, "type": "image", "content": "Hook", "text": "تعبت من البرجر الممل؟"},
    {"index": 2, "type": "image", "content": "Agitation", "text": "كل مرة نفس الخيبة..."},
    {"index": 3, "type": "video", "duration": "8s", "content": "Solution", "text": "جرّب Burger House — طازج كل يوم"},
    {"index": 4, "type": "image", "content": "Proof", "text": "٤.٨/٥ من ١٠٠٠ عميل"},
    {"index": 5, "type": "image", "content": "CTA", "text": "اطلب الآن — يبدأ من ١.٥ د.ب | #إعلان"}
  ],
  "caption": "من البرجر الممل 😞 إلى الطازج اللذيذ 🍔! اسحب لتشوف الفرق... #برجر_البحرين #إعلان",
  "hashtags": ["#برجر_هاوس", "#طعام_طازج", "#البحرين", "#إعلان"]
}
```````````

### توطين البحرين (Bahrain Localization Pack)
````````````yaml
bahrain_localization:
  character_based:
    attire: "ملابس كاجوال معاصرة، دشداشة رسمية، عباية محتشمة"
    settings: "مقاهي محلية، شوارع المنامة، منازل حديثة"
    cultural_notes:
      - "تجنب اللقطات الحميمية"
      - "احترام الخصوصية"
      - "إبراز المناسبات: رمضان، العيد، اليوم الوطني"
  product_focused:
    color_palette: "ذهبي، بيج، أخضر داكن"
    props: "أطباق عربية، فناجين قهوة، ديكور محلي"
    typography: "خطوط Cairo أو Tajawal للـRTL"
  virtual_influencer:
    avatar_design: "ملامح خليجية، حجاب أو بدون وفق الهوية"
    language: "لهجة بحرينية طبيعية"
    references: "ذكر أماكن محلية (الرفاع، السيتي سنتر)"
  language_rule:
    scenario_text: "English visual description"
    dialogue_voiceover: "اللهجة التي يحددها المستخدم"
    text_overlay: "Arabic RTL عند الحاجة"
````````````

### خوارزمية توليد السيناريو (Pseudo-Code)
````````````python
def generate_video_scenario(input_data):
    ensure_required_fields(input_data)
    template = select_template(input_data.scenario_type)
    generator = pick_generator(input_data)
    if missing_critical_info(input_data):
        ask_for_clarification()
        assume_defaults_if_needed()
    scenes = build_scenes(template, input_data)
    audio_plan = craft_audio_plan(input_data.audio_type, input_data.dialogue)
    compliance = run_compliance_checks(scenes, audio_plan)
    return {
        "scenario_type": input_data.scenario_type,
        "ai_generator": generator,
        "scenes": scenes,
        "audio": audio_plan,
        "compliance": compliance,
        "post_production": recommend_post_steps(input_data)
    }
````````````

### قدرات المولدات (اختيار سريع)
| المولد | حوار عربي | نصوص على الشاشة | صوت مدمج | أفضل الاستخدامات | ملاحظات |
|--------|-----------|------------------|----------|-------------------|---------|
| Kling Wan 2.5 | ✅ | ✅ | ✅ | قصص وشخصيات | دعم جيد للحركة |
| Sora 2 | ✅ | محدود | ✅ | سيناريوهات طويلة | حوار محدود حاليًا |
| Veo 3 | ✅ | محدود | ✅ | Product Focused | التزام عالٍ بالبرومبت |
| Veo 3.1 | ✅ ممتاز | ✅ | ✅ | محتوى عربي | الأفضل للهجات الخليجية |
| Runway Gen-3 | ❌ | ❌ | ❌ | VFX سريع | استخدم صوت خارجي |
| Pika Labs | ❌ | ❌ | ❌ | منتجات ثابتة | سهل التخصيص |
| Luma Dream | ❌ | ❌ | ❌ | مشاهد بسيطة | لقطات واقعية |
| HeyGen | ✅ | ✅ | ✅ | Virtual Influencer | أفاتار جاهز |
| D-ID | ✅ | ✅ | ✅ | Avatar سريع | تخصيص محدود |
| Synthesia | ✅ | ✅ | ✅ | محتوى Corporate | أصوات احترافية |

### المخرجات المتوقعة (JSON)
````````````json
{
  "video_scenario": {
    "scenario_type": "character_based",
    "campaign": "Burger House Bahrain Launch",
    "duration_total": "12s",
    "aspect_ratio": "9:16",
    "ai_generator": "Veo_3.1",
    "audio_generation_supported": true,
    "dialogue_language": "Bahraini_Arabic",
    "audio_type": "dialogue_generated + music_sfx_generated",
    "scenes": [
      {
        "number": "S1",
        "title": "The Problem",
        "duration": "3s",
        "type": "character_based",
        "character": {"appearance": "Male 26", "emotion": "frustration"},
        "sound_voice": {
          "dialogue": "شنو هالبرجر الممل هذا؟",
          "tone": "frustrated",
          "accent": "Bahraini"
        },
        "sfx": ["bag crinkle"],
        "music": "tense minor"
      }
    ],
    "audio_generation_notes": {
      "generator": "Veo 3.1",
      "lip_sync": "auto",
      "post_production": "اختياري"
    },
    "continuity_notes": {
      "character": "نفس الملابس",
      "environment": "تحسن الإضاءة تدريجي",
      "props": "إزالة الكيس القديم قبل S3"
    },
    "post_production_notes": {
      "text_overlay": "DaVinci Resolve",
      "music": "Replace if needed",
      "disclosure": "#إعلان في S4"
    },
    "compliance": "✅",
    "ready_for_generation": true
  },
  "summary": [
    "ما تم توليده: سيناريو character_based (12s، 4 مشاهد) لقناة TikTok.",
    "الامتثال: ✅ Veo 3.1 | ✅ #إعلان | ✅ RTL | ✅ ثقافة بحرينية.",
    "الخطوة التالية: رفع السيناريو إلى Veo 3.1 وتنفيذ تعديلات المونتاج." ]
}
````````````

**انتهى قسم MODULE_08 (المحتوى مدمج ضمن 08_09_video_and_content.md)**

<!-- CMIS:END::MODULE_08 -->

---

<!-- CMIS:START::MODULE_09 -->
# MODULE 09 — Content Planning Intelligence

<!-- CMIS:START::PURPOSE -->
## الغرض (≤ سطرين)
- تصميم خطط محتوى متكاملة (خصوصاً لإنستقرام وتيك توك) تربط أهداف الأعمال بأهداف المحتوى، وتوزّع أنواع المحتوى (صور، فيديوهات، كاروسيل، بث مباشر) بشكل استراتيجي لتحقيق نمو المبيعات، بناء الثقة، والاحتفاظ بالعملاء.
<!-- CMIS:END::PURPOSE -->

<!-- CMIS:START::INPUTS -->
## المدخلات (JSON)
```json
{
  "brand": "",
  "product_or_service": "",
  "objective": "awareness|consideration|conversion|retention",
  "target_audience": "",
  "platform": "Instagram|Facebook|TikTok|LinkedIn|Multi-Platform",
  "planning_period": "week|month|quarter",
  "posting_frequency": "daily|5x_week|3x_week|2x_day",
  "budget_level": "low|medium|high",
  "channels": ["Stories", "Reels", "Static", "Live"],
  "trend_research": {
    "topic": "",
    "language": "ar",
    "depth": "summary|detailed"
  }
}
```

### المدخلات الأصلية (منسوخة حرفيًا)
`````json
{
  "platform": "Instagram|Facebook|TikTok|LinkedIn|Multi-Platform",
  "planning_period": "week|month|quarter",
  "brand": "",
  "product_or_service": "",
  "marketing_objective": "awareness|conversion|retention",
  "target_audience": "",
  "posting_frequency": "daily|3x_week|5x_week|2x_day",
  "budget_level": "low|medium|high",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD" }
}
`````
<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->
## خطوات المعالجة
1. **تأكيد البيانات**: تحقق من التوافق بين `objective`, `platform`, `planning_period`, `posting_frequency`، واضبط الافتراضات (مثلاً `posting_frequency` الافتراضي = `5x_week`).
2. **تحليل الهدف**: حدد توزيع الأهداف (Awareness/Consideration/Conversion/Retention) بناءً على الهدف الرئيسي.
3. **توليد مصفوفات المحتوى**: أنشئ قوائم المحتوى المحتمل (Static، Video، Stories، Live، Community) واربطها بالمراحل (TOFU/MOFU/BOFU/Loyalty).
4. **تنويعات خطة المحتوى**: أخرج 3 خطط (v1-v3) بإستراتيجيات مختلفة (مثلاً: Performance Heavy، Storytelling Focused، Community-Led).
5. **DCO Expansion**: عند طلب توسيع ديناميكي، أضف خطط v4-v8 لكل قناة رئيسية مع تغيير نوع المحتوى وتكرار النشر.
6. **دمج الأبحاث**: في حال توافر `trend_research`, أدرج ملخصًا + مصدر داخل `insights.trends` وامنح أفكار محتوى مرتبطة بالترند.
7. **خطة النشر**: بُنى جدولاً زمنياً بالتواريخ أو الأيام، يتضمن النوع، الوصف، الهدف، توقع KPI، هاشتاقات، CTA، ومتطلبات الإنتاج.
8. **تحقق الامتثال**: تأكد من ( #إعلان، BHD، CTA واحد لكل منشور ترويجي، التنويع بين الأنواع، عدم تكرار نوعين متشابهين يوميًا).
9. **المخرجات**: التزم بـJSON Schema الموثق وأضف ملخصًا تنفيذيًا من 3 أسطر.
<!-- CMIS:END::STEPS -->

<!-- CMIS:START::MIXER_STEP -->
### Mixer (خطط المحتوى)
- أنشئ `content_mix_matrix` تربط كل هدف بمحتوى محدد (مثلاً Awareness → Educational Video، Consideration → Carousel Proof، Conversion → Offer Reel).
- غيّر نبرة الكتابة عبر التنويعات (ملهم، استشاري، مباشر في المبيعات).
- اربط كل تنويع بـ `distribution_rationale` يشرح سبب اختيار القنوات والأنواع.
<!-- CMIS:END::MIXER_STEP -->

### أنواع المحتوى (Static Visual)
`````yaml
static_content_types:
  single_image_ad:
    description: "صورة واحدة بعرض مباشر"
    ratio: "1:1 | 4:5 | 9:16"
    elements: ["منتج", "CTA", "سعر BHD", "#إعلان"]
    frequency: "20-30%"
  carousel_images:
    description: "كاروسيل 5-7 شرائح"
    structure: ["Hook", "Features", "Proof", "CTA"]
    frequency: "15-20%"
  infographic:
    description: "إنفوجرافيك تعليمي أو إحصائي"
    ratio: "9:16 أو 1:1"
    elements: ["أرقام", "أيقونات", "مصدر"]
    frequency: "10-15%"
`````

### أنواع المحتوى (Video)
`````yaml
video_content_types:
  product_creative_video:
    duration: "6-15s"
    style: "سينمائي"
    frequency: "15-20%"
  service_creative_video:
    duration: "10-20s"
    style: "قبل/بعد"
    frequency: "15-20%"
  character_story_video:
    duration: "10-30s"
    style: "سرد قصصي"
    frequency: "10-15%"
  virtual_influencer_video:
    duration: "15-30s"
    style: "Avatar talking head"
    frequency: "5-10%"
  vfx_cinematic_video:
    duration: "10-20s"
    style: "خدع بصرية"
    frequency: "5-10%"
  documentary_style_video:
    duration: "30-60s"
    style: "واقعي"
    frequency: "5-10%"
  educational_video:
    duration: "20-60s"
    style: "How-To"
    frequency: "15-20%"
  awareness_psa_video:
    duration: "15-30s"
    style: "رسالة توعوية"
    frequency: "5%"
  ugc_style_video:
    duration: "10-20s"
    style: "كاميرا هاتف"
    frequency: "10-15%"
  mixed_carousel_video:
    duration: "5-8s (داخل كاروسيل)"
    style: "Hybrid"
    frequency: "10%"
`````

### استراتيجية التوزيع الافتراضية (هدف Conversion)
`````yaml
content_distribution_conversion_goal:
  awareness:
    share: "30%"
    mix: {educational_video: "10%", awareness_psa_video: "5%", infographic: "10%", documentary_style_video: "5%"}
  consideration:
    share: "40%"
    mix: {product_creative_video: "15%", service_creative_video: "10%", character_story_video: "10%", ugc_style_video: "5%"}
  conversion:
    share: "30%"
    mix: {single_image_ad: "10%", carousel_images: "10%", virtual_influencer_video: "5%", mixed_carousel_video: "5%"}
  engagement_bonus:
    vfx_cinematic_video: "5% (اختياري)"
`````

### قالب خطة أسبوعية (Instagram)
`````markdown
| اليوم | الوقت | النوع | الوصف | الهدف | Hashtags |
|------|------|------|-------|-------|----------|
| الأحد | 12 ظهراً | Product Creative Video | برجر يدور 360° مع steam | Awareness | #برجر_البحرين #طعام_طازج #إعلان |
| الاثنين | 7 مساءً | Single Image Ad | عرض خاص: وجبة كاملة 2 BHD | Conversion | #عروض #برجر_هاوس #إعلان |
| الثلاثاء | 1 ظهراً | Educational Video | "3 علامات البرجر الطازج" | Consideration | #نصائح_طعام #برجر_صحي |
| الأربعاء | 6 مساءً | UGC Style Video | عميل يوثق التجربة | Conversion | #تجربة_عملاء #برجر_حقيقي #إعلان |
| الخميس | 12 ظهراً | Carousel Images | مميزات البرجر | Consideration | #مميزات #جودة #إعلان |
| الجمعة | 8 مساءً | Virtual Influencer Video | أفاتار يوصي بالمنتج | Conversion | #توصية #أفضل_برجر #إعلان |
| السبت | 2 ظهراً | Infographic | 5 أسباب تحب برجر هاوس | Awareness | #إنفوجرافيك #حقائق |
`````

### قالب خطة شهرية (30 يوم)
`````json
{
  "monthly_content_plan": {
    "brand": "برجر هاوس",
    "goal": "زيادة الطلبات بنسبة 25%",
    "platform": "Instagram",
    "posting_frequency": "daily (1 post + 3 stories)",
    "week_1_theme": "الافتتاح والتعريف",
    "week_1_content": [
      {"day": 1, "type": "product_creative_video", "goal": "awareness"},
      {"day": 2, "type": "single_image_ad", "goal": "conversion"},
      {"day": 3, "type": "educational_video", "goal": "consideration"},
      {"day": 4, "type": "ugc_style_video", "goal": "conversion"},
      {"day": 5, "type": "carousel_images", "goal": "consideration"},
      {"day": 6, "type": "virtual_influencer_video", "goal": "conversion"},
      {"day": 7, "type": "infographic", "goal": "awareness"}
    ],
    "week_2_theme": "بناء الثقة والإثبات",
    "week_2_content": [
      {"day": 8, "type": "character_story_video", "goal": "consideration"},
      {"day": 9, "type": "documentary_style_video", "goal": "awareness"},
      {"day": 10, "type": "product_creative_video", "goal": "awareness"},
      {"day": 11, "type": "carousel_images", "goal": "conversion"},
      {"day": 12, "type": "educational_video", "goal": "consideration"},
      {"day": 13, "type": "ugc_style_video", "goal": "conversion"},
      {"day": 14, "type": "vfx_cinematic_video", "goal": "awareness"}
    ],
    "week_3_theme": "التحويل والعروض",
    "week_3_content": [
      {"day": 15, "type": "single_image_ad", "goal": "conversion"},
      {"day": 16, "type": "virtual_influencer_video", "goal": "conversion"},
      {"day": 17, "type": "product_creative_video", "goal": "consideration"},
      {"day": 18, "type": "mixed_carousel_video", "goal": "conversion"},
      {"day": 19, "type": "character_story_video", "goal": "consideration"},
      {"day": 20, "type": "single_image_ad", "goal": "conversion"},
      {"day": 21, "type": "educational_video", "goal": "consideration"}
    ],
    "week_4_theme": "الاحتفاظ والمجتمع",
    "week_4_content": [
      {"day": 22, "type": "awareness_psa_video", "goal": "brand"},
      {"day": 23, "type": "ugc_style_video", "goal": "conversion"},
      {"day": 24, "type": "carousel_images", "goal": "conversion"},
      {"day": 25, "type": "documentary_style_video", "goal": "awareness"},
      {"day": 26, "type": "product_creative_video", "goal": "consideration"},
      {"day": 27, "type": "virtual_influencer_video", "goal": "conversion"},
      {"day": 28, "type": "vfx_cinematic_video", "goal": "awareness"}
    ],
    "bonus_days": [
      {"day": 29, "type": "infographic", "goal": "recap"},
      {"day": 30, "type": "single_image_ad", "goal": "conversion"}
    ],
    "stories_daily": ["Behind-the-scenes", "Customer reviews", "Polls", "Countdown"],
    "kpi_targets": {
      "reach": "150000-200000",
      "engagement_rate": "4-6%",
      "website_clicks": "3000-5000",
      "conversions": "300-500 orders",
      "roi": "3-5x"
    }
  }
}
`````

### خوارزمية توليد خطة المحتوى
`````python
def generate_content_plan(input_data):
    ratios = pick_goal_distribution(input_data.objective)
    total_posts = infer_total_posts(input_data.planning_period, input_data.posting_frequency)
    mix = allocate_content_types(ratios, total_posts)
    schedule = []
    for day in range(1, total_posts + 1):
        stage = determine_stage(day, mix)
        content_type = select_content_type(stage, input_data.platform, history=schedule)
        entry = build_post_entry(day, content_type, stage, input_data)
        schedule.append(entry)
    ensure_no_repetition(schedule)
    return {
        "content_mix": mix,
        "schedule": schedule,
        "stories_strategy": craft_story_plan(input_data),
        "kpis": estimate_kpis(input_data.objective, total_posts)
    }
`````

### مثال مخرجات (JSON)
`````json
{
  "content_plan": {
    "brand": "برجر هاوس البحرين",
    "platform": "Instagram",
    "period": "month",
    "goal": "زيادة الطلبات بنسبة 25%",
    "posting_frequency": "daily",
    "content_distribution": {
      "awareness": "30% (9 posts)",
      "consideration": "40% (12 posts)",
      "conversion": "30% (9 posts)"
    },
    "schedule": [
      {
        "day": 1,
        "content_type": "product_creative_video",
        "description": "برجر يدور 360° مع steam وإضاءة ذهبية",
        "duration": "10s",
        "ai_generator": "Pika Labs",
        "goal": "awareness",
        "expected_reach": "5000-8000",
        "hashtags": ["#برجر_البحرين", "#طعام_طازج", "#إعلان"],
        "caption": "#إعلان — برجر حقيقي، طازج كل يوم 🍔",
        "cta": "اطلب الآن",
        "compliance": "✅"
      },
      {
        "day": 2,
        "content_type": "single_image_ad",
        "description": "صورة برجر + نص عرض 2 BHD",
        "ratio": "4:5",
        "goal": "conversion",
        "expected_clicks": "200-350",
        "hashtags": ["#عروض", "#برجر_هاوس", "#إعلان"],
        "caption": "#إعلان — عرض خاص! وجبة كاملة بـ٢ د.ب",
        "cta": "اطلب الآن",
        "compliance": "✅"
      }
    ],
    "stories_strategy": {
      "frequency": "3 stories/day",
      "themes": ["Behind-the-scenes", "Polls", "Countdown", "Reviews"]
    },
    "kpi_targets": {
      "reach": "150000-200000",
      "engagement_rate": "4-6%",
      "website_clicks": "3000-5000",
      "conversions": "300-500",
      "roi": "3-5x"
    },
    "insights": {
      "trends": [
        {
          "topic": "#BahrainFoodies",
          "summary": "زيادة 18% في محادثات الطعام المحلي خلال آخر 30 يوم",
          "source": "[مصدر: Deloitte]"
        }
      ]
    }
  },
  "summary": [
    "خطة محتوى شهرية لإنستقرام: 30 منشور + 90 ستوري.",
    "تنويع المحتوى يغطي Awareness/Consideration/Conversion بنسبة 30/40/30.",
    "الخطوة التالية: تمرير كل منشور للوحدات 01-08 لتوليد النسخ، التصاميم، والسيناريوهات."
  ]
}
`````

**انتهى قسم MODULE_09 (المحتوى مدمج ضمن 08_09_video_and_content.md)**

<!-- CMIS:END::MODULE_09 -->

---

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
        "composition": "",
        "background": "",
        "lighting": "",
        "colors": "",
        "highlight": "",
        "de_emphasize": "",
        "element_positions": "",
        "ratio": "9:16",
        "motion": ""
      },
      "used_fields": {
        "marketing_objective": "",
        "emotional_triggers": [],
        "channels": [],
        "segments": [],
        "pains": [],
        "marketing_frameworks": [],
        "marketing_strategies": [],
        "tones": [],
        "features": [],
        "benefits": [],
        "transformational_benefits": [],
        "usps": [],
        "message_map": [],
        "proofs": [],
        "assumptions": []
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
- التزم بالقواعد نفسها عند إنشاء تنويعات جديدة.
<!-- CMIS:END::REFS_QUALITY -->

<!-- CMIS:END::MODULE_08_09 -->
