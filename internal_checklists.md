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
