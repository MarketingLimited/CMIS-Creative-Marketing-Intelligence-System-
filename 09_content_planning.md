# **09_content_planning.md**

## **الغرض**

توليد **خطط محتوى متكاملة** لحسابات السوشال ميديا (خاصة إنستقرام) مع تنويع استراتيجي في أنواع المحتوى البصري والفيديو لتحقيق أهداف تسويقية محددة.

**الهدف الافتراضي:** زيادة المبيعات/الطلبات
**السوق الافتراضي:** مملكة البحرين (AR/RTL، BHD)

> **ملاحظة امتثال:** كل أمثلة النسخ والخطط تبدأ بـ`#إعلان` في أول جملة عند استخدام المحتوى لأغراض ترويجية مدفوعة، وتعرض الأسعار أو العروض بالـBHD.

---

## **المدخلات المتوقعة**
`````json
{
  "platform": "Instagram|Facebook|TikTok|LinkedIn|Multi-Platform",
  "planning_period": "week|month|quarter",
  "brand": "",
  "product_or_service": "",
  "marketing_objective": "sales|leads|awareness|engagement|traffic|retention",
  "target_audience": "",
  "posting_frequency": "daily|3x_week|5x_week|2x_day",
  "budget_level": "low|medium|high",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD" }
}
`````

---

## **أنواع المحتوى المتاحة**

### **📸 محتوى بصري ثابت (Static Visual Content)**
`````yaml
static_content_types:
  
  1_single_image_ad:
    description: "إعلان صورة واحدة احترافية"
    best_for: ["عروض سريعة", "منتج واحد", "إعلان مباشر"]
    ratio: "1:1 | 4:5 | 9:16"
    elements: ["منتج/خدمة", "نص overlay", "CTA", "سعر BHD", "وسم #إعلان واضح"]
    frequency: "20-30% من المحتوى"
    
  2_carousel_images:
    description: "كاروسيل صور متعددة (2-10 صور)"
    best_for: ["عرض مميزات متعددة", "قبل/بعد", "مجموعة منتجات"]
    ratio: "1:1 (موحّد عبر الصور)"
    structure:
      - "Slide 1: Hook/مشكلة"
      - "Slides 2-4: مميزات/حلول"
      - "Slide 5: Proof/تقييمات"
      - "Slide Final: CTA + سعر + #إعلان"
    frequency: "15-20% من المحتوى"
    
  3_infographic:
    description: "إنفوجرافيك تعليمي أو إحصائي"
    best_for: ["محتوى تعليمي", "إحصائيات", "مقارنات"]
    ratio: "9:16 (vertical) | 1:1"
    elements: ["أيقونات", "أرقام كبيرة", "ألوان العلامة", "مصدر", "#إعلان عند الترويج"]
    frequency: "10-15% من المحتوى"
`````

---

### **🎬 محتوى فيديو (Video Content)**
`````yaml
video_content_types:
  
  1_product_creative_video:
    description: "فيديو إبداعي للمنتجات (Product-Focused)"
    duration: "6-15s"
    style: "سينمائي، حركات كاميرا احترافية، إضاءة درامية"
    best_for: ["منتجات ملموسة", "طعام", "أزياء", "إلكترونيات"]
    ai_generators: ["Pika", "Runway", "Sora 2", "Veo 3"]
    audio: "موسيقى + SFX"
    frequency: "15-20% من المحتوى"
    examples:
      - "برجر يدور 360° مع steam"
      - "ساعة تطفو مع إضاءة ذهبية"
      - "هاتف ينكشف بحركة بطيئة"
    
  2_service_creative_video:
    description: "فيديو إبداعي للخدمات (Service Showcase)"
    duration: "10-20s"
    style: "مشاهد قبل/بعد، تحوّل بصري، نتائج"
    best_for: ["خدمات تنظيف", "صيانة", "تجميل", "استشارات"]
    ai_generators: ["Runway", "Sora 2", "Veo 3"]
    audio: "موسيقى متفائلة + voiceover اختياري"
    frequency: "15-20% من المحتوى"
    examples:
      - "غرفة فوضوية → منظمة (time-lapse)"
      - "سجادة متسخة → نظيفة (split screen)"
      - "مكتب قديم → محدّث (transition)"
    
  3_character_story_video:
    description: "فيديو قصة مع شخصيات (Character-Based)"
    duration: "10-30s"
    style: "سرد قصصي، حوار، مشكلة→حل"
    best_for: ["بناء ثقة", "عاطفي", "relatable"]
    ai_generators: ["Veo 3.1", "Sora 2", "Kling Wan 2.5"]
    audio: "حوار بلهجة بحرينية + موسيقى + SFX"
    frequency: "10-15% من المحتوى"
    examples:
      - "عميل محبط من برجر سيء → يجرب برجر هاوس"
      - "أم متعبة من التنظيف → تكتشف خدمة سكوب لاين"
    
  4_virtual_influencer_video:
    description: "إنفلونسر افتراضي (AI Avatar) يعلن"
    duration: "15-30s"
    style: "شخصية رقمية واقعية تتحدث مباشرة للكاميرا"
    best_for: ["مصداقية", "توصية شخصية", "محتوى متكرر"]
    ai_generators: ["HeyGen", "D-ID", "Synthesia", "Veo 3.1"]
    audio: "حوار مُولَّد (لهجة بحرينية/خليجية)"
    frequency: "5-10% من المحتوى"
    script_structure:
      - "Hook: مشكلة أو سؤال"
      - "Body: عرض المنتج/الخدمة"
      - "Proof: تقييم أو رقم"
      - "CTA: دعوة واضحة"
    notes:
      - "الشخصية الافتراضية يجب أن تكون متسقة عبر الفيديوهات"
      - "ملابس محتشمة ملائمة للبحرين"
      - "نبرة ودية احترافية"
    
  5_vfx_cinematic_video:
    description: "خدع بصرية وخيال سينمائي (VFX/CGI)"
    duration: "10-20s"
    style: "تأثيرات خاصة، انفجارات، تطاير، تحوّلات غير واقعية"
    best_for: ["جذب انتباه", "viral potential", "منتجات فريدة"]
    ai_generators: ["Runway Gen-3", "Pika", "Sora 2"]
    audio: "موسيقى دراما + SFX قوية"
    frequency: "5-10% من المحتوى (محتوى مميز)"
    examples:
      - "برجر ينفجر لمكونات تطير ثم تعود"
      - "منتج يتحول من عادي لذهبي مع particles"
      - "شخص يقفز عبر الزمن (خدمة سريعة)"
    notes:
      - "لا تبالغ حتى لا يفقد مصداقية"
      - "استخدم بحذر مع منتجات جادة (B2B)"
    
  6_documentary_style_video:
    description: "فيديو وثائقي (Documentary/Behind-the-Scenes)"
    duration: "30-60s"
    style: "كاميرا واقعية، مقابلات، صوت طبيعي"
    best_for: ["بناء ثقة", "شفافية", "علامة تجارية"]
    production: "تصوير حقيقي (ليس AI) أو AI مع أسلوب realistic"
    audio: "voiceover + أصوات بيئة"
    frequency: "5-10% من المحتوى"
    examples:
      - "كيف نحضّر البرجر (مطبخ خلف الكواليس)"
      - "يوم في حياة فريق التنظيف"
      - "قصة تأسيس العلامة"
    
  7_educational_video:
    description: "فيديو تعليمي (How-to/Tutorial)"
    duration: "20-60s"
    style: "خطوات واضحة، نص على الشاشة، بطيء"
    best_for: ["بناء سلطة", "engagement عالي", "قيمة مجانية"]
    ai_generators: ["أي مولد + نصوص في المونتاج"
    audio: "voiceover تعليمي + موسيقى هادئة"
    frequency: "15-20% من المحتوى"
    examples:
      - "3 خطوات للحفاظ على البرجر ساخن"
      - "كيف تنظف السجاد بنفسك (ثم اذكر خدمتك كحل أسهل)"
      - "5 علامات تحتاج صيانة سيارتك"
    
  8_awareness_psa_video:
    description: "فيديو توعوي (Awareness/PSA)"
    duration: "15-30s"
    style: "رسالة اجتماعية، نبرة جادة أو ملهمة"
    best_for: ["brand values", "مسؤولية اجتماعية", "بناء صورة"]
    audio: "موسيقى ملهمة + voiceover قوي"
    frequency: "5% من المحتوى"
    examples:
      - "أهمية الحفاظ على النظافة (شركة تنظيف)"
      - "لا تهدر الطعام (مطعم)"
      - "اليوم الوطني البحريني (أي علامة)"
    
  9_ugc_style_video:
    description: "محتوى من إنشاء المستخدم (UGC Style)"
    duration: "10-20s"
    style: "غير مصقول، هاتف عمودي، شخصي"
    best_for: ["مصداقية", "relatable", "تكلفة منخفضة"]
    ai_generators: ["Veo 3.1", "Kling Wan 2.5"]
    audio: "حوار طبيعي + أصوات بيئة"
    frequency: "10-15% من المحتوى"
    examples:
      - "كنت متردد بس جربت... واو!"
      - "شوفوا شنو وصلني (unboxing)"
    
  10_mixed_carousel_video:
    description: "كاروسيل صور مع فيديو (Hybrid)"
    structure:
      - "Slides 1-2: صور ثابتة (Hook)"
      - "Slide 3: فيديو قصير 5-8s (Proof/Action)"
      - "Slides 4-5: صور (CTA)"
    best_for: ["تنويع", "جذب انتباه", "قصة بصرية"]
    frequency: "10% من المحتوى"
`````

---

## **استراتيجية التنويع — Instagram Content Mix**

### **📊 نسب توزيع المحتوى (افتراضي لزيادة المبيعات)**
`````yaml
content_distribution_sales_goal:
  
  awareness_content: "30%"  # لجذب جمهور جديد
    - educational_video: "10%"
    - awareness_video: "5%"
    - infographic: "10%"
    - documentary_video: "5%"
  
  consideration_content: "40%"  # لبناء ثقة واهتمام
    - product_creative_video: "15%"
    - service_creative_video: "10%"
    - character_story_video: "10%"
    - ugc_style_video: "5%"
  
  conversion_content: "30%"  # لتحفيز الشراء
    - single_image_ad: "10%"
    - carousel_images: "10%"
    - virtual_influencer_video: "5%"
    - mixed_carousel_video: "5%"
  
  engagement_content: "optional"  # محتوى خاص للتفاعل
    - vfx_cinematic_video: "5% (مميز)"
    - polls/questions: "حسب الحاجة"
`````

---

## **قالب خطة محتوى أسبوعية (Instagram)**
`````markdown
### **خطة محتوى — الأسبوع 1 (مطعم برجر هاوس — الهدف: زيادة الطلبات)**

| اليوم | الوقت | النوع | الوصف | الهدف | Hashtags |
|------|------|------|-------|-------|----------|
| **الأحد** | 12 ظهراً | Product Creative Video | برجر يدور 360° مع steam، موسيقى، 10s | Awareness | #برجر_البحرين #طعام_طازج #إعلان |
| **الاثنين** | 7 مساءً | Single Image Ad | عرض خاص: وجبة كاملة 2 BHD | Conversion | #عروض #برجر_هاوس #إعلان |
| **الثلاثاء** | 1 ظهراً | Educational Video | "3 علامات البرجر الطازج" (30s) | Consideration | #نصائح_طعام #برجر_صحي |
| **الأربعاء** | 6 مساءً | UGC Style Video | عميل يفتح الطلب ويتفاجأ بالجودة (15s) | Conversion | #تجربة_عملاء #برجر_حقيقي #إعلان |
| **الخميس** | 12 ظهراً | Carousel Images (5 slides) | مميزات برجر هاوس (لحم طازج، صوصات...) | Consideration | #مميزات #جودة #إعلان |
| **الجمعة** | 8 مساءً | Virtual Influencer Video | إنفلونسر افتراضي يوصي بالبرجر (20s) | Conversion | #توصية #أفضل_برجر #إعلان |
| **السبت** | 2 ظهراً | Infographic | "5 أسباب نحب برجر هاوس" (إحصائيات) | Awareness | #إنفوجرافيك #حقائق |

**المحتوى الإضافي (Stories):**
- Behind-the-scenes: تحضير البرجر (يومي)
- Polls: "أي صوص تفضل؟"
- Countdown: عرض ينتهي الأحد
`````

---

## **قالب خطة محتوى شهرية (30 يوم)**
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
      {"day": 14, "type": "vfx_cinematic_video", "goal": "awareness (viral)"}
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
      {"day": 28, "type": "vfx_cinematic_video", "goal": "awareness (viral)"}
    ],
    
    "bonus_days": [
      {"day": 29, "type": "infographic", "goal": "recap month stats"},
      {"day": 30, "type": "single_image_ad", "goal": "conversion (final push)"}
    ],
    
    "stories_daily": [
      "Behind-the-scenes",
      "Customer reviews",
      "Polls & Questions",
      "Countdown timers",
      "Limited offers"
    ]
  }
}
`````

---

## **خوارزمية توليد خطة محتوى تلقائية**
`````python
def generate_content_plan(input):
    # 1. تحليل الهدف
    if input.goal == "sales":
        conversion_ratio = 0.30
        consideration_ratio = 0.40
        awareness_ratio = 0.30
    elif input.goal == "awareness":
        conversion_ratio = 0.15
        consideration_ratio = 0.30
        awareness_ratio = 0.55
    elif input.goal == "engagement":
        conversion_ratio = 0.20
        consideration_ratio = 0.35
        awareness_ratio = 0.45
    
    # 2. حساب عدد المنشورات
    if input.period == "week":
        total_posts = 7
    elif input.period == "month":
        total_posts = 30
    
    # 3. توزيع الأنواع
    content_mix = {
        "awareness": int(total_posts * awareness_ratio),
        "consideration": int(total_posts * consideration_ratio),
        "conversion": int(total_posts * conversion_ratio)
    }
    
    # 4. اختيار أنواع المحتوى
    awareness_types = ["educational_video", "infographic", "awareness_video", "documentary"]
    consideration_types = ["product_creative", "service_creative", "character_story", "ugc"]
    conversion_types = ["single_image_ad", "carousel_images", "virtual_influencer", "mixed_carousel"]
    
    # 5. بناء الجدول الزمني
    schedule = []
    for day in range(1, total_posts + 1):
        stage = determine_stage(day, content_mix)
        content_type = select_content_type(stage, input.product_type)
        post = create_post_brief(day, content_type, stage, input)
        schedule.append(post)
    
    # 6. إضافة تنويع استراتيجي
    schedule = add_variety(schedule)  # لا تكرر نفس النوع في يومين متتاليين
    
    return {
        "plan": schedule,
        "content_mix": content_mix,
        "kpis": calculate_expected_kpis(input.goal, total_posts)
    }
`````

---

## **مخرجات الوحدة (JSON)**
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
        "date": "2025-11-01",
        "time": "12:00 PM",
        "content_type": "product_creative_video",
        "description": "برجر يدور 360° مع steam وإضاءة ذهبية",
        "duration": "10s",
        "ai_generator": "Pika Labs",
        "audio": "موسيقى upbeat + sizzle SFX",
        "goal": "awareness",
        "expected_reach": "5000-8000",
        "hashtags": ["#برجر_البحرين", "#طعام_طازج", "#إعلان"],
        "caption": "برجر حقيقي، طازج كل يوم 🍔 جرّب الفرق! #إعلان",
        "cta": "اطلب الآن عبر الرابط",
        "compliance": "✅"
      },
      {
        "day": 2,
        "date": "2025-11-02",
        "time": "07:00 PM",
        "content_type": "single_image_ad",
        "description": "صورة برجر + نص عرض 2 BHD",
        "ratio": "4:5",
        "design_notes": "خلفية داكنة، برجر في المنتصف، سعر overlay كبير ذهبي",
        "goal": "conversion",
        "expected_clicks": "200-350",
        "hashtags": ["#عروض", "#برجر_هاوس", "#إعلان"],
        "caption": "عرض خاص! وجبة كاملة بـ ٢ د.ب فقط — لفترة محدودة 🔥",
        "cta": "اطلب الآن",
        "compliance": "✅"
      }
    ],
    
    "weekly_themes": [
      "الأسبوع 1: الافتتاح والتعريف",
      "الأسبوع 2: بناء الثقة والإثبات",
      "الأسبوع 3: التحويل والعروض",
      "الأسبوع 4: الاحتفاظ والمجتمع"
    ],
    
    "stories_strategy": {
      "frequency": "3 stories/day",
      "types": ["Behind-the-scenes", "Polls", "Countdown", "Reviews"]
    },
    
    "kpi_targets": {
      "reach": "150,000-200,000/month",
      "engagement_rate": "4-6%",
      "website_clicks": "3,000-5,000",
      "conversions": "300-500 orders",
      "roi": "3-5x"
    }
  }
}
`````

---

## **ملخص حالة (3 أسطر)**

* **ما تمّ توليده:** خطة محتوى 30 يوم لإنستقرام، 10 أنواع محتوى متنوعة، توزيع 30% awareness / 40% consideration / 30% conversion.
* **التنويع:** لا تكرار نوع محتوى في يومين متتاليين، تناوب استراتيجي بين فيديو/صور/كاروسيل.
* **الخطوة التالية:** تنفيذ كل منشور عبر الوحدات 01-08 (توليد النصوص، التصاميم، السيناريوهات).

**انتهى ملف 09_content_planning.md**
