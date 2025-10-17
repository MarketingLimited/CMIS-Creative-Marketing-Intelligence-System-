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

## تغييرات إلزامية للثلاثة الرئيسيين
- v1: Pain-focused — **PAS** — زاوية الخسارة — نبرة عاجلة.
- v2: Benefit-focused — **AIDA** — زاوية القيمة — نبرة إيجابية.
- v3: Proof-focused — **FAB/4U** — زاوية الدليل — نبرة واثقة.
- أضف اختلافًا صوتيًا على الأقل في أحد التنويعات (لهجة/موسيقى/إيقاع).
- أضف اختلافًا مجتمعيًا: قصة موظف (EGC) مقابل شهادة عميل (UGC).
- أضف اختلافًا تفاعليًا: CTA مباشر مقابل سؤال/استطلاع.
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
```

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
