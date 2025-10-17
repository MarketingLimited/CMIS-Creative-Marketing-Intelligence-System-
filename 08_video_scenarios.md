# **08_video_scenarios.md**

## **الغرض**

توليد سيناريوهات فيديو احترافية للإعلانات باستخدام **أي مولد فيديو بالذكاء الاصطناعي**، مع دعم نوعين:

1. **Character-Based:** سيناريوهات مع شخصيات وحوار
2. **Product-Focused:** مشاهد منتجات/خدمات بدون شخصيات

**جديد:** دعم كامل للمولدات التي **تُنتج الفيديو مع الصوت مباشرة** (Kling Wan 2.5, Sora 2, Veo 3, Veo 3.1).

التوطين الافتراضي: **مملكة البحرين** (AR/RTL، عملة BHD)، مع امتثال كامل لحواجز الامتثال والسلامة.

---

## **المولدات المدعومة — تصنيف حسب القدرات**
```
ai_generators_classification:
  
  video_with_audio_generation:  # تُنتج فيديو + صوت مباشرة
    - name: "Kling Wan 2.5"
      capabilities:
        - "توليد فيديو + صوت مباشرة"
        - "حوار بلغات متعددة (عربي، إنجليزي، صيني...)"
        - "موسيقى خلفية + SFX تلقائية"
        - "مزامنة حركة الشفاه مع الحوار"
      best_for: ["Character-Based مع حوار", "UGC style", "قصص تسويقية"]
      max_duration: "10s (قابلة للتمديد)"
      audio_input: "نص الحوار + وصف الصوت (tone, accent, emotion)"
    
    - name: "Sora 2 (OpenAI)"
      capabilities:
        - "توليد فيديو + صوت مباشرة"
        - "حوار طبيعي بلهجات متعددة"
        - "SFX واقعية (خطوات، أبواب، طبيعة...)"
        - "موسيقى خلفية تلقائية"
      best_for: ["سيناريوهات طويلة معقدة", "Character-Based", "Product-Focused مع SFX"]
      max_duration: "20s"
      audio_input: "نص الحوار + وصف البيئة الصوتية"
    
    - name: "Veo 3 (Google DeepMind)"
      capabilities:
        - "توليد فيديو + صوت مباشرة"
        - "حوار بجودة عالية (لهجات متعددة)"
        - "موسيقى + SFX احترافية"
        - "مزامنة دقيقة للشفاه"
      best_for: ["إعلانات احترافية", "Character-Based", "B2B videos"]
      max_duration: "8s (Veo 3 Fast) | 60s+ (Veo 3 Standard)"
      audio_input: "نص الحوار كامل + وصف النبرة والعاطفة"
    
    - name: "Veo 3.1 (Google DeepMind — أحدث)"
      capabilities:
        - "توليد فيديو + صوت مباشرة (محسّن)"
        - "حوار أكثر طبيعية"
        - "دعم أفضل للهجات العربية (خليجي، مصري...)"
        - "SFX أكثر واقعية"
      best_for: ["كل أنواع الإعلانات", "أفضل جودة صوت عربي"]
      max_duration: "60s+"
      audio_input: "نص الحوار + لهجة محددة + عاطفة"
  
  video_only_generation:  # تُنتج فيديو فقط (صوت يُضاف لاحقاً)
    - name: "Runway Gen-3"
      capabilities: ["فيديو سريع", "جودة جيدة", "نصوص محدودة"]
      best_for: ["Product-Focused", "مشاهد قصيرة"]
      audio: "يُضاف في المونتاج"
    
    - name: "Pika Labs"
      capabilities: ["ممتاز للمنتجات الثابتة", "حركات بسيطة"]
      best_for: ["Product-Focused", "food photography"]
      audio: "يُضاف في المونتاج"
    
    - name: "Luma Dream Machine"
      capabilities: ["سريع", "جودة متوسطة"]
      best_for: ["مشاهد بسيطة سريعة"]
      audio: "يُضاف في المونتاج"
    
    - name: "Stable Video Diffusion"
      capabilities: ["مفتوح المصدر", "قابل للتخصيص"]
      best_for: ["تجارب", "استخدامات خاصة"]
      audio: "يُضاف في المونتاج"
```

---

## **المدخلات المتوقعة (محدّثة)**
```json
{
  "scenario_type": "character_based|product_focused",
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
    "voice_characteristics": "male_warm|female_confident|neutral_calm"  // ← جديد
  },
  "technical_specs": {
    "duration_seconds": [6, 8, 10, 15, 30, 60],
    "aspect_ratio": "9:16|16:9|1:1",
    "scenes_max": 4,
    "ai_generator": "Kling_Wan_2.5|Sora_2|Veo_3|Veo_3.1|Runway|Pika|Luma|Any",
    "audio_generation": true|false  // ← جديد: هل المولد يدعم توليد الصوت؟
  },
  "audio_type": "dialogue_generated|music_sfx_generated|music_only|silent",  // ← محدّث
  "market": { "name": "Bahrain", "language": "AR", "currency": "BHD", "direction": "RTL" }
}
```

---

## **قالب المشهد — Character-Based (مع مولدات الصوت)**

### **إضافة حقول جديدة للصوت المُولَّد:**
```markdown
  sound_voice:
    audio_generation_supported: true|false  // ← جديد
    
    # إذا audio_generation_supported = true:
    dialogue_for_generation:
      language: "Bahraini_Arabic | Gulf_Arabic | Egyptian_Arabic | English"
      lines: "[النص الكامل بلهجة المستخدم]"
      voice_characteristics:
        gender: "male | female | neutral"
        age: "young_adult | middle_aged | elderly"
        tone: "urgent | calm | persuasive | friendly | authoritative"
        accent: "Bahraini | Gulf | Egyptian | Levantine | Standard_Arabic"
        emotion: "frustrated | curious | relieved | joyful | confident"
        pace: "fast | medium | slow"
      pronunciation_notes: "[ملاحظات نطق خاصة إن لزم]"
      lip_sync_priority: "high | medium | low"  // مدى أهمية مزامنة الشفاه
    
    sfx_for_generation:
      auto_generate: true  // السماح للمولد بتوليد SFX تلقائياً
      specific_sounds: ["footsteps", "door creak", "phone ring", "typing"]
      environment_ambience: "quiet home | busy street | office | cafe"
      volume_balance: "dialogue_primary | balanced | sfx_primary"
    
    music_for_generation:
      auto_generate: true
      style: "tense minor key | uplifting major | calm ambient | energetic"
      mood: "suspenseful | hopeful | celebratory | professional"
      volume: "background_subtle | balanced | foreground_noticeable"
    
    # إذا audio_generation_supported = false:
    audio_post_production:
      dialogue: "يُسجَّل ويُضاف في المونتاج"
      sfx: "مكتبة SFX خالية من حقوق الملكية"
      music: "مكتبة موسيقى (Epidemic Sound / Artlist)"
```

---

## **قالب المشهد — Product-Focused (مع مولدات الصوت)**

### **إضافة حقول SFX المُولَّدة:**
```markdown
  sound_audio:
    audio_generation_supported: true|false  // ← جديد
    
    # إذا audio_generation_supported = true:
    sfx_for_generation:
      product_sounds: ["sizzle", "crunch", "pour", "packaging rustle"]
      environment_sounds: ["none", "kitchen ambience", "outdoor nature"]
      impact_sounds: ["product landing on surface", "ice clinking"]
      volume: "subtle | medium | prominent"
    
    music_for_generation:
      auto_generate: true
      style: "upbeat acoustic | luxurious orchestral | energetic electronic"
      mood: "appetizing | premium | exciting"
      sync_with_motion: true  // مزامنة الموسيقى مع حركة الكاميرا
    
    voiceover_optional:
      required: false
      text: "Burger House — طازج، سريع، لذيذ"
      language: "Bahraini_Arabic"
      voice: "male_warm | female_confident"
      timing: "end of video (S4)"
    
    # إذا audio_generation_supported = false:
    audio_post_production:
      sfx: "يُضاف في المونتاج"
      music: "مكتبة موسيقى"
      voiceover: "يُسجَّل ويُضاف"
```

---

## **مثال سيناريو كامل — Character-Based مع Veo 3.1 (صوت مُولَّد)**

### **📹 Scenario: "Burger House Bahrain — Veo 3.1 Full Audio"**

**Campaign:** Young professional discovers fresh burgers  
**Type:** Character-Based  
**Duration:** 12s (4 scenes × 3s)  
**Aspect Ratio:** 9:16  
**Dialogue:** Bahraini Arabic (مُولَّد مباشرة)  
**Audio:** Dialogue + Music + SFX (كلها مُولَّدة)  
**AI Generator:** **Veo 3.1** (audio_generation_supported: true)

---

#### **Scene 1 – The Problem (3s)**

**Character/Subject Focus:**
- Appearance: Male, 26, casual t-shirt, tired expression
- Emotion: Disappointment, frustration
- Body Language: Shoulders slumped, looking down at burger
- Eye Contact: At burger (disgust)

**Environment:**
- Location: Living room couch, evening
- Atmosphere: Dim, disappointed

**Action:**
- Opens delivery bag, pulls out flat boring burger, sighs heavily

**Camera:**
- Angle: Close-up on hands and burger
- Movement: Slow zoom-out to face

**Lighting:**
- Tone: Dim cool blue-gray
- Palette: Muted, lifeless

**Sound/Voice — FOR VEO 3.1 GENERATION:**
```json
{
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
    "pronunciation_notes": "نطق 'شنو' بلهجة بحرينية واضحة، تشديد على 'ممل' بنبرة إحباط",
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
}
```

**Props:** Generic delivery bag, flat burger, phone on table

**Technical:**
- Duration: 3s
- Aspect Ratio: 9:16
- Resolution: 1080p
- FPS: 24fps
- AI Generator: **Veo 3.1**
- Audio Type: **dialogue_generated + music_sfx_generated**

---

#### **Scene 2 – The Discovery (3s)**

**Character:** Same, now curious, picking up phone

**Action:** Scrolling, eyes widen, taps screen (order)

**Sound/Voice — FOR VEO 3.1 GENERATION:**
```json
{
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "يالله نجرب Burger House...",
    "voice_characteristics": {
      "gender": "male",
      "age": "young_adult",
      "tone": "curious_hopeful",
      "accent": "Bahraini",
      "emotion": "interest_building",
      "pace": "medium"
    },
    "pronunciation_notes": "نطق 'Burger House' بلكنة عربية خفيفة",
    "lip_sync_priority": "high"
  },
  
  "sfx_for_generation": {
    "specific_sounds": ["phone tap", "notification chime"],
    "environment_ambience": "quiet home"
  },
  
  "music_for_generation": {
    "style": "curious ascending notes",
    "mood": "hopeful"
  }
}
```

**Technical:**
- Duration: 3s
- AI Generator: **Veo 3.1**
- Audio: **dialogue_generated + music_sfx_generated**

---

#### **Scene 3 – The Solution (4s)**

**Character:** Excited, opening fresh Burger House delivery

**Action:** Opens bag, lifts burger (steam), takes big bite, closes eyes in satisfaction

**Sound/Voice — FOR VEO 3.1 GENERATION:**
```json
{
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "وااااو! هذا برجر حقيقي!",
    "voice_characteristics": {
      "gender": "male",
      "age": "young_adult",
      "tone": "joyful_excited",
      "accent": "Bahraini",
      "emotion": "delight_satisfaction",
      "pace": "fast (excited)"
    },
    "pronunciation_notes": "تطويل 'وااااو' لإظهار الإعجاب، تشديد على 'حقيقي'",
    "lip_sync_priority": "high"
  },
  
  "sfx_for_generation": {
    "specific_sounds": ["bag opening rustle", "satisfying crunch bite"],
    "product_sounds": ["burger sizzle subtle"],
    "environment_ambience": "quiet home"
  },
  
  "music_for_generation": {
    "style": "uplifting major key",
    "mood": "celebratory",
    "volume": "balanced"
  }
}
```

**Technical:**
- Duration: 4s
- AI Generator: **Veo 3.1**
- Audio: **dialogue_generated + music_sfx_generated**

---

#### **Scene 4 – The CTA (2s)**

**Character:** Satisfied, thumbs up to camera

**Action:** Wipes mouth, thumbs up, nods

**Sound/Voice — FOR VEO 3.1 GENERATION:**
```json
{
  "dialogue_for_generation": {
    "language": "Bahraini_Arabic",
    "lines": "اطلب الحين — توصيل ٢٥ دقيقة!",
    "voice_characteristics": {
      "gender": "male",
      "age": "young_adult",
      "tone": "enthusiastic_recommending",
      "accent": "Bahraini",
      "emotion": "confident_happy",
      "pace": "medium"
    },
    "pronunciation_notes": "نطق 'الحين' بلهجة بحرينية، التشديد على '٢٥ دقيقة'",
    "lip_sync_priority": "high"
  },
  
  "voiceover_disclosure": {
    "text": "#إعلان",
    "language": "Arabic",
    "voice": "same_as_character",
    "timing": "first_1_second",
    "volume": "clear_audible"
  },
  
  "sfx_for_generation": {
    "specific_sounds": ["satisfied 'mmm' sound"],
    "auto_generate": true
  },
  
  "music_for_generation": {
    "style": "final uplifting chord",
    "mood": "resolved_happy"
  }
}
```

**Technical:**
- Duration: 2s
- AI Generator: **Veo 3.1**
- Audio: **dialogue_generated + voiceover + music_sfx_generated**

---

### **📋 Post-Generation Notes (مع Veo 3.1):**
```
continuity:
  character: "نفس القميص والشعر عبر المشاهد"
  environment: "نفس الصالة، تحسن الإضاءة تدريجياً"
  audio_quality: "Veo 3.1 سيُنتج صوت متسق عبر المشاهد"
  lip_sync: "مزامنة تلقائية — لا حاجة لتدخل يدوي"
  dialogue_naturalness: "تحقق من طبيعية اللهجة البحرينية، أعد التوليد إن لزم"
  disclosure: "#إعلان مُولَّد صوتياً في S4 أول ثانية"
  
post_generation_optional:
  music_replacement: "يمكن استبدال الموسيقى المُولَّدة بمكتبة احترافية إن لزم"
  sfx_enhancement: "يمكن تعزيز SFX في المونتاج"
  dialogue_re_recording: "نادراً — فقط إذا كانت اللهجة غير دقيقة"
```

---

## **مثال سيناريو Product-Focused مع Sora 2 (SFX مُولَّدة)**

### **📦 Scenario: "Burger Showcase — Sora 2 with SFX"**

**Type:** Product-Focused  
**Duration:** 8s  
**Aspect Ratio:** 1:1  
**Dialogue:** None  
**Audio:** Music + SFX (مُولَّدة مباشرة)  
**AI Generator:** **Sora 2** (audio_generation_supported: true)

---

#### **Scene 1 – Product Reveal (2s)**

**Product:** Fresh burger with steam

**Sound/Audio — FOR SORA 2 GENERATION:**
```json
{
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
  }
}
```

**Technical:**
- Duration: 2s
- AI Generator: **Sora 2**
- Audio: **music_sfx_generated** (no dialogue)

---

#### **Scene 2 – Ingredients Float (2s)**

**Product:** Deconstructed burger layers floating

**Sound/Audio — FOR SORA 2 GENERATION:**
```json
{
  "sfx_for_generation": {
    "product_sounds": ["soft whoosh as ingredients float"],
    "impact_sounds": ["none"],
    "volume": "subtle"
  },
  
  "music_for_generation": {
    "style": "continues from S1",
    "mood": "curious",
    "sync_with_motion": true
  }
}
```

---

#### **Scene 3 – Assembly (2s)**

**Product:** Burger being assembled

**Sound/Audio — FOR SORA 2 GENERATION:**
```json
{
  "sfx_for_generation": {
    "product_sounds": ["bun landing plop", "sesame seeds falling"],
    "volume": "medium"
  },
  
  "music_for_generation": {
    "style": "builds to crescendo",
    "mood": "satisfying"
  }
}
```

---

#### **Scene 4 – Branding (2s)**

**Product:** Final hero shot

**Sound/Audio — FOR SORA 2 GENERATION:**
```json
{
  "sfx_for_generation": {
    "auto_generate": false  // صامت هنا
  },
  
  "music_for_generation": {
    "style": "final uplifting chord",
    "mood": "resolved"
  },
  
  "voiceover_optional": {
    "required": true,
    "text": "Burger House — طازج، سريع، لذيذ",
    "language": "Bahraini_Arabic",
    "voice": "male_warm",
    "timing": "throughout S4 (2s)"
  }
}
```

**Text Overlay (يُضاف في المونتاج — Sora 2 لا يدعم نصوص):**
- "Burger House"
- "يبدأ من ١.٥ د.ب"
- "#إعلان"

---

## **جدول مقارنة المولدات — Audio Capabilities**
```markdown
| المولد | توليد صوت | حوار | SFX | موسيقى | مزامنة شفاه | لهجات عربية | ملاحظات |
|--------|-----------|------|-----|--------|------------|-------------|----------|
| **Kling Wan 2.5** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | أفضل لـ UGC style |
| **Sora 2** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد جداً | سيناريوهات طويلة |
| **Veo 3** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز | ✅ جيد | احترافي |
| **Veo 3.1** | ✅ | ✅ | ✅ | ✅ | ✅ ممتاز جداً | ✅ ممتاز | أفضل جودة عربي |
| **Runway Gen-3** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | يُضاف في المونتاج |
| **Pika Labs** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | يُضاف في المونتاج |
| **Luma Dream** | ❌ | ❌ | ❌ | ❌ | N/A | N/A | يُضاف في المونتاج |
```

---

## **إرشادات الاستخدام حسب المولد**

### **🎙️ للمولدات مع توليد الصوت (Kling Wan 2.5, Sora 2, Veo 3/3.1):**
```markdown
best_practices:
  dialogue:
    - "اكتب الحوار كاملاً باللهجة المطلوبة"
    - "حدد النبرة، العاطفة، السرعة بدقة"
    - "أضف ملاحظات نطق للكلمات الصعبة"
    - "اطلب lip_sync_priority: high إذا كانت المزامنة حرجة"
  
  sfx:
    - "حدد الأصوات المطلوبة بوضوح"
    - "اذكر بيئة الصوت (quiet home / busy street)"
    - "حدد توازن الصوت (dialogue أساسي أم SFX)"
  
  music:
    - "صف الأسلوب والمزاج بوضوح"
    - "اطلب sync_with_motion: true للتزامن مع الحركة"
  
  quality_check:
    - "استمع للصوت المُولَّد — تحقق من اللهجة"
    - "إذا كانت اللهجة غير دقيقة، أعد التوليد مع ملاحظات أوضح"
    - "يمكن استبدال الموسيقى في المونتاج إن لزم"
```

### **🎬 للمولدات بدون توليد الصوت (Runway, Pika, Luma):**
```markdown
workflow:
  1. "ولّد الفيديو أولاً (صامت أو موسيقى عامة)"
  2. "سجّل الحوار بشكل منفصل (استوديو أو Elevenlabs)"
  3. "أضف SFX من مكتبة (Epidemic Sound / Freesound)"
  4. "أضف موسيقى من مكتبة (Artlist / Musicbed)"
  5. "امزج في DaVinci Resolve / Premiere Pro"
```

---

## **مخرجات JSON (محدّثة)**
```json
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
        "character": { "appearance": "...", "emotion": "frustration" },
        "sound_voice": {
          "audio_generation_supported": true,
          "dialogue_for_generation": {
            "language": "Bahraini_Arabic",
            "lines": "شنو هالبرجر الممل هذا؟",
            "voice_characteristics": {
              "gender": "male",
              "tone": "frustrated",
              "accent": "Bahraini",
              "emotion": "disappointed_annoyed"
            }
          },
          "sfx_for_generation": {
            "specific_sounds": ["bag crinkling", "sigh"]
          },
          "music_for_generation": {
            "style": "tense minor key"
          }
        }
      }
    ],
    
    "audio_generation_notes": {
      "generator": "Veo 3.1",
      "dialogue_quality": "ممتاز للهجة البحرينية",
      "lip_sync": "تلقائي",
      "post_production": "اختياري — فقط إذا احتاج تحسين"
    },
    
    "compliance": "✅",
    "veo_ready": true
  }
}
```

---

## **ملخص حالة (محدّث)**

* **ما تمّ توليده:** سيناريو Character-Based (12 ثانية) مع حوار بحريني مُولَّد مباشرة عبر Veo 3.1.
* **الامتثال:** ✅ Veo 3.1 | ✅ صوت مُولَّد | ✅ مزامنة شفاه تلقائية | ✅ إفصاح #إعلان صوتي.
* **الخطوة التالية:** رفع السيناريو لـ Veo 3.1 — الفيديو سيخرج جاهزاً بالصوت (حوار + موسيقى + SFX).

**انتهى التحديث — 08_video_scenarios.md**
