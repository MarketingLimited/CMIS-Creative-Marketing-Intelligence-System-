<!-- CMIS:START::PURPOSE -->
## الغرض (سطران كحد أقصى)
- توليد سيناريوهات فيديو احترافية للإعلانات باستخدام **أي مولد فيديو بالذكاء الاصطناعي**، مع دعم **10+ أنواع محتوى فيديو** متنوعة لتغطية جميع احتياجات الحملات التسويقية.
  **أنواع السيناريوهات:**
  1. **Character-Based:** سيناريوهات مع شخصيات وحوار (قصة تسويقية)
  2. **Product-Focused:** مشاهد منتجات/خدمات بدون شخصيات (visual storytelling)
  3. **Virtual Influencer:** أفاتار رقمي يتحدث مباشرة
  4. **VFX/Cinematic:** خدع بصرية وخيال سينمائي
  5. **Documentary:** وثائقي واقعي (Behind-the-Scenes)
  6. **Educational:** تعليمي (How-To/Tutorial)
  7. **Awareness/PSA:** توعوي (Public Service Announcement)
  8. **UGC Style:** محتوى من إنشاء المستخدم
  9. **Mixed Carousel:** كاروسيل صور مع فيديو
  التوطين الافتراضي: **مملكة البحرين** (AR/RTL، عملة BHD)، مع امتثال كامل لحواجز الامتثال والسلامة.
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
    "required": true|false,
    "language": "Bahraini_Arabic|Gulf_Arabic|Egyptian_Arabic|English|None",
    "dialect_notes": "لهجة بحرينية حديثة، نبرة ودية",
    "voice_characteristics": "male_warm|female_confident|neutral_calm"
  },
  "technical_specs": {
    "duration_seconds": [6, 8, 10, 15, 30, 60],
    "aspect_ratio": "9:16|16:9|1:1",
    "scenes_max": 4,
    "ai_generator": "Kling_Wan_2.5|Sora_2|Veo_3|Veo_3.1|Runway|Pika|Luma|HeyGen|D-ID|Synthesia|Any",
    "audio_generation": true|false
  },
  "audio_type": "dialogue_generated|music_sfx_generated|music_only|silent",
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" }
}
````````````
<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. تحليل الطلب.
2. إن وُجد `trend_research` فعّل آلية البحث وادمج الملخص والمصدر في المخرجات.
3. تطبيق القواعد الجوهرية (#إعلان، BHD، RTL، CTA واحد، منع المطلقات…).
4. إنتاج المخرجات وفق القالب أدناه.

### المحتوى الأصلي الكامل (منسوخ حرفيًا)
## **سياسة الامتثال والسلامة (عامة لجميع المولدات)**
````````````yaml
compliance_universal:
  forbidden:
    - "مشاهير أو شخصيات عامة معروفة (إن وُجدت شخصيات)"
    - "نصوص على الشاشة مبالغ فيها (إلا إذا كانت جزءاً طبيعياً من التصميم)"
    - "علامات تجارية منافسة أو شعارات غير مصرح بها"
    - "ادعاءات مبالغ فيها (100% مضمون، 99.9% فعالية)"
    - "محتوى مسيء، تمييزي، أو غير آمن"
  
  required:
    - "شخصيات عامة غير معروفة (إن وُجدت)"
    - "أزياء محلية مناسبة لسياق البحرين (إن وُجدت شخصيات)"
    - "بيئات واقعية وقابلة للتصديق"
    - "استمرارية بصرية (ألوان، إضاءة، أسلوب)"
    - "إفصاح #إعلان في بداية الفيديو (نصاً overlay أو صوتاً خلال أول 3 ثوانٍ)"
    - "احترام RTL للنصوص العربية (إن ظهرت في التصميم)"
  
  generator_specific:
    veo3: ["لا نصوص مباشرة على الشاشة إلا طبيعية", "لا مشاهير"]
    runway: ["دعم نصوص محدود", "تفضيل المشاهد البسيطة"]
    pika: ["ممتاز للمنتجات الثابتة", "حركات بسيطة"]
    sora: ["سيناريوهات معقدة ممكنة", "حوار محدود حالياً"]
    heygen: ["أفاتار جاهز فقط", "لا تخصيص كامل"]
````````````

---

## **قواعد اللغة في السيناريوهات**

- **وصف المشاهد (Scene Description):** يُكتب بالإنجليزية لتتماشى مع متطلبات معظم مولدات الفيديو، مع تضمين تفاصيل الإضاءة، الحركة، الكاميرا، والبيئة.
- **الحوار (Dialogue):** يُنتج باللهجة المطلوبة (بحريني/خليجي/مصري/إنجليزي) مع تحديد النبرة (`voice_characteristics`) لضمان مزامنة الشفاه عند التوليد الصوتي.
- **النصوص على الشاشة (Text Overlay):** تُضاف في المونتاج اللاحق بصيغة عربية RTL واضحة، ≤8 كلمات، مع تباين لوني ≥4.5:1.
- **المؤثرات الصوتية والموسيقى:** إذا كان المولد لا يدعم الصوت، تُذكر توصيات الموسيقى/SFX لإضافتها لاحقًا في التحرير.

---

## **قوس السرد التسويقي (حسب النوع)**

### **🎭 Character-Based (مع شخصيات)**
````````````yaml
story_arc_character:
  1_attention_hook:     "إبراز نقطة الألم أو التحدي (2-3 ثوانٍ)"
  2_conflict_tension:   "تصعيد المشكلة أو العواقب (2-3 ثوانٍ)"
  3_solution_intro:     "تقديم المنتج/الخدمة كحل (3-4 ثوانٍ)"
  4_resolution_cta:     "الطمأنينة والدعوة للإجراء (2-3 ثوانٍ)"
````````````

### **📦 Product-Focused (منتجات فقط)**
````````````yaml
story_arc_product:
  1_product_reveal:     "ظهور المنتج بشكل مثير (2-3 ثوانٍ)"
  2_features_showcase:  "إبراز المميزات الرئيسية (3-4 ثوانٍ)"
  3_benefit_visual:     "تصوير الفائدة بصرياً (2-3 ثوانٍ)"
  4_branding_cta:       "شعار + سعر + دعوة للإجراء (2 ثوانٍ)"
````````````

### **🤖 Virtual Influencer**
````````````yaml
story_arc_influencer:
  1_introduction:       "تحية + تقديم نفس (2-3 ثوانٍ)"
  2_problem_relate:     "ذكر المشكلة بشكل relatable (3-5 ثوانٍ)"
  3_recommendation:     "توصية بالمنتج/الخدمة مع دليل (5-8 ثوانٍ)"
  4_cta_strong:         "دعوة قوية للإجراء (2-3 ثوانٍ)"
````````````

### **🎆 VFX/Cinematic**
````````````yaml
story_arc_vfx:
  1_wow_moment:         "لحظة بصرية مذهلة (3-5 ثوانٍ)"
  2_surreal_journey:    "رحلة بصرية غير واقعية (5-8 ثوانٍ)"
  3_reality_return:     "العودة للواقع + المنتج (3-5 ثوانٍ)"
  4_branding:           "شعار + CTA (2 ثوانٍ)"
````````````

### **📚 Educational**
````````````yaml
story_arc_educational:
  1_question_hook:      "سؤال يثير الاهتمام (2-3 ثوانٍ)"
  2_steps_tips:         "3-5 خطوات/نصائح واضحة (20-40 ثوانٍ)"
  3_recap_benefit:      "ملخص الفائدة (3-5 ثوانٍ)"
  4_brand_cta:          "ربط بالعلامة + CTA (3-5 ثوانٍ)"
````````````

---

## **القوالب — حسب نوع الفيديو**

---

### **📦 Template 1: Product-Focused (منتجات بدون شخصيات)**
````````````markdown
## **Product-Focused Video Template**

**Scenario Type:** Product-Focused  
**Best For:** طعام، إلكترونيات، أزياء، منتجات ملموسة  
**Duration:** 6-15s  
**AI Generators:** Pika, Runway, Sora 2, Veo 3  
**Audio:** Music + SFX (مُولَّدة أو تُضاف لاحقاً)

---

**Scene Structure (4 Scenes):**

#### **Scene 1 – Product Reveal (2-3s)**
```````````json
{
  "scene_number": "S1",
  "title": "Product Reveal",
  "duration": "2s",
  "type": "product_focused",
  
  "product_subject": {
    "item": "Fresh beef burger with steam rising",
    "appearance": "Juicy patty, melted cheese, fresh lettuce, sesame bun",
    "state": "Static on wooden board, slight steam animation",
    "emotional_association": "Appetite, freshness"
  },
  
  "environment": {
    "setting": "Clean wooden table, soft kitchen background (blurred)",
    "surface": "Dark wood cutting board",
    "context": "Restaurant kitchen ambiance",
    "cultural_touches": "None needed (universal food appeal)"
  },
  
  "camera_movement": {
    "angle": "Eye-level, slightly overhead",
    "movement": "Slow dolly-in (2s)",
    "speed": "Slow (luxurious)"
  },
  
  "lighting_color": {
    "lighting_style": "Soft natural light from side window",
    "palette": "Warm golden tones, rich browns",
    "highlights": "On burger top (cheese glisten)",
    "shadows": "Soft shadows on left side"
  },
  
  "visual_effects": {
    "motion": "Steam rising gently",
    "transitions": "Fade in from black",
    "particles": "None"
  },
  
  "sound_audio": {
    "audio_generation_supported": true,
    "sfx_for_generation": {
      "product_sounds": ["burger sizzle", "steam hiss"],
      "environment_sounds": ["quiet kitchen ambience"],
      "volume": "medium"
    },
    "music_for_generation": {
      "auto_generate": true,
      "style": "upbeat acoustic guitar",
      "mood": "appetizing",
      "volume": "background_subtle"
    },
    "voiceover_optional": {
      "required": false
    }
  },
  
  "text_overlay_optional": {
    "display": "None in this scene",
    "note": "تُضاف في المونتاج إن لزم"
  },
  
  "branding": {
    "logo_display": "None yet",
    "color_scheme": "Warm browns, golden yellow"
  },
  
  "negative_prompts": {
    "exclude": "Plastic-looking burger, cartoonish steam, overly glossy/fake"
  },
  
  "technical": {
    "duration": "2s",
    "aspect_ratio": "1:1",
    "resolution": "1080p",
    "fps": "24fps",
    "audio_type": "music_sfx",
    "ai_generator": "Pika"
  }
}
```````````

#### **Scene 2 – Ingredients Close-Up (2s)**
```````````json
{
  "scene_number": "S2",
  "title": "Ingredients Floating",
  "duration": "2s",
  
  "product_subject": {
    "item": "Deconstructed burger layers (bun, patty, cheese, lettuce, tomato)",
    "appearance": "Each ingredient separated vertically in mid-air",
    "state": "Floating, slowly rotating (levitation effect)",
    "emotional_association": "Quality, transparency"
  },
  
  "environment": {
    "setting": "Clean white/light gray background",
    "surface": "None (floating)",
    "context": "Studio-style product showcase"
  },
  
  "camera_movement": {
    "angle": "Eye-level",
    "movement": "Slow 360° orbit around floating ingredients",
    "speed": "Medium"
  },
  
  "lighting_color": {
    "lighting_style": "Bright studio lighting, even",
    "palette": "Vibrant greens (lettuce), red (tomato), golden (bun)",
    "highlights": "On cheese and patty surface",
    "shadows": "None (clean studio look)"
  },
  
  "visual_effects": {
    "motion": "Levitation, slow rotation",
    "transitions": "Cross-dissolve from S1",
    "particles": "Subtle light sparkle on cheese"
  },
  
  "sound_audio": {
    "sfx_for_generation": {
      "product_sounds": ["soft whoosh as ingredients float"],
      "volume": "subtle"
    },
    "music_for_generation": {
      "style": "continues from S1",
      "mood": "curious",
      "sync_with_motion": true
    }
  },
  
  "text_overlay_optional": {
    "display": "١٠٠٪ لحم طازج (center, appears for 1s)",
    "style": "Bold Arabic text, white with shadow",
    "language": "AR (RTL)",
    "timing": "Mid-scene",
    "note": "يُضاف في المونتاج"
  },
  
  "technical": {
    "duration": "2s",
    "aspect_ratio": "1:1",
    "fps": "30fps (smooth motion)",
    "ai_generator": "Pika / Runway"
  }
}
```````````

#### **Scene 3 – Assembly (2s)**
```````````json
{
  "scene_number": "S3",
  "title": "Burger Assembly",
  "duration": "2s",
  
  "product_subject": {
    "item": "Burger being assembled (top bun coming down)",
    "state": "Motion (assembly animation)"
  },
  
  "camera_movement": {
    "angle": "Side view, eye-level",
    "movement": "Static (focus on assembly)"
  },
  
  "visual_effects": {
    "motion": "Top bun slowly lands on burger",
    "particles": "Tiny sesame seeds falling"
  },
  
  "sound_audio": {
    "sfx_for_generation": {
      "product_sounds": ["soft plop as bun lands"],
      "volume": "medium"
    },
    "music_for_generation": {
      "style": "builds to crescendo",
      "mood": "satisfying"
    }
  },
  
  "technical": {
    "duration": "2s",
    "fps": "24fps"
  }
}
```````````

#### **Scene 4 – Branding & CTA (2s)**
```````````json
{
  "scene_number": "S4",
  "title": "Final Hero Shot + Branding",
  "duration": "2s",
  
  "product_subject": {
    "item": "Final burger on board, perfect shot",
    "state": "Static, steam still rising"
  },
  
  "camera_movement": {
    "angle": "Slight overhead",
    "movement": "Very slow zoom-out"
  },
  
  "sound_audio": {
    "music_for_generation": {
      "style": "final uplifting chord"
    },
    "voiceover_optional": {
      "required": true,
      "text": "Burger House — طازج، سريع، لذيذ",
      "language": "Bahraini_Arabic",
      "voice": "male_warm",
      "timing": "throughout S4 (2s)"
    }
  },
  
  "text_overlay": {
    "display": [
      "Burger House (brand name, top)",
      "يبدأ من ١.٥ د.ب (bottom)",
      "#إعلان (small, corner)"
    ],
    "style": "Clean, bold Arabic + English",
    "language": "Bilingual (AR RTL + EN)"
  },
  
  "branding": {
    "logo": "Small logo top-right corner",
    "color_scheme": "Brand colors (gold, brown, white)"
  }
}
```````````

---

### **Post-Generation Notes (Product-Focused):**
```````````yaml
continuity:
  product: "نفس البرجر عبر المشاهد (لون، حجم، تفاصيل)"
  environment: "نفس الطاولة الخشبية في S1, S3, S4"
  lighting: "دافئة طبيعية، متسقة"
  color_grading: "Warm tones throughout"
  text_overlay: "يُضاف في المونتاج (DaVinci Resolve / Premiere Pro)"
  soundtrack: "Upbeat acoustic guitar (60-90 BPM)"
  disclosure: "#إعلان يظهر في S4 (ركن السفلي)"
  export: "1:1 ratio, 1080p, 24fps, MP4 H.264"
```````````

---

### **🎭 Template 2: Character-Based (قصة مع شخصيات)**
```````````markdown
## **Character-Based Video Template**

**Scenario Type:** Character-Based  
**Best For:** بناء ثقة، عاطفي، relatable  
**Duration:** 10-30s  
**AI Generators:** Veo 3.1, Sora 2, Kling Wan 2.5  
**Audio:** Dialogue (مُولَّد) + Music + SFX

---

**Example: "Burger Discovery Story" (12s)**

#### **Scene 1 – The Problem (3s)**
``````````json
{
  "scene_number": "S1",
  "title": "The Problem — Disappointment",
  "duration": "3s",
  "type": "character_based",
  
  "character_subject": {
    "appearance": "Male, 26, casual t-shirt, messy hair, tired expression",
    "emotion": "Disappointment, frustration",
    "body_language": "Shoulders slumped, looking down at burger",
    "eye_contact": "At burger (disgust)"
  },
  
  "environment": {
    "location": "Living room couch, Bahrain apartment",
    "details": "TV playing in background, delivery bag on coffee table",
    "atmosphere": "Dim evening light, casual home setting"
  },
  
  "action_movement": {
    "character_actions": "Opens delivery bag, pulls out flat boring burger, sighs heavily",
    "pacing": "Slow, disappointed",
    "interaction": "With delivery bag and burger"
  },
  
  "camera": {
    "angle": "Close-up on hands and burger, then zoom-out to face",
    "lens": "Medium close-up",
    "movement": "Slow zoom-out"
  },
  
  "lighting_color": {
    "tone": "Dim cool blue-gray",
    "palette": "Muted, lifeless colors",
    "contrast": "Low"
  },
  
  "sound_voice": {
    "audio_generation_supported": true,
    
    "dialogue_for_generation": {
      "language": "Bahraini_Arabic",
      "lines": "شنو هالبرجر الممل هذا؟",
      "voice_characteristics": {
        "gender": "male",
        "age": "young_adult",
        "tone": "frustrated",
        "accent": "Bahraini",
        "emotion": "disappointed_annoyed",
        "pace": "medium"
      },
      "pronunciation_notes": "نطق 'شنو' بلهجة بحرينية واضحة، تشديد على 'ممل'",
      "lip_sync_priority": "high"
    },
    
    "sfx_for_generation": {
      "auto_generate": true,
      "specific_sounds": ["delivery bag crinkling", "disappointed sigh"],
      "environment_ambience": "quiet home",
      "volume_balance": "dialogue_primary"
    },
    
    "music_for_generation": {
      "auto_generate": true,
      "style": "tense minor key",
      "mood": "disappointed",
      "volume": "background_subtle"
    }
  },
  
  "props": {
    "items": "Generic delivery bag, flat boring burger, phone on table"
  },
  
  "negative_prompts": {
    "exclude": "Cartoonish, fake burger, plastic furniture"
  },
  
  "technical": {
    "duration": "3s",
    "aspect_ratio": "9:16",
    "resolution": "1080p",
    "fps": "24fps",
    "audio_type": "dialogue_generated + music_sfx_generated",
    "ai_generator": "Veo 3.1"
  }
}
``````````

#### **Scene 2 – Discovery (3s)**
``````````json
{
  "scene_number": "S2",
  "title": "The Discovery — Hope",
  "duration": "3s",
  
  "character": "Same, now picking up phone with curious expression",
  "emotion": "Curiosity, hope",
  "action": "Scrolling on phone, eyes widen, taps screen",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "يالله نجرب Burger House...",
    "voice_characteristics": {
      "tone": "curious_hopeful",
      "emotion": "interest_building"
    }
  },
  
  "sfx": ["phone tap", "notification chime"],
  "music": "curious ascending notes"
}
``````````

#### **Scene 3 – Solution (4s)**
``````````json
{
  "scene_number": "S3",
  "title": "The Solution — Delight",
  "duration": "4s",
  
  "character": "Excited, opening fresh Burger House bag",
  "action": "Opens bag, lifts burger (steam), takes big bite, closes eyes in satisfaction",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "وااااو! هذا برجر حقيقي!",
    "voice_characteristics": {
      "tone": "joyful_excited",
      "emotion": "delight_satisfaction",
      "pace": "fast (excited)"
    },
    "pronunciation_notes": "تطويل 'وااااو' لإظهار الإعجاب"
  },
  
  "sfx": ["bag opening", "satisfying crunch bite", "burger sizzle"],
  "music": "uplifting major key"
}
``````````

#### **Scene 4 – CTA (2s)**
``````````json
{
  "scene_number": "S4",
  "title": "Call to Action",
  "duration": "2s",
  
  "character": "Satisfied, thumbs up to camera",
  "action": "Wipes mouth, thumbs up, nods",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "اطلب الحين — توصيل ٢٥ دقيقة!",
    "voice_characteristics": {
      "tone": "enthusiastic_recommending"
    }
  },
  
  "voiceover_disclosure": {
    "text": "#إعلان",
    "timing": "first_1_second",
    "volume": "clear_audible"
  }
}
``````````

---

### **🤖 Template 3: Virtual Influencer (أفاتار رقمي)**
``````````markdown
## **Virtual Influencer Video Template**

**Scenario Type:** Virtual Influencer (AI Avatar)  
**Best For:** مصداقية، توصية شخصية، محتوى متكرر  
**Duration:** 15-30s  
**AI Generators:** HeyGen, D-ID, Synthesia, Veo 3.1  
**Audio:** Dialogue (مُولَّد مباشرة) + Music

---

**Single Scene Structure (20s):**
`````````json
{
  "scenario_type": "virtual_influencer",
  "duration": "20s",
  
  "avatar_character": {
    "appearance": "أنثى، 28 سنة، شعر طويل داكن، عباية كاجوال معاصرة، مكياج بسيط",
    "personality": "ودية، واثقة، relatable",
    "name": "نورة — عشاق البرجر 🍔",
    "setting": "خلفية بسيطة (gradient ناعم أو مكتب منزلي)",
    "cultural_fit": "ملابس محتشمة، سياق بحريني"
  },
  
  "script_dialogue": {
    "language": "Bahraini_Arabic",
    "full_script": [
      "[0-5s] السلام عليكم! أنا نورة، وصراحة كنت أدور على برجر صج لذيذ...",
      "[5-12s] جربت Burger House وشنو أقولكم؟ اللحم طازج، الصوص خيالي، والتوصيل سريع.",
      "[12-17s] صار المطعم المفضل حقي، وأنصحكم تجربونه.",
      "[17-20s] اطلبوا الحين من الرابط — ما راح تندمون! 🍔"
    ],
    "voice_characteristics": {
      "gender": "female",
      "age": "young_adult",
      "tone": "friendly_confident",
      "accent": "Bahraini",
      "emotion": "enthusiastic",
      "pace": "medium"
    }
  },
  
  "camera": {
    "angle": "eye-level (direct to camera)",
    "framing": "medium close-up (shoulders and face)",
    "movement": "static (professional)"
  },
  
  "lighting": {
    "style": "soft studio lighting",
    "palette": "warm, inviting"
  },
  
  "visual_elements": {
    "lower_third": "نورة — عشاق البرجر 🍔 (يظهر 0-3s)",
    "product_overlay": "صورة برجر صغيرة (10-12s)",
    "cta_text": "اطلب الآن ↗️ (18-20s)",
    "disclosure": "#إعلان (corner, 0-20s)"
  },
  
  "compliance": {
    "disclosure": "#إعلان (نص + صوت في البداية)",
    "avatar_consistency": "نفس الشخصية (نورة) عبر جميع الفيديوهات",
    "cultural_fit": "✅"
  },
  
  "technical": {
    "duration": "20s",
    "aspect_ratio": "9:16",
    "resolution": "1080p",
    "fps": "30fps",
    "audio_type": "dialogue_generated",
    "ai_generator": "HeyGen"
  }
}
`````````

**Post-Generation Notes:**
- استخدم نفس الأفاتار (نورة) في جميع الفيديوهات للاتساق
- يمكن تغيير الخلفية حسب المنتج
- النص يُكتب في HeyGen/D-ID مباشرة
- الصوت يُولَّد تلقائياً بلهجة بحرينية

---

### **🎆 Template 4: VFX/Cinematic (خدع بصرية)**
`````````markdown
## **VFX Cinematic Video Template**

**Scenario Type:** VFX/Cinematic Surreal  
**Best For:** جذب انتباه، viral potential، منتجات فريدة  
**Duration:** 10-20s  
**AI Generators:** Runway Gen-3, Pika, Sora 2  
**Audio:** Music (دراما) + SFX قوية

---

**Example: "Burger Explosion & Reassembly" (15s)**

#### **Scene 1 — Explosion (0-5s)**
````````json
{
  "scene_number": "S1",
  "title": "Burger Explosion",
  "duration": "5s",
  
  "product": "Burger on dark table",
  "action": "Burger explodes outward in slow-motion",
  
  "elements_flying": [
    "Bun top (upward)",
    "Patty (center burst)",
    "Lettuce leaves (spinning)",
    "Cheese (melting mid-air)",
    "Tomato slices (radial)"
  ],
  
  "camera": {
    "movement": "Slow-motion (120fps feel), zoom-out",
    "angle": "Eye-level"
  },
  
  "lighting": {
    "style": "Dark background, spotlight on burger",
    "palette": "Dark + golden highlights",
    "vfx_lighting": "Particles glowing"
  },
  
  "visual_effects": {
    "motion": "Explosion radial outward",
    "particles": "Light rays, fire sparks, energy waves",
    "speed": "Slow-motion (0.3x speed)"
  },
  
  "sound_audio": {
    "sfx": "Explosion whoosh, dramatic bass drop",
    "music": "Epic orchestral hit"
  },
  
  "technical": {
    "duration": "5s",
    "fps": "60fps (for slow-mo effect)",
    "ai_generator": "Runway Gen-3"
  }
}
````````

#### **Scene 2 — Floating (5-10s)**
````````json
{
  "scene_number": "S2",
  "title": "Floating Ingredients",
  "duration": "5s",
  
  "action": "Ingredients float and rotate in mid-air",
  
  "camera": {
    "movement": "360° orbit around floating pieces"
  },
  
  "lighting": {
    "style": "Golden spotlight on each ingredient"
  },
  
  "visual_effects": {
    "motion": "Levitation, slow rotation",
    "particles": "Glowing particles, light streaks, magic shimmer"
  },
  
  "sound_audio": {
    "sfx": "Magical shimmer sound, ethereal whoosh",
    "music": "Suspenseful strings"
  }
}
````````

#### **Scene 3 — Reassembly (10-15s)**
````````json
{
  "scene_number": "S3",
  "title": "Magnetic Reassembly",
  "duration": "5s",
  
  "action": "Ingredients fly back together in reverse (magnetic pull)",
  "timing": "Fast (2x speed)",
  
  "camera": {
    "movement": "Zoom-in as burger reforms"
  },
  
  "lighting": {
    "style": "Bright flash as burger completes"
  },
  
  "visual_effects": {
    "motion": "Reverse explosion, magnetic snap",
    "particles": "Energy waves converging, final burst of light"
  },
  
  "sound_audio": {
    "sfx": "Magnetic 'snap' sound, satisfying click, final 'boom'",
    "music": "Triumphant chord"
  }
}
````````

#### **Scene 4 — Hero Shot (15-18s)**
````````json
{
  "scene_number": "S4",
  "title": "Final Product",
  "duration": "3s",
  
  "product": "Perfect burger, steam rising",
  "camera": "Slow push-in, static hero shot",
  "lighting": "Warm golden glow",
  
  "text_overlay": {
    "display": "Burger House — طازج كل يوم",
    "timing": "Throughout (3s)"
  },
  
  "branding": {
    "logo": "Center",
    "cta": "اطلب الآن",
    "disclosure": "#إعلان"
  },
  
  "sound_audio": {
    "sfx": "Sizzle sound",
    "music": "Final note fade"
  }
}
````````

**تحذير:** لا تبالغ في التأثيرات حتى لا يفقد المنتج مصداقيته. استخدم بحذر مع منتجات B2B.

---

### **📚 Template 5: Educational (تعليمي)**
````````markdown
## **Educational Video Template**

**Scenario Type:** Educational/How-To  
**Best For:** بناء سلطة، engagement عالي، قيمة مجانية  
**Duration:** 30-60s  
**AI Generators:** أي مولد + نصوص في المونتاج  
**Audio:** Voiceover تعليمي + موسيقى هادئة

---

**Example: "3 علامات البرجر الطازج" (40s)**

#### **Intro (0-5s)**
```````json
{
  "scene": "Opening",
  "visual": "سؤال على شاشة + برجر غير واضح",
  "text_overlay": "هل تعرف كيف تختار برجر طازج؟",
  "voiceover": "كثير ناس ما يعرفون الفرق...",
  "music": "هادئة، فضولية"
}
```````

#### **Step 1 (5-15s)**
```````json
{
  "scene": "Step 1",
  "title_overlay": "١. اللحم يجب أن يكون بنياً (ليس رمادياً)",
  "visual": "مقارنة لحم طازج vs قديم (split screen)",
  "voiceover": {
    "language": "Bahraini_Arabic",
    "text": "اللحم الطازج لونه بني غامق، مو رمادي..."
  },
  "camera": "Close-up على اللحم",
  "duration": "10s"
}
```````

#### **Step 2 (15-25s)**
```````json
{
  "scene": "Step 2",
  "title_overlay": "٢. الخبز محمص (ليس طرياً جداً)",
  "visual": "خبز محمص vs طري (side by side)",
  "voiceover": "الخبز الطازج يكون محمص من برا، طري من داخل..."
}
```````

#### **Step 3 (25-35s)**
```````json
{
  "scene": "Step 3",
  "title_overlay": "٣. رائحة واضحة (ليست معدومة)",
  "visual": "شخص (أو يد) يشم البرجر ويبتسم",
  "voiceover": "البرجر الطازج له رائحة قوية..."
}
```````

#### **CTA (35-40s)**
```````json
{
  "scene": "Branding & CTA",
  "text_overlay": "في Burger House — كل برجر طازج كل يوم ✅",
  "visual": "برجر كامل جميل + logo",
  "voiceover": "جرّب الفرق الحقيقي الآن",
  "cta": "اطلب عبر الرابط",
  "disclosure": "#إعلان"
}
```````

**Notes:**
- النصوص على الشاشة كبيرة وواضحة (RTL)
- الخطوات مرقّمة ومرئية
- الصوت هادئ تعليمي (ليس مبالغ)

---

### **📢 Template 6: Awareness/PSA (توعوي)**
```````markdown
## **Awareness/PSA Video Template**

**Scenario Type:** Awareness (Public Service)  
**Best For:** brand values، مسؤولية اجتماعية، بناء صورة  
**Duration:** 20-30s  
**Audio:** موسيقى ملهمة + voiceover قوي

---

**Example: "النظافة مسؤولية الجميع" (شركة تنظيف — 25s)**

#### **Scene 1 (0-8s)**
``````json
{
  "scene": "Community",
  "visual": "أطفال يلعبون في حديقة نظيفة، عائلات تمشي",
  "text_overlay": "نظافة مجتمعنا تبدأ من بيوتنا",
  "voiceover": {
    "language": "Bahraini_Arabic",
    "text": "كل بيت نظيف يعني مجتمع صحي وآمن...",
    "tone": "ملهم، هادئ"
  },
  "music": "ملهمة، بطيئة",
  "camera": "Wide shots، cinematic"
}
``````

#### **Scene 2 (8-16s)**
``````json
{
  "scene": "Solution",
  "visual": "Transition إلى بيت نظيف منظم، أم سعيدة",
  "text_overlay": "سكوب لاين — نساعدك تحافظ على بيتك",
  "voiceover": "نحن هنا لنخفف عنك... ونوفّر وقتك لأهم الأشياء",
  "music": "تتصاعد"
}
``````

#### **Scene 3 (16-25s)**
``````json
{
  "scene": "Call to Action",
  "visual": "عائلة سعيدة في بيت نظيف، شعار الشركة",
  "text_overlay": "لأن النظافة حق للجميع",
  "voiceover": "احجز خدمتنا اليوم — لبيت أنظف وحياة أسهل",
  "cta": "احجز الآن",
  "disclosure": "#إعلان",
  "music": "نهاية ملهمة"
}
``````

**Notes:**
- النبرة ملهمة وليست تجارية مباشرة
- الربط بين القيمة الاجتماعية والخدمة طبيعي
- يُستخدم في مناسبات خاصة (اليوم الوطني، حملات مجتمعية)

---

### **📱 Template 7: UGC Style (محتوى مستخدم)**
``````markdown
## **UGC Style Video Template**

**Scenario Type:** UGC (User-Generated Content Style)  
**Best For:** مصداقية، relatable، تكلفة منخفضة  
**Duration:** 10-20s  
**AI Generators:** Veo 3.1, Kling Wan 2.5  
**Audio:** حوار طبيعي + أصوات بيئة

---

**Example: "Unboxing Reaction" (15s)**
`````json
{
  "scenario_type": "ugc_style",
  "duration": "15s",
  
  "style_guidelines": {
    "camera": "Handheld vertical (9:16), شخص يمسك الهاتف",
    "quality": "غير مصقول، واقعي (ليس احترافي جداً)",
    "lighting": "طبيعية (إضاءة غرفة/نافذة)",
    "framing": "غير مثالي (authentic)"
  },
  
  "character": {
    "appearance": "شاب عادي، ملابس كاجوال",
    "personality": "متحمس، صادق، relatable"
  },
  
  "script_flow": [
    {
      "timing": "0-3s",
      "action": "يمسك كيس التوصيل، يبتسم للكاميرا",
      "dialogue": "شوفوا شنو وصلني اليوم!",
      "emotion": "فضول، تشويق"
    },
    {
      "timing": "3-8s",
      "action": "يفتح الكيس، يُخرج البرجر، عيونه تتسع",
      "dialogue": "واااو! شوفوا هالحجم! ريحته خيالية...",
      "emotion": "مفاجأة سعيدة"
    },
    {
      "timing": "8-12s",
      "action": "يقضم، يمضغ، يغلق عينيه بارتياح",
      "dialogue": "مممم... صدق طعمه مو طبيعي! اللحم طري والصوص...",
      "emotion": "استمتاع"
    },
    {
      "timing": "12-15s",
      "action": "ينظر للكاميرا مباشرة، thumbs up",
      "dialogue": "جربوه — رابط في البايو! #إعلان",
      "emotion": "توصية صادقة"
    }
  ],
  
  "audio": {
    "dialogue_language": "Bahraini_Arabic (غير رسمي، كلام شارع)",
    "voice_tone": "حماسي، طبيعي، غير مكتوب",
    "background": "أصوات بيئة (TV بعيد، هاتف يرن)"
  },
  
  "visual_effects": {
    "none": "بدون تأثيرات (raw)"
  },
  
  "compliance": {
    "disclosure": "#إعلان في الحوار + نص overlay (15s)"
  },
  
  "technical": {
    "aspect_ratio": "9:16",
    "resolution": "1080p (أو 720p لواقعية أكثر)",
    "fps": "30fps",
    "ai_generator": "Veo 3.1"
  }
}
`````

**Key Tips:**
- لا تُصقّل كثيراً — الأصالة مهمة
- الحوار عفوي (ليس سكربت محفوظ)
- أخطاء صغيرة مقبولة (توقف، ضحكة)
- الكاميرا تهتز قليلاً (handheld)

---

### **🎞️ Template 8: Documentary Style (وثائقي)**
`````markdown
## **Documentary Video Template**

**Scenario Type:** Documentary/Behind-the-Scenes  
**Best For:** بناء ثقة، شفافية، علامة تجارية  
**Duration:** 30-60s  
**Production:** تصوير حقيقي (أو AI بأسلوب realistic)  
**Audio:** Voiceover + أصوات طبيعية

---

**Example: "كيف نحضّر البرجر" (45s)**

#### **Opening (0-5s)**
````json
{
  "scene": "Introduction",
  "visual": "باب المطبخ يُفتح، كاميرا تدخل",
  "text_overlay": "خلف الكواليس — Burger House",
  "voiceover": "تعالوا نشوف كيف نحضّر برجركم...",
  "style": "Documentary handheld camera"
}
````

#### **Process Scenes (5-35s)**
````json
{
  "scenes": [
    {
      "timing": "5-15s",
      "visual": "طاهٍ يختار اللحم الطازج من الثلاجة",
      "voiceover": "كل صباح، نستلم لحم طازج ١٠٠٪...",
      "camera": "Following chef, natural movements"
    },
    {
      "timing": "15-25s",
      "visual": "تشكيل الفطائر يدوياً، شوي على النار",
      "voiceover": "نشكّل كل فطيرة يدوياً، نشويها على درجة حرارة مضبوطة...",
      "sfx": "Sizzle sounds, kitchen ambience"
    },
    {
      "timing": "25-35s",
      "visual": "تجميع البرجر، إضافة الخضار الطازجة",
      "voiceover": "نضيف خضار محلية طازجة، وصوصاتنا الخاصة...",
      "camera": "Close-ups on fresh ingredients"
    }
  ]
}
````

#### **Closing (35-45s)**
````json
{
  "scene": "Final Message",
  "visual": "برجر جاهز يُعطى للعميل، ابتسامة",
  "text_overlay": "طازج. صادق. لذيذ.",
  "voiceover": "هذا التزامنا لكم — جرّبوا الفرق",
  "cta": "اطلب الآن",
  "disclosure": "#إعلان"
}
````

**Notes:**
- أسلوب واقعي (ليس مصطنع)
- إضاءة طبيعية قدر الإمكان
- موسيقى هادئة في الخلفية
- يبني ثقة طويلة المدى

---

### **🔀 Template 9: Mixed Carousel (صور + فيديو)**
````markdown
## **Mixed Carousel Template**

**Scenario Type:** Hybrid (Images + Video)  
**Best For:** تنويع، جذب انتباه، قصة بصرية  
**Platform:** Instagram/Facebook  
**Total Slides:** 5 (3 صور + 1 فيديو + 1 صورة نهائية)

---

**Structure:**
```json
{
  "carousel_structure": [
    {
      "slide": 1,
      "type": "image",
      "content": "Hook — مشكلة أو سؤال",
      "visual": "صورة برجر ممل/رمادي",
      "text_overlay": "تعبت من البرجر الممل؟",
      "ratio": "1:1"
    },
    {
      "slide": 2,
      "type": "image",
      "content": "Agitation — تصعيد المشكلة",
      "visual": "شخص محبط ينظر لبرجر سيء",
      "text_overlay": "كل مرة نفس الخيبة...",
      "ratio": "1:1"
    },
    {
      "slide": 3,
      "type": "video",
      "content": "Solution — فيديو برجر طازج (8s)",
      "visual": "فيديو برجر يدور 360° مع steam",
      "audio": "موسيقى + sizzle SFX",
      "text_overlay": "جرّب Burger House — طازج كل يوم",
      "duration": "8s",
      "ratio": "1:1"
    },
    {
      "slide": 4,
      "type": "image",
      "content": "Proof — إثبات اجتماعي",
      "visual": "تقييمات 5 نجوم + عدد عملاء",
      "text_overlay": "٤.٨/٥ — أكثر من ١٠٠٠ عميل راضٍ",
      "ratio": "1:1"
    },
    {
      "slide": 5,
      "type": "image",
      "content": "CTA — دعوة للإجراء",
      "visual": "برجر + سعر + logo",
      "text_overlay": "اطلب الآن — يبدأ من ١.٥ د.ب | #إعلان",
      "cta_button": "اطلب الآن",
      "ratio": "1:1"
    }
  ],
  
  "caption": "من البرجر الممل 😞 إلى الطازج اللذيذ 🍔! اسحب لتشوف الفرق... #برجر_البحرين #إعلان",
  
  "hashtags": ["#برجر_هاوس", "#طعام_طازج", "#البحرين", "#إعلان"]
}
```

**Notes:**
- الفيديو في المنتصف (slide 3) لجذب الانتباه
- الصور قبل وبعد تبني القصة
- النسبة 1:1 موحّدة عبر الكاروسيل
- CTA واضح في النهاية

---

## **توطين البحرين (مدمج تلقائيًا)**
```yaml
bahrain_localization:
  
  character_based:
    attire: "ملابس كاجوال معاصرة، دشداشة (رسمي)، عباية محتشمة (نساء)"
    settings: "بيوت حديثة، مكاتب، مقاهي محلية، شوارع المنامة"
    cultural_notes:
      - "تجنب لقطات حميمية غير مناسبة"
      - "احترام الخصوصية"
      - "مواسم: رمضان (فوانيس)، العيد، اليوم الوطني (16-17 ديسمبر)"
  
  product_focused:
    color_palette: "دافئ (ذهبي، بيج، أخضر داكن) للعلامات المحلية"
    props: "أطباق عربية، أكواب قهوة عربية، ديكورات محلية"
    text_overlay: "RTL للعربية، خطوط Cairo/Tajawal"
  
  virtual_influencer:
    avatar_design: "ملامح خليجية، ملابس محتشمة معاصرة"
    language: "لهجة بحرينية/خليجية طبيعية"
    context: "إشارات محلية (أماكن، عادات، مواسم)"
  
  language_rule:
    scenario_text: "إنجليزي دائماً (الوصف البصري، التقني، التعليمات)"
    dialogue_voiceover: "لهجة المستخدم المختارة (بحريني، خليجي، مصري، إنجليزي، أو بدون)"
    text_overlay: "عربي RTL عند الحاجة"
```

---

## **خوارزمية التوليد التلقائي (محدّثة)**
```python
def generate_video_scenario(input):
    # 1. تحديد نوع السيناريو
    scenario_types = {
        "character_based": scene_template_character,
        "product_focused": scene_template_product,
        "virtual_influencer": scene_template_influencer,
        "vfx_cinematic": scene_template_vfx,
        "documentary": scene_template_documentary,
        "educational": scene_template_educational,
        "awareness_psa": scene_template_psa,
        "ugc_style": scene_template_ugc,
        "mixed_carousel": scene_template_carousel
    }
    
    template = scenario_types[input.scenario_type]
    
    # 2. اختيار المولد المناسب
    if input.scenario_type == "virtual_influencer":
        recommended_generator = "HeyGen"
    elif input.scenario_type == "vfx_cinematic":
        recommended_generator = "Runway_Gen3"
    elif input.audio_type == "dialogue_generated":
        recommended_generator = "Veo_3.1"
    else:
        recommended_generator = input.ai_generator or "Veo_3.1"
    
    # 3. Information Check
    if missing_critical_info(input):
        ask_user_clarification()
        if partial_answers():
            assume_reasonable_defaults()
    
    # 4. Scene Breakdown
    scenes = []
    for i in range(1, input.scenes_max + 1):
        scene = create_scene(
            template=template,
            number=i,
            duration=calculate_duration(input.total_seconds, i),
            product_or_character=input.type,
            environment=localize_bahrain(input.location),
            dialogue=input.dialogue.language if needs_dialogue(input.scenario_type) else None,
            audio_type=input.audio_type,
            generator=recommended_generator
        )
        scenes.append(scene)
    
    # 5. Compliance Check
    for scene in scenes:
        validate_universal_rules(scene)
        sanitize_prohibited_content(scene)
        add_disclosure_if_paid(scene)
    
    # 6. Output Packaging
    return {
        "scenario_type": input.scenario_type,
        "full_scenario": scenes,
        "dialogue_script": extract_dialogue(scenes) if input.dialogue.required else None,
        "technical_prompts": generate_ai_prompts(scenes, recommended_generator),
        "continuity_notes": build_continuity_guide(scenes),
        "post_production_notes": audio_text_overlay_instructions(scenes)
    }
```

---

## **أمثلة طلبات وكيفية معالجتها**

| الطلب المختصر | القرار | المولد المقترح | ملاحظات إضافية |
|---------------|--------|----------------|-----------------|
| "فيديو 12 ثانية للبرجر مع قصة عميل" | Character-Based مع حوار بحريني | **Veo 3.1** | 4 مشاهد مع إفصاح صوتي في المشهد الأخير |
| "مشاهد برجر فقط 8 ثوانٍ بدون أشخاص" | Product-Focused بصري بالكامل | **Sora 2** أو **Runway Gen-3** | أضف SFX طبخ في المونتاج |
| "فيديو إنفلونسر افتراضي يوصي بالبرجر" | Virtual Influencer | **HeyGen** | إعداد نص عربي بلهجة بحرينية، CTA واضح |
| "فيديو خدع بصرية للبرجر" | VFX/Cinematic | **Runway Gen-3** | دمج حركة كاميرا سريعة + كشف المنتج في النهاية |
| "فيديو تعليمي: كيف تختار برجر طازج" | Educational | **Veo 3.1** مع Voiceover | استخدم بنية خطوات وتوصيات سلامة غذائية |

---

## **قائمة تحقق امتثال سيناريو الفيديو**

- ✅ لا مشاهير معروفين أو رموز محمية ما لم يوجد تصريح.
- ✅ إفصاح **#إعلان** في أول 3 ثوانٍ (نص وصوت حسب الإمكان).
- ✅ تجنب الوعود المطلقة؛ استخدم نطاقات أو أدلة مرجعية في الحوار.
- ✅ احترام الثقافة المحلية: ملابس محتشمة، سياقات ملائمة، عدم استغلال ديني/وطني.
- ✅ توثيق أي عناصر مضافة في المونتاج (نصوص، موسيقى، ترجمة) ضمن `post_production_notes`.

---

## **التكامل مع الوحدات السابقة**
```yaml
integration:
  from_09_content_planning:
    - "استخدام content_type لتحديد scenario_type تلقائياً"
    - "استخدام weekly/monthly plan لتوزيع أنواع الفيديو"
  
  from_04_adaptation:
    - "استخدام copy.hook كعنوان المشهد الأول"
    - "استخدام copy.story_bab كقوس سردي"
    - "استخدام design_notes كمرجع بصري"
  
  from_02_persuasion:
    - "استخدام emotional_triggers لتحديد نبرة المشاهد"
    - "استخدام cta لصياغة المشهد الأخير"
  
  from_01_market_intel:
    - "استخدام personas لتصميم الشخصيات"
    - "استخدام pains لصياغة مشاهد المشكلة"
    - "استخدام features/benefits لإبراز المنتج"
```

---

## **جدول مقارنة المولدات — Audio Capabilities**

| المولد | صوت | حوار | SFX | موسيقى | مزامنة شفاه | عربي | الأفضل لـ |
|--------|-----|------|-----|--------|------------|------|-----------|
| **Kling Wan 2.5** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | UGC style |
| **Sora 2** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد جداً | سيناريوهات طويلة |
| **Veo 3** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | احترافي |
| **Veo 3.1** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز جداً | ✅ ممتاز | **الأفضل للعربي** |
| **Runway Gen-3** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | VFX/سريع |
| **Pika Labs** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | منتجات ثابتة |
| **Luma Dream** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | مشاهد بسيطة |
| **HeyGen** | ✅ | ✅ | ❌ | ❌ | ✅ ممتاز | ✅ جيد جداً | **Virtual Influencer** |
| **D-ID** | ✅ | ✅ | ❌ | ❌ | ✅ جيد | ✅ جيد | Avatar سريع |
| **Synthesia** | ✅ | ✅ | ❌ | ❌ | ✅ ممتاز | ✅ ممتاز | Corporate |

---

## **مخرجات الوحدة (JSON)**
```json
{
  "video_scenario": {
    "scenario_type": "character_based | product_focused | virtual_influencer | vfx_cinematic | documentary | educational | awareness_psa | ugc_style | mixed_carousel",
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
        "character": { "appearance": "...", "emotion": "frustration" },
        "sound_voice": {
          "audio_generation_supported": true,
          "dialogue_for_generation": {
            "language": "Bahraini_Arabic",
            "lines": "شنو هالبرجر الممل هذا؟",
            "voice_characteristics": {...}
          },
          "sfx_for_generation": {...},
          "music_for_generation": {...}
        }
      }
    ],
    
    "audio_generation_notes": {
      "generator": "Veo 3.1",
      "dialogue_quality": "ممتاز للهجة البحرينية",
      "lip_sync": "تلقائي",
      "post_production": "اختياري — فقط إذا احتاج تحسين"
    },
    
    "continuity_notes": {
      "character": "نفس الملابس عبر المشاهد",
      "environment": "تحسن الإضاءة تدريجياً",
      "props": "إزالة الكيس القديم قبل S3"
    },
    
    "post_production_notes": {
      "text_overlay": "يُضاف في المونتاج (DaVinci Resolve)",
      "music": "يمكن استبدال الموسيقى المُولَّدة",
      "disclosure": "#إعلان في S4 (صوت + نص)"
    },
    
    "compliance": "✅",
    "ready_for_generation": true
  }
}
```

---

## **ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **ما تمّ توليده:** سيناريو [scenario_type] ([duration]s، [scenes] مشاهد) لـ [channel]، [audio_type].
* **الامتثال:** ✅ [generator] | ✅ إفصاح #إعلان | ✅ RTL/BHD | ✅ ثقافة بحرينية.
* **الخطوة التالية:** رفع السيناريو لـ [ai_generator] + [post_production_steps].

---

**انتهى ملف 08_video_scenarios.md**
````

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::EXAMPLES -->

## أمثلة عملية (لا تحذف القديمة — ألصقها هنا)

## **سياسة الامتثال والسلامة (عامة لجميع المولدات)**
````````````yaml
compliance_universal:
  forbidden:
    - "مشاهير أو شخصيات عامة معروفة (إن وُجدت شخصيات)"
    - "نصوص على الشاشة مبالغ فيها (إلا إذا كانت جزءاً طبيعياً من التصميم)"
    - "علامات تجارية منافسة أو شعارات غير مصرح بها"
    - "ادعاءات مبالغ فيها (100% مضمون، 99.9% فعالية)"
    - "محتوى مسيء، تمييزي، أو غير آمن"
  
  required:
    - "شخصيات عامة غير معروفة (إن وُجدت)"
    - "أزياء محلية مناسبة لسياق البحرين (إن وُجدت شخصيات)"
    - "بيئات واقعية وقابلة للتصديق"
    - "استمرارية بصرية (ألوان، إضاءة، أسلوب)"
    - "إفصاح #إعلان في بداية الفيديو (نصاً overlay أو صوتاً خلال أول 3 ثوانٍ)"
    - "احترام RTL للنصوص العربية (إن ظهرت في التصميم)"
  
  generator_specific:
    veo3: ["لا نصوص مباشرة على الشاشة إلا طبيعية", "لا مشاهير"]
    runway: ["دعم نصوص محدود", "تفضيل المشاهد البسيطة"]
    pika: ["ممتاز للمنتجات الثابتة", "حركات بسيطة"]
    sora: ["سيناريوهات معقدة ممكنة", "حوار محدود حالياً"]
    heygen: ["أفاتار جاهز فقط", "لا تخصيص كامل"]
````````````

---

## **قواعد اللغة في السيناريوهات**

- **وصف المشاهد (Scene Description):** يُكتب بالإنجليزية لتتماشى مع متطلبات معظم مولدات الفيديو، مع تضمين تفاصيل الإضاءة، الحركة، الكاميرا، والبيئة.
- **الحوار (Dialogue):** يُنتج باللهجة المطلوبة (بحريني/خليجي/مصري/إنجليزي) مع تحديد النبرة (`voice_characteristics`) لضمان مزامنة الشفاه عند التوليد الصوتي.
- **النصوص على الشاشة (Text Overlay):** تُضاف في المونتاج اللاحق بصيغة عربية RTL واضحة، ≤8 كلمات، مع تباين لوني ≥4.5:1.
- **المؤثرات الصوتية والموسيقى:** إذا كان المولد لا يدعم الصوت، تُذكر توصيات الموسيقى/SFX لإضافتها لاحقًا في التحرير.

---

## **قوس السرد التسويقي (حسب النوع)**

### **🎭 Character-Based (مع شخصيات)**
````````````yaml
story_arc_character:
  1_attention_hook:     "إبراز نقطة الألم أو التحدي (2-3 ثوانٍ)"
  2_conflict_tension:   "تصعيد المشكلة أو العواقب (2-3 ثوانٍ)"
  3_solution_intro:     "تقديم المنتج/الخدمة كحل (3-4 ثوانٍ)"
  4_resolution_cta:     "الطمأنينة والدعوة للإجراء (2-3 ثوانٍ)"
````````````

### **📦 Product-Focused (منتجات فقط)**
````````````yaml
story_arc_product:
  1_product_reveal:     "ظهور المنتج بشكل مثير (2-3 ثوانٍ)"
  2_features_showcase:  "إبراز المميزات الرئيسية (3-4 ثوانٍ)"
  3_benefit_visual:     "تصوير الفائدة بصرياً (2-3 ثوانٍ)"
  4_branding_cta:       "شعار + سعر + دعوة للإجراء (2 ثوانٍ)"
````````````

### **🤖 Virtual Influencer**
````````````yaml
story_arc_influencer:
  1_introduction:       "تحية + تقديم نفس (2-3 ثوانٍ)"
  2_problem_relate:     "ذكر المشكلة بشكل relatable (3-5 ثوانٍ)"
  3_recommendation:     "توصية بالمنتج/الخدمة مع دليل (5-8 ثوانٍ)"
  4_cta_strong:         "دعوة قوية للإجراء (2-3 ثوانٍ)"
````````````

### **🎆 VFX/Cinematic**
````````````yaml
story_arc_vfx:
  1_wow_moment:         "لحظة بصرية مذهلة (3-5 ثوانٍ)"
  2_surreal_journey:    "رحلة بصرية غير واقعية (5-8 ثوانٍ)"
  3_reality_return:     "العودة للواقع + المنتج (3-5 ثوانٍ)"
  4_branding:           "شعار + CTA (2 ثوانٍ)"
````````````

### **📚 Educational**
````````````yaml
story_arc_educational:
  1_question_hook:      "سؤال يثير الاهتمام (2-3 ثوانٍ)"
  2_steps_tips:         "3-5 خطوات/نصائح واضحة (20-40 ثوانٍ)"
  3_recap_benefit:      "ملخص الفائدة (3-5 ثوانٍ)"
  4_brand_cta:          "ربط بالعلامة + CTA (3-5 ثوانٍ)"
````````````

---

## **القوالب — حسب نوع الفيديو**

---

### **📦 Template 1: Product-Focused (منتجات بدون شخصيات)**
````````````markdown
## **Product-Focused Video Template**

**Scenario Type:** Product-Focused  
**Best For:** طعام، إلكترونيات، أزياء، منتجات ملموسة  
**Duration:** 6-15s  
**AI Generators:** Pika, Runway, Sora 2, Veo 3  
**Audio:** Music + SFX (مُولَّدة أو تُضاف لاحقاً)

---

**Scene Structure (4 Scenes):**

#### **Scene 1 – Product Reveal (2-3s)**
```````````json
{
  "scene_number": "S1",
  "title": "Product Reveal",
  "duration": "2s",
  "type": "product_focused",
  
  "product_subject": {
    "item": "Fresh beef burger with steam rising",
    "appearance": "Juicy patty, melted cheese, fresh lettuce, sesame bun",
    "state": "Static on wooden board, slight steam animation",
    "emotional_association": "Appetite, freshness"
  },
  
  "environment": {
    "setting": "Clean wooden table, soft kitchen background (blurred)",
    "surface": "Dark wood cutting board",
    "context": "Restaurant kitchen ambiance",
    "cultural_touches": "None needed (universal food appeal)"
  },
  
  "camera_movement": {
    "angle": "Eye-level, slightly overhead",
    "movement": "Slow dolly-in (2s)",
    "speed": "Slow (luxurious)"
  },
  
  "lighting_color": {
    "lighting_style": "Soft natural light from side window",
    "palette": "Warm golden tones, rich browns",
    "highlights": "On burger top (cheese glisten)",
    "shadows": "Soft shadows on left side"
  },
  
  "visual_effects": {
    "motion": "Steam rising gently",
    "transitions": "Fade in from black",
    "particles": "None"
  },
  
  "sound_audio": {
    "audio_generation_supported": true,
    "sfx_for_generation": {
      "product_sounds": ["burger sizzle", "steam hiss"],
      "environment_sounds": ["quiet kitchen ambience"],
      "volume": "medium"
    },
    "music_for_generation": {
      "auto_generate": true,
      "style": "upbeat acoustic guitar",
      "mood": "appetizing",
      "volume": "background_subtle"
    },
    "voiceover_optional": {
      "required": false
    }
  },
  
  "text_overlay_optional": {
    "display": "None in this scene",
    "note": "تُضاف في المونتاج إن لزم"
  },
  
  "branding": {
    "logo_display": "None yet",
    "color_scheme": "Warm browns, golden yellow"
  },
  
  "negative_prompts": {
    "exclude": "Plastic-looking burger, cartoonish steam, overly glossy/fake"
  },
  
  "technical": {
    "duration": "2s",
    "aspect_ratio": "1:1",
    "resolution": "1080p",
    "fps": "24fps",
    "audio_type": "music_sfx",
    "ai_generator": "Pika"
  }
}
```````````

#### **Scene 2 – Ingredients Close-Up (2s)**
```````````json
{
  "scene_number": "S2",
  "title": "Ingredients Floating",
  "duration": "2s",
  
  "product_subject": {
    "item": "Deconstructed burger layers (bun, patty, cheese, lettuce, tomato)",
    "appearance": "Each ingredient separated vertically in mid-air",
    "state": "Floating, slowly rotating (levitation effect)",
    "emotional_association": "Quality, transparency"
  },
  
  "environment": {
    "setting": "Clean white/light gray background",
    "surface": "None (floating)",
    "context": "Studio-style product showcase"
  },
  
  "camera_movement": {
    "angle": "Eye-level",
    "movement": "Slow 360° orbit around floating ingredients",
    "speed": "Medium"
  },
  
  "lighting_color": {
    "lighting_style": "Bright studio lighting, even",
    "palette": "Vibrant greens (lettuce), red (tomato), golden (bun)",
    "highlights": "On cheese and patty surface",
    "shadows": "None (clean studio look)"
  },
  
  "visual_effects": {
    "motion": "Levitation, slow rotation",
    "transitions": "Cross-dissolve from S1",
    "particles": "Subtle light sparkle on cheese"
  },
  
  "sound_audio": {
    "sfx_for_generation": {
      "product_sounds": ["soft whoosh as ingredients float"],
      "volume": "subtle"
    },
    "music_for_generation": {
      "style": "continues from S1",
      "mood": "curious",
      "sync_with_motion": true
    }
  },
  
  "text_overlay_optional": {
    "display": "١٠٠٪ لحم طازج (center, appears for 1s)",
    "style": "Bold Arabic text, white with shadow",
    "language": "AR (RTL)",
    "timing": "Mid-scene",
    "note": "يُضاف في المونتاج"
  },
  
  "technical": {
    "duration": "2s",
    "aspect_ratio": "1:1",
    "fps": "30fps (smooth motion)",
    "ai_generator": "Pika / Runway"
  }
}
```````````

#### **Scene 3 – Assembly (2s)**
```````````json
{
  "scene_number": "S3",
  "title": "Burger Assembly",
  "duration": "2s",
  
  "product_subject": {
    "item": "Burger being assembled (top bun coming down)",
    "state": "Motion (assembly animation)"
  },
  
  "camera_movement": {
    "angle": "Side view, eye-level",
    "movement": "Static (focus on assembly)"
  },
  
  "visual_effects": {
    "motion": "Top bun slowly lands on burger",
    "particles": "Tiny sesame seeds falling"
  },
  
  "sound_audio": {
    "sfx_for_generation": {
      "product_sounds": ["soft plop as bun lands"],
      "volume": "medium"
    },
    "music_for_generation": {
      "style": "builds to crescendo",
      "mood": "satisfying"
    }
  },
  
  "technical": {
    "duration": "2s",
    "fps": "24fps"
  }
}
```````````

#### **Scene 4 – Branding & CTA (2s)**
```````````json
{
  "scene_number": "S4",
  "title": "Final Hero Shot + Branding",
  "duration": "2s",
  
  "product_subject": {
    "item": "Final burger on board, perfect shot",
    "state": "Static, steam still rising"
  },
  
  "camera_movement": {
    "angle": "Slight overhead",
    "movement": "Very slow zoom-out"
  },
  
  "sound_audio": {
    "music_for_generation": {
      "style": "final uplifting chord"
    },
    "voiceover_optional": {
      "required": true,
      "text": "Burger House — طازج، سريع، لذيذ",
      "language": "Bahraini_Arabic",
      "voice": "male_warm",
      "timing": "throughout S4 (2s)"
    }
  },
  
  "text_overlay": {
    "display": [
      "Burger House (brand name, top)",
      "يبدأ من ١.٥ د.ب (bottom)",
      "#إعلان (small, corner)"
    ],
    "style": "Clean, bold Arabic + English",
    "language": "Bilingual (AR RTL + EN)"
  },
  
  "branding": {
    "logo": "Small logo top-right corner",
    "color_scheme": "Brand colors (gold, brown, white)"
  }
}
```````````

---

### **Post-Generation Notes (Product-Focused):**
```````````yaml
continuity:
  product: "نفس البرجر عبر المشاهد (لون، حجم، تفاصيل)"
  environment: "نفس الطاولة الخشبية في S1, S3, S4"
  lighting: "دافئة طبيعية، متسقة"
  color_grading: "Warm tones throughout"
  text_overlay: "يُضاف في المونتاج (DaVinci Resolve / Premiere Pro)"
  soundtrack: "Upbeat acoustic guitar (60-90 BPM)"
  disclosure: "#إعلان يظهر في S4 (ركن السفلي)"
  export: "1:1 ratio, 1080p, 24fps, MP4 H.264"
```````````

---

### **🎭 Template 2: Character-Based (قصة مع شخصيات)**
```````````markdown
## **Character-Based Video Template**

**Scenario Type:** Character-Based  
**Best For:** بناء ثقة، عاطفي، relatable  
**Duration:** 10-30s  
**AI Generators:** Veo 3.1, Sora 2, Kling Wan 2.5  
**Audio:** Dialogue (مُولَّد) + Music + SFX

---

**Example: "Burger Discovery Story" (12s)**

#### **Scene 1 – The Problem (3s)**
``````````json
{
  "scene_number": "S1",
  "title": "The Problem — Disappointment",
  "duration": "3s",
  "type": "character_based",
  
  "character_subject": {
    "appearance": "Male, 26, casual t-shirt, messy hair, tired expression",
    "emotion": "Disappointment, frustration",
    "body_language": "Shoulders slumped, looking down at burger",
    "eye_contact": "At burger (disgust)"
  },
  
  "environment": {
    "location": "Living room couch, Bahrain apartment",
    "details": "TV playing in background, delivery bag on coffee table",
    "atmosphere": "Dim evening light, casual home setting"
  },
  
  "action_movement": {
    "character_actions": "Opens delivery bag, pulls out flat boring burger, sighs heavily",
    "pacing": "Slow, disappointed",
    "interaction": "With delivery bag and burger"
  },
  
  "camera": {
    "angle": "Close-up on hands and burger, then zoom-out to face",
    "lens": "Medium close-up",
    "movement": "Slow zoom-out"
  },
  
  "lighting_color": {
    "tone": "Dim cool blue-gray",
    "palette": "Muted, lifeless colors",
    "contrast": "Low"
  },
  
  "sound_voice": {
    "audio_generation_supported": true,
    
    "dialogue_for_generation": {
      "language": "Bahraini_Arabic",
      "lines": "شنو هالبرجر الممل هذا؟",
      "voice_characteristics": {
        "gender": "male",
        "age": "young_adult",
        "tone": "frustrated",
        "accent": "Bahraini",
        "emotion": "disappointed_annoyed",
        "pace": "medium"
      },
      "pronunciation_notes": "نطق 'شنو' بلهجة بحرينية واضحة، تشديد على 'ممل'",
      "lip_sync_priority": "high"
    },
    
    "sfx_for_generation": {
      "auto_generate": true,
      "specific_sounds": ["delivery bag crinkling", "disappointed sigh"],
      "environment_ambience": "quiet home",
      "volume_balance": "dialogue_primary"
    },
    
    "music_for_generation": {
      "auto_generate": true,
      "style": "tense minor key",
      "mood": "disappointed",
      "volume": "background_subtle"
    }
  },
  
  "props": {
    "items": "Generic delivery bag, flat boring burger, phone on table"
  },
  
  "negative_prompts": {
    "exclude": "Cartoonish, fake burger, plastic furniture"
  },
  
  "technical": {
    "duration": "3s",
    "aspect_ratio": "9:16",
    "resolution": "1080p",
    "fps": "24fps",
    "audio_type": "dialogue_generated + music_sfx_generated",
    "ai_generator": "Veo 3.1"
  }
}
``````````

#### **Scene 2 – Discovery (3s)**
``````````json
{
  "scene_number": "S2",
  "title": "The Discovery — Hope",
  "duration": "3s",
  
  "character": "Same, now picking up phone with curious expression",
  "emotion": "Curiosity, hope",
  "action": "Scrolling on phone, eyes widen, taps screen",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "يالله نجرب Burger House...",
    "voice_characteristics": {
      "tone": "curious_hopeful",
      "emotion": "interest_building"
    }
  },
  
  "sfx": ["phone tap", "notification chime"],
  "music": "curious ascending notes"
}
``````````

#### **Scene 3 – Solution (4s)**
``````````json
{
  "scene_number": "S3",
  "title": "The Solution — Delight",
  "duration": "4s",
  
  "character": "Excited, opening fresh Burger House bag",
  "action": "Opens bag, lifts burger (steam), takes big bite, closes eyes in satisfaction",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "وااااو! هذا برجر حقيقي!",
    "voice_characteristics": {
      "tone": "joyful_excited",
      "emotion": "delight_satisfaction",
      "pace": "fast (excited)"
    },
    "pronunciation_notes": "تطويل 'وااااو' لإظهار الإعجاب"
  },
  
  "sfx": ["bag opening", "satisfying crunch bite", "burger sizzle"],
  "music": "uplifting major key"
}
``````````

#### **Scene 4 – CTA (2s)**
``````````json
{
  "scene_number": "S4",
  "title": "Call to Action",
  "duration": "2s",
  
  "character": "Satisfied, thumbs up to camera",
  "action": "Wipes mouth, thumbs up, nods",
  
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "اطلب الحين — توصيل ٢٥ دقيقة!",
    "voice_characteristics": {
      "tone": "enthusiastic_recommending"
    }
  },
  
  "voiceover_disclosure": {
    "text": "#إعلان",
    "timing": "first_1_second",
    "volume": "clear_audible"
  }
}
``````````

---

### **🤖 Template 3: Virtual Influencer (أفاتار رقمي)**
``````````markdown
## **Virtual Influencer Video Template**

**Scenario Type:** Virtual Influencer (AI Avatar)  
**Best For:** مصداقية، توصية شخصية، محتوى متكرر  
**Duration:** 15-30s  
**AI Generators:** HeyGen, D-ID, Synthesia, Veo 3.1  
**Audio:** Dialogue (مُولَّد مباشرة) + Music

---

**Single Scene Structure (20s):**
`````````json
{
  "scenario_type": "virtual_influencer",
  "duration": "20s",
  
  "avatar_character": {
    "appearance": "أنثى، 28 سنة، شعر طويل داكن، عباية كاجوال معاصرة، مكياج بسيط",
    "personality": "ودية، واثقة، relatable",
    "name": "نورة — عشاق البرجر 🍔",
    "setting": "خلفية بسيطة (gradient ناعم أو مكتب منزلي)",
    "cultural_fit": "ملابس محتشمة، سياق بحريني"
  },
  
  "script_dialogue": {
    "language": "Bahraini_Arabic",
    "full_script": [
      "[0-5s] السلام عليكم! أنا نورة، وصراحة كنت أدور على برجر صج لذيذ...",
      "[5-12s] جربت Burger House وشنو أقولكم؟ اللحم طازج، الصوص خيالي، والتوصيل سريع.",
      "[12-17s] صار المطعم المفضل حقي، وأنصحكم تجربونه.",
      "[17-20s] اطلبوا الحين من الرابط — ما راح تندمون! 🍔"
    ],
    "voice_characteristics": {
      "gender": "female",
      "age": "young_adult",
      "tone": "friendly_confident",
      "accent": "Bahraini",
      "emotion": "enthusiastic",
      "pace": "medium"
    }
  },
  
  "camera": {
    "angle": "eye-level (direct to camera)",
    "framing": "medium close-up (shoulders and face)",
    "movement": "static (professional)"
  },
  
  "lighting": {
    "style": "soft studio lighting",
    "palette": "warm, inviting"
  },
  
  "visual_elements": {
    "lower_third": "نورة — عشاق البرجر 🍔 (يظهر 0-3s)",
    "product_overlay": "صورة برجر صغيرة (10-12s)",
    "cta_text": "اطلب الآن ↗️ (18-20s)",
    "disclosure": "#إعلان (corner, 0-20s)"
  },
  
  "compliance": {
    "disclosure": "#إعلان (نص + صوت في البداية)",
    "avatar_consistency": "نفس الشخصية (نورة) عبر جميع الفيديوهات",
    "cultural_fit": "✅"
  },
  
  "technical": {
    "duration": "20s",
    "aspect_ratio": "9:16",
    "resolution": "1080p",
    "fps": "30fps",
    "audio_type": "dialogue_generated",
    "ai_generator": "HeyGen"
  }
}
`````````

**Post-Generation Notes:**
- استخدم نفس الأفاتار (نورة) في جميع الفيديوهات للاتساق
- يمكن تغيير الخلفية حسب المنتج
- النص يُكتب في HeyGen/D-ID مباشرة
- الصوت يُولَّد تلقائياً بلهجة بحرينية

---

### **🎆 Template 4: VFX/Cinematic (خدع بصرية)**
`````````markdown
## **VFX Cinematic Video Template**

**Scenario Type:** VFX/Cinematic Surreal  
**Best For:** جذب انتباه، viral potential، منتجات فريدة  
**Duration:** 10-20s  
**AI Generators:** Runway Gen-3, Pika, Sora 2  
**Audio:** Music (دراما) + SFX قوية

---

**Example: "Burger Explosion & Reassembly" (15s)**

#### **Scene 1 — Explosion (0-5s)**
````````json
{
  "scene_number": "S1",
  "title": "Burger Explosion",
  "duration": "5s",
  
  "product": "Burger on dark table",
  "action": "Burger explodes outward in slow-motion",
  
  "elements_flying": [
    "Bun top (upward)",
    "Patty (center burst)",
    "Lettuce leaves (spinning)",
    "Cheese (melting mid-air)",
    "Tomato slices (radial)"
  ],
  
  "camera": {
    "movement": "Slow-motion (120fps feel), zoom-out",
    "angle": "Eye-level"
  },
  
  "lighting": {
    "style": "Dark background, spotlight on burger",
    "palette": "Dark + golden highlights",
    "vfx_lighting": "Particles glowing"
  },
  
  "visual_effects": {
    "motion": "Explosion radial outward",
    "particles": "Light rays, fire sparks, energy waves",
    "speed": "Slow-motion (0.3x speed)"
  },
  
  "sound_audio": {
    "sfx": "Explosion whoosh, dramatic bass drop",
    "music": "Epic orchestral hit"
  },
  
  "technical": {
    "duration": "5s",
    "fps": "60fps (for slow-mo effect)",
    "ai_generator": "Runway Gen-3"
  }
}
````````

#### **Scene 2 — Floating (5-10s)**
````````json
{
  "scene_number": "S2",
  "title": "Floating Ingredients",
  "duration": "5s",
  
  "action": "Ingredients float and rotate in mid-air",
  
  "camera": {
    "movement": "360° orbit around floating pieces"
  },
  
  "lighting": {
    "style": "Golden spotlight on each ingredient"
  },
  
  "visual_effects": {
    "motion": "Levitation, slow rotation",
    "particles": "Glowing particles, light streaks, magic shimmer"
  },
  
  "sound_audio": {
    "sfx": "Magical shimmer sound, ethereal whoosh",
    "music": "Suspenseful strings"
  }
}
````````

#### **Scene 3 — Reassembly (10-15s)**
````````json
{
  "scene_number": "S3",
  "title": "Magnetic Reassembly",
  "duration": "5s",
  
  "action": "Ingredients fly back together in reverse (magnetic pull)",
  "timing": "Fast (2x speed)",
  
  "camera": {
    "movement": "Zoom-in as burger reforms"
  },
  
  "lighting": {
    "style": "Bright flash as burger completes"
  },
  
  "visual_effects": {
    "motion": "Reverse explosion, magnetic snap",
    "particles": "Energy waves converging, final burst of light"
  },
  
  "sound_audio": {
    "sfx": "Magnetic 'snap' sound, satisfying click, final 'boom'",
    "music": "Triumphant chord"
  }
}
````````

#### **Scene 4 — Hero Shot (15-18s)**
````````json
{
  "scene_number": "S4",
  "title": "Final Product",
  "duration": "3s",
  
  "product": "Perfect burger, steam rising",
  "camera": "Slow push-in, static hero shot",
  "lighting": "Warm golden glow",
  
  "text_overlay": {
    "display": "Burger House — طازج كل يوم",
    "timing": "Throughout (3s)"
  },
  
  "branding": {
    "logo": "Center",
    "cta": "اطلب الآن",
    "disclosure": "#إعلان"
  },
  
  "sound_audio": {
    "sfx": "Sizzle sound",
    "music": "Final note fade"
  }
}
````````

**تحذير:** لا تبالغ في التأثيرات حتى لا يفقد المنتج مصداقيته. استخدم بحذر مع منتجات B2B.

---

### **📚 Template 5: Educational (تعليمي)**
````````markdown
## **Educational Video Template**

**Scenario Type:** Educational/How-To  
**Best For:** بناء سلطة، engagement عالي، قيمة مجانية  
**Duration:** 30-60s  
**AI Generators:** أي مولد + نصوص في المونتاج  
**Audio:** Voiceover تعليمي + موسيقى هادئة

---

**Example: "3 علامات البرجر الطازج" (40s)**

#### **Intro (0-5s)**
```````json
{
  "scene": "Opening",
  "visual": "سؤال على شاشة + برجر غير واضح",
  "text_overlay": "هل تعرف كيف تختار برجر طازج؟",
  "voiceover": "كثير ناس ما يعرفون الفرق...",
  "music": "هادئة، فضولية"
}
```````

#### **Step 1 (5-15s)**
```````json
{
  "scene": "Step 1",
  "title_overlay": "١. اللحم يجب أن يكون بنياً (ليس رمادياً)",
  "visual": "مقارنة لحم طازج vs قديم (split screen)",
  "voiceover": {
    "language": "Bahraini_Arabic",
    "text": "اللحم الطازج لونه بني غامق، مو رمادي..."
  },
  "camera": "Close-up على اللحم",
  "duration": "10s"
}
```````

#### **Step 2 (15-25s)**
```````json
{
  "scene": "Step 2",
  "title_overlay": "٢. الخبز محمص (ليس طرياً جداً)",
  "visual": "خبز محمص vs طري (side by side)",
  "voiceover": "الخبز الطازج يكون محمص من برا، طري من داخل..."
}
```````

#### **Step 3 (25-35s)**
```````json
{
  "scene": "Step 3",
  "title_overlay": "٣. رائحة واضحة (ليست معدومة)",
  "visual": "شخص (أو يد) يشم البرجر ويبتسم",
  "voiceover": "البرجر الطازج له رائحة قوية..."
}
```````

#### **CTA (35-40s)**
```````json
{
  "scene": "Branding & CTA",
  "text_overlay": "في Burger House — كل برجر طازج كل يوم ✅",
  "visual": "برجر كامل جميل + logo",
  "voiceover": "جرّب الفرق الحقيقي الآن",
  "cta": "اطلب عبر الرابط",
  "disclosure": "#إعلان"
}
```````

**Notes:**
- النصوص على الشاشة كبيرة وواضحة (RTL)
- الخطوات مرقّمة ومرئية
- الصوت هادئ تعليمي (ليس مبالغ)

---

### **📢 Template 6: Awareness/PSA (توعوي)**
```````markdown
## **Awareness/PSA Video Template**

**Scenario Type:** Awareness (Public Service)  
**Best For:** brand values، مسؤولية اجتماعية، بناء صورة  
**Duration:** 20-30s  
**Audio:** موسيقى ملهمة + voiceover قوي

---

**Example: "النظافة مسؤولية الجميع" (شركة تنظيف — 25s)**

#### **Scene 1 (0-8s)**
``````json
{
  "scene": "Community",
  "visual": "أطفال يلعبون في حديقة نظيفة، عائلات تمشي",
  "text_overlay": "نظافة مجتمعنا تبدأ من بيوتنا",
  "voiceover": {
    "language": "Bahraini_Arabic",
    "text": "كل بيت نظيف يعني مجتمع صحي وآمن...",
    "tone": "ملهم، هادئ"
  },
  "music": "ملهمة، بطيئة",
  "camera": "Wide shots، cinematic"
}
``````

#### **Scene 2 (8-16s)**
``````json
{
  "scene": "Solution",
  "visual": "Transition إلى بيت نظيف منظم، أم سعيدة",
  "text_overlay": "سكوب لاين — نساعدك تحافظ على بيتك",
  "voiceover": "نحن هنا لنخفف عنك... ونوفّر وقتك لأهم الأشياء",
  "music": "تتصاعد"
}
``````

#### **Scene 3 (16-25s)**
``````json
{
  "scene": "Call to Action",
  "visual": "عائلة سعيدة في بيت نظيف، شعار الشركة",
  "text_overlay": "لأن النظافة حق للجميع",
  "voiceover": "احجز خدمتنا اليوم — لبيت أنظف وحياة أسهل",
  "cta": "احجز الآن",
  "disclosure": "#إعلان",
  "music": "نهاية ملهمة"
}
``````

**Notes:**
- النبرة ملهمة وليست تجارية مباشرة
- الربط بين القيمة الاجتماعية والخدمة طبيعي
- يُستخدم في مناسبات خاصة (اليوم الوطني، حملات مجتمعية)

---

### **📱 Template 7: UGC Style (محتوى مستخدم)**
``````markdown
## **UGC Style Video Template**

**Scenario Type:** UGC (User-Generated Content Style)  
**Best For:** مصداقية، relatable، تكلفة منخفضة  
**Duration:** 10-20s  
**AI Generators:** Veo 3.1, Kling Wan 2.5  
**Audio:** حوار طبيعي + أصوات بيئة

---

**Example: "Unboxing Reaction" (15s)**
`````json
{
  "scenario_type": "ugc_style",
  "duration": "15s",
  
  "style_guidelines": {
    "camera": "Handheld vertical (9:16), شخص يمسك الهاتف",
    "quality": "غير مصقول، واقعي (ليس احترافي جداً)",
    "lighting": "طبيعية (إضاءة غرفة/نافذة)",
    "framing": "غير مثالي (authentic)"
  },
  
  "character": {
    "appearance": "شاب عادي، ملابس كاجوال",
    "personality": "متحمس، صادق، relatable"
  },
  
  "script_flow": [
    {
      "timing": "0-3s",
      "action": "يمسك كيس التوصيل، يبتسم للكاميرا",
      "dialogue": "شوفوا شنو وصلني اليوم!",
      "emotion": "فضول، تشويق"
    },
    {
      "timing": "3-8s",
      "action": "يفتح الكيس، يُخرج البرجر، عيونه تتسع",
      "dialogue": "واااو! شوفوا هالحجم! ريحته خيالية...",
      "emotion": "مفاجأة سعيدة"
    },
    {
      "timing": "8-12s",
      "action": "يقضم، يمضغ، يغلق عينيه بارتياح",
      "dialogue": "مممم... صدق طعمه مو طبيعي! اللحم طري والصوص...",
      "emotion": "استمتاع"
    },
    {
      "timing": "12-15s",
      "action": "ينظر للكاميرا مباشرة، thumbs up",
      "dialogue": "جربوه — رابط في البايو! #إعلان",
      "emotion": "توصية صادقة"
    }
  ],
  
  "audio": {
    "dialogue_language": "Bahraini_Arabic (غير رسمي، كلام شارع)",
    "voice_tone": "حماسي، طبيعي، غير مكتوب",
    "background": "أصوات بيئة (TV بعيد، هاتف يرن)"
  },
  
  "visual_effects": {
    "none": "بدون تأثيرات (raw)"
  },
  
  "compliance": {
    "disclosure": "#إعلان في الحوار + نص overlay (15s)"
  },
  
  "technical": {
    "aspect_ratio": "9:16",
    "resolution": "1080p (أو 720p لواقعية أكثر)",
    "fps": "30fps",
    "ai_generator": "Veo 3.1"
  }
}
`````

**Key Tips:**
- لا تُصقّل كثيراً — الأصالة مهمة
- الحوار عفوي (ليس سكربت محفوظ)
- أخطاء صغيرة مقبولة (توقف، ضحكة)
- الكاميرا تهتز قليلاً (handheld)

---

### **🎞️ Template 8: Documentary Style (وثائقي)**
`````markdown
## **Documentary Video Template**

**Scenario Type:** Documentary/Behind-the-Scenes  
**Best For:** بناء ثقة، شفافية، علامة تجارية  
**Duration:** 30-60s  
**Production:** تصوير حقيقي (أو AI بأسلوب realistic)  
**Audio:** Voiceover + أصوات طبيعية

---

**Example: "كيف نحضّر البرجر" (45s)**

#### **Opening (0-5s)**
````json
{
  "scene": "Introduction",
  "visual": "باب المطبخ يُفتح، كاميرا تدخل",
  "text_overlay": "خلف الكواليس — Burger House",
  "voiceover": "تعالوا نشوف كيف نحضّر برجركم...",
  "style": "Documentary handheld camera"
}
````

#### **Process Scenes (5-35s)**
````json
{
  "scenes": [
    {
      "timing": "5-15s",
      "visual": "طاهٍ يختار اللحم الطازج من الثلاجة",
      "voiceover": "كل صباح، نستلم لحم طازج ١٠٠٪...",
      "camera": "Following chef, natural movements"
    },
    {
      "timing": "15-25s",
      "visual": "تشكيل الفطائر يدوياً، شوي على النار",
      "voiceover": "نشكّل كل فطيرة يدوياً، نشويها على درجة حرارة مضبوطة...",
      "sfx": "Sizzle sounds, kitchen ambience"
    },
    {
      "timing": "25-35s",
      "visual": "تجميع البرجر، إضافة الخضار الطازجة",
      "voiceover": "نضيف خضار محلية طازجة، وصوصاتنا الخاصة...",
      "camera": "Close-ups on fresh ingredients"
    }
  ]
}
````

#### **Closing (35-45s)**
````json
{
  "scene": "Final Message",
  "visual": "برجر جاهز يُعطى للعميل، ابتسامة",
  "text_overlay": "طازج. صادق. لذيذ.",
  "voiceover": "هذا التزامنا لكم — جرّبوا الفرق",
  "cta": "اطلب الآن",
  "disclosure": "#إعلان"
}
````

**Notes:**
- أسلوب واقعي (ليس مصطنع)
- إضاءة طبيعية قدر الإمكان
- موسيقى هادئة في الخلفية
- يبني ثقة طويلة المدى

---

### **🔀 Template 9: Mixed Carousel (صور + فيديو)**
````markdown
## **Mixed Carousel Template**

**Scenario Type:** Hybrid (Images + Video)  
**Best For:** تنويع، جذب انتباه، قصة بصرية  
**Platform:** Instagram/Facebook  
**Total Slides:** 5 (3 صور + 1 فيديو + 1 صورة نهائية)

---

**Structure:**
```json
{
  "carousel_structure": [
    {
      "slide": 1,
      "type": "image",
      "content": "Hook — مشكلة أو سؤال",
      "visual": "صورة برجر ممل/رمادي",
      "text_overlay": "تعبت من البرجر الممل؟",
      "ratio": "1:1"
    },
    {
      "slide": 2,
      "type": "image",
      "content": "Agitation — تصعيد المشكلة",
      "visual": "شخص محبط ينظر لبرجر سيء",
      "text_overlay": "كل مرة نفس الخيبة...",
      "ratio": "1:1"
    },
    {
      "slide": 3,
      "type": "video",
      "content": "Solution — فيديو برجر طازج (8s)",
      "visual": "فيديو برجر يدور 360° مع steam",
      "audio": "موسيقى + sizzle SFX",
      "text_overlay": "جرّب Burger House — طازج كل يوم",
      "duration": "8s",
      "ratio": "1:1"
    },
    {
      "slide": 4,
      "type": "image",
      "content": "Proof — إثبات اجتماعي",
      "visual": "تقييمات 5 نجوم + عدد عملاء",
      "text_overlay": "٤.٨/٥ — أكثر من ١٠٠٠ عميل راضٍ",
      "ratio": "1:1"
    },
    {
      "slide": 5,
      "type": "image",
      "content": "CTA — دعوة للإجراء",
      "visual": "برجر + سعر + logo",
      "text_overlay": "اطلب الآن — يبدأ من ١.٥ د.ب | #إعلان",
      "cta_button": "اطلب الآن",
      "ratio": "1:1"
    }
  ],
  
  "caption": "من البرجر الممل 😞 إلى الطازج اللذيذ 🍔! اسحب لتشوف الفرق... #برجر_البحرين #إعلان",
  
  "hashtags": ["#برجر_هاوس", "#طعام_طازج", "#البحرين", "#إعلان"]
}
```

**Notes:**
- الفيديو في المنتصف (slide 3) لجذب الانتباه
- الصور قبل وبعد تبني القصة
- النسبة 1:1 موحّدة عبر الكاروسيل
- CTA واضح في النهاية

---

## **توطين البحرين (مدمج تلقائيًا)**
```yaml
bahrain_localization:
  
  character_based:
    attire: "ملابس كاجوال معاصرة، دشداشة (رسمي)، عباية محتشمة (نساء)"
    settings: "بيوت حديثة، مكاتب، مقاهي محلية، شوارع المنامة"
    cultural_notes:
      - "تجنب لقطات حميمية غير مناسبة"
      - "احترام الخصوصية"
      - "مواسم: رمضان (فوانيس)، العيد، اليوم الوطني (16-17 ديسمبر)"
  
  product_focused:
    color_palette: "دافئ (ذهبي، بيج، أخضر داكن) للعلامات المحلية"
    props: "أطباق عربية، أكواب قهوة عربية، ديكورات محلية"
    text_overlay: "RTL للعربية، خطوط Cairo/Tajawal"
  
  virtual_influencer:
    avatar_design: "ملامح خليجية، ملابس محتشمة معاصرة"
    language: "لهجة بحرينية/خليجية طبيعية"
    context: "إشارات محلية (أماكن، عادات، مواسم)"
  
  language_rule:
    scenario_text: "إنجليزي دائماً (الوصف البصري، التقني، التعليمات)"
    dialogue_voiceover: "لهجة المستخدم المختارة (بحريني، خليجي، مصري، إنجليزي، أو بدون)"
    text_overlay: "عربي RTL عند الحاجة"
```

---

## **خوارزمية التوليد التلقائي (محدّثة)**
```python
def generate_video_scenario(input):
    # 1. تحديد نوع السيناريو
    scenario_types = {
        "character_based": scene_template_character,
        "product_focused": scene_template_product,
        "virtual_influencer": scene_template_influencer,
        "vfx_cinematic": scene_template_vfx,
        "documentary": scene_template_documentary,
        "educational": scene_template_educational,
        "awareness_psa": scene_template_psa,
        "ugc_style": scene_template_ugc,
        "mixed_carousel": scene_template_carousel
    }
    
    template = scenario_types[input.scenario_type]
    
    # 2. اختيار المولد المناسب
    if input.scenario_type == "virtual_influencer":
        recommended_generator = "HeyGen"
    elif input.scenario_type == "vfx_cinematic":
        recommended_generator = "Runway_Gen3"
    elif input.audio_type == "dialogue_generated":
        recommended_generator = "Veo_3.1"
    else:
        recommended_generator = input.ai_generator or "Veo_3.1"
    
    # 3. Information Check
    if missing_critical_info(input):
        ask_user_clarification()
        if partial_answers():
            assume_reasonable_defaults()
    
    # 4. Scene Breakdown
    scenes = []
    for i in range(1, input.scenes_max + 1):
        scene = create_scene(
            template=template,
            number=i,
            duration=calculate_duration(input.total_seconds, i),
            product_or_character=input.type,
            environment=localize_bahrain(input.location),
            dialogue=input.dialogue.language if needs_dialogue(input.scenario_type) else None,
            audio_type=input.audio_type,
            generator=recommended_generator
        )
        scenes.append(scene)
    
    # 5. Compliance Check
    for scene in scenes:
        validate_universal_rules(scene)
        sanitize_prohibited_content(scene)
        add_disclosure_if_paid(scene)
    
    # 6. Output Packaging
    return {
        "scenario_type": input.scenario_type,
        "full_scenario": scenes,
        "dialogue_script": extract_dialogue(scenes) if input.dialogue.required else None,
        "technical_prompts": generate_ai_prompts(scenes, recommended_generator),
        "continuity_notes": build_continuity_guide(scenes),
        "post_production_notes": audio_text_overlay_instructions(scenes)
    }
```

---

## **أمثلة طلبات وكيفية معالجتها**

| الطلب المختصر | القرار | المولد المقترح | ملاحظات إضافية |
|---------------|--------|----------------|-----------------|
| "فيديو 12 ثانية للبرجر مع قصة عميل" | Character-Based مع حوار بحريني | **Veo 3.1** | 4 مشاهد مع إفصاح صوتي في المشهد الأخير |
| "مشاهد برجر فقط 8 ثوانٍ بدون أشخاص" | Product-Focused بصري بالكامل | **Sora 2** أو **Runway Gen-3** | أضف SFX طبخ في المونتاج |
| "فيديو إنفلونسر افتراضي يوصي بالبرجر" | Virtual Influencer | **HeyGen** | إعداد نص عربي بلهجة بحرينية، CTA واضح |
| "فيديو خدع بصرية للبرجر" | VFX/Cinematic | **Runway Gen-3** | دمج حركة كاميرا سريعة + كشف المنتج في النهاية |
| "فيديو تعليمي: كيف تختار برجر طازج" | Educational | **Veo 3.1** مع Voiceover | استخدم بنية خطوات وتوصيات سلامة غذائية |

---

## **قائمة تحقق امتثال سيناريو الفيديو**

- ✅ لا مشاهير معروفين أو رموز محمية ما لم يوجد تصريح.
- ✅ إفصاح **#إعلان** في أول 3 ثوانٍ (نص وصوت حسب الإمكان).
- ✅ تجنب الوعود المطلقة؛ استخدم نطاقات أو أدلة مرجعية في الحوار.
- ✅ احترام الثقافة المحلية: ملابس محتشمة، سياقات ملائمة، عدم استغلال ديني/وطني.
- ✅ توثيق أي عناصر مضافة في المونتاج (نصوص، موسيقى، ترجمة) ضمن `post_production_notes`.

---

## **التكامل مع الوحدات السابقة**
```yaml
integration:
  from_09_content_planning:
    - "استخدام content_type لتحديد scenario_type تلقائياً"
    - "استخدام weekly/monthly plan لتوزيع أنواع الفيديو"
  
  from_04_adaptation:
    - "استخدام copy.hook كعنوان المشهد الأول"
    - "استخدام copy.story_bab كقوس سردي"
    - "استخدام design_notes كمرجع بصري"
  
  from_02_persuasion:
    - "استخدام emotional_triggers لتحديد نبرة المشاهد"
    - "استخدام cta لصياغة المشهد الأخير"
  
  from_01_market_intel:
    - "استخدام personas لتصميم الشخصيات"
    - "استخدام pains لصياغة مشاهد المشكلة"
    - "استخدام features/benefits لإبراز المنتج"
```

---

## **جدول مقارنة المولدات — Audio Capabilities**

| المولد | صوت | حوار | SFX | موسيقى | مزامنة شفاه | عربي | الأفضل لـ |
|--------|-----|------|-----|--------|------------|------|-----------|
| **Kling Wan 2.5** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | UGC style |
| **Sora 2** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد جداً | سيناريوهات طويلة |
| **Veo 3** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | احترافي |
| **Veo 3.1** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز جداً | ✅ ممتاز | **الأفضل للعربي** |
| **Runway Gen-3** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | VFX/سريع |
| **Pika Labs** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | منتجات ثابتة |
| **Luma Dream** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | مشاهد بسيطة |
| **HeyGen** | ✅ | ✅ | ❌ | ❌ | ✅ ممتاز | ✅ جيد جداً | **Virtual Influencer** |
| **D-ID** | ✅ | ✅ | ❌ | ❌ | ✅ جيد | ✅ جيد | Avatar سريع |
| **Synthesia** | ✅ | ✅ | ❌ | ❌ | ✅ ممتاز | ✅ ممتاز | Corporate |

---

## **مخرجات الوحدة (JSON)**
```json
{
  "video_scenario": {
    "scenario_type": "character_based | product_focused | virtual_influencer | vfx_cinematic | documentary | educational | awareness_psa | ugc_style | mixed_carousel",
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
        "character": { "appearance": "...", "emotion": "frustration" },
        "sound_voice": {
          "audio_generation_supported": true,
          "dialogue_for_generation": {
            "language": "Bahraini_Arabic",
            "lines": "شنو هالبرجر الممل هذا؟",
            "voice_characteristics": {...}
          },
          "sfx_for_generation": {...},
          "music_for_generation": {...}
        }
      }
    ],
    
    "audio_generation_notes": {
      "generator": "Veo 3.1",
      "dialogue_quality": "ممتاز للهجة البحرينية",
      "lip_sync": "تلقائي",
      "post_production": "اختياري — فقط إذا احتاج تحسين"
    },
    
    "continuity_notes": {
      "character": "نفس الملابس عبر المشاهد",
      "environment": "تحسن الإضاءة تدريجياً",
      "props": "إزالة الكيس القديم قبل S3"
    },
    
    "post_production_notes": {
      "text_overlay": "يُضاف في المونتاج (DaVinci Resolve)",
      "music": "يمكن استبدال الموسيقى المُولَّدة",
      "disclosure": "#إعلان في S4 (صوت + نص)"
    },
    
    "compliance": "✅",
    "ready_for_generation": true
  }
}
```

---

## **ملخص حالة (3 أسطر — يُنتج تلقائيًا)**

* **ما تمّ توليده:** سيناريو [scenario_type] ([duration]s، [scenes] مشاهد) لـ [channel]، [audio_type].
* **الامتثال:** ✅ [generator] | ✅ إفصاح #إعلان | ✅ RTL/BHD | ✅ ثقافة بحرينية.
* **الخطوة التالية:** رفع السيناريو لـ [ai_generator] + [post_production_steps].

---

**انتهى ملف 08_video_scenarios.md**
````

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
