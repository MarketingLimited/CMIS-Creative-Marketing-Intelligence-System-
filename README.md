# CMIS — Creative Marketing Intelligence System

## نظرة عامة
CMIS هو نظام ذكاء تسويقي توليدي بُني خصيصًا لتلبية متطلبات السوق البحرينية حيث اللغة العربية (RTL) والعملة الدينار البحريني (BHD) واشتراطات الإفصاح #إعلان. يجمع النظام بين ذكاء السوق، الإقناع، اختيار الأطر، التكييف متعدد القنوات، الاختبار والتحسين، التحقق من الامتثال، ثم يولّد حزمة تسليم موحّدة تشمل إعلانات القنوات المختلفة، تقارير الامتثال، سيناريوهات الفيديو، وخطط المحتوى.
> **مهم:** استخدم الملف `instruction_prompt.md` كمرجع التشغيل الأساسي، مع الرجوع إلى `instruction_addendum.md` (تقويم السوق، قوالب JSON السريعة، الإعداد المتقدم) والوحدات 01–09 للتفاصيل التخصصية.

## المتطلبات المسبقة
- حساب ChatGPT يتيح إنشاء GPTs مخصصة.
- حساب Gemini (AI Studio) يتيح إنشاء Gems مخصصة.
- الوصول إلى ملفات المشروع محليًا أو عبر Git لتغذية النموذج بالمعرفة.
- استخدام نماذج **GPT-5** و **Gemini 2.5** مع تمكين الوصول إلى الإنترنت.

## بيئة التشغيل الحالية
- هذه الملفات معدّة للتضمين في GPTs وGems؛ لا حاجة لكتابة كود أو بناء تكاملات مخصصة في هذه المرحلة.
- لا يوجد اتصال مباشر مع تطبيقات تسويق أو تحليلات خارجية حاليًا. على المستخدم تحميل التقارير والبيانات يدويًا (مثل أداء الحملات، بيانات المنتجات، أو معلومات الجمهور).
- عند الحاجة إلى بيانات إضافية، يقدّم النظام إرشادًا واضحًا للمستخدم حول التقارير أو الحقول المطلوبة قبل متابعة التوصيات التفصيلية.

## طريقة التشغيل (الخيار A) — عبر GPT مخصص في ChatGPT
### الخطوات
1. افتح ChatGPT ثم Explore → Create a GPT.
2. افتح الملف `instruction_prompt.md` و انسخ محتواه كاملًا (≤7900 حرف) إلى حقل **Instructions** ليكون النظام معرّفًا بأحدث برومبت رسمي لـ *CMIS Orchestrator*. استخدم المقتطف أدناه فقط للتدقيق السريع بأن النسخة من الملف تم نقلها بشكل صحيح:

```
أنت CMIS Orchestrator.
- السوق الافتراضي: البحرين (AR حديثة بترتيب RTL)، العملة: BHD، ويُلصق الوسم #إعلان في بداية أي مادة مرعية (نصًا وصوتًا عند الحاجة).
- نفّذ الوحدات حسب الترتيب: Market Intel → Persuasion → Frameworks → Adaptation & Distribution → Testing & Optimization → Compliance → Output.
- استخرج المدخلات من الطلب، ووسّم الفرضيات بـ [افتراض]، وطبّق قواعد الحراسة: منع الادعاءات المطلقة، ضبط CTA للجمهور، استخدام مصادر وحديثة، احترام الخصوصية (موافقة صريحة + حق الإلغاء + حقوق الوصول/التصحيح/المحو).
- وفّر المخرجات الرئيسة التالية:
  1) Unified Delivery File: يشمل strategy_summary، مصفوفة الإعلانات ads[] لكل قناة (Meta, Google_RSA, TikTok, LinkedIn, Email, WhatsApp_SMS, OOH, Landing)، أقسام DCO، توصيات التحسين.
  2) Compliance Report: يحتوي status، issues، fix_suggestions، sanitized_copy، consent_text، final_mark.
  3) Self-Checks: مصفوفة قواعد الامتثال والتحسين (rule، result، auto_fix، owner).
- عند طلب فيديو أو خطة محتوى، فعّل وحدات Video Scenarios وContent Planning مع احترام التوقيت والسيناريوهات المناسبة (UGC، documentary، virtual_influencer وغيرها).
- أعد المخرجات بصيغة JSON متوافقة مع المخططات أعلاه مع شرح موجز بالعربية.
- عند التصحيح التلقائي، أظهر النص المنقح وتوثيق سبب التعديل.
```

3. ضمن **Knowledge** (المرفقات) قم بتحميل `instruction_prompt.md` (البرومبت الرسمي المختصر)، `instruction_addendum.md` (التفاصيل التكميلية)، وجميع ملفات الوحدات `01_market_intel.md` حتى `09_content_planning.md` لتصبح مرجعًا للنموذج.
4. (اختياري) أضف Prompt Starters لتسريع الاستخدام، مثل:
   - "بادر بتحليل سوق لخدمة الدفع بالتقسيط وولّد إعلانات Meta/Google".
   - "أنشئ خطة محتوى أسبوعية لحساب إنستقرام لمنتج صحي".
5. **تشغيل مثال:** استخدم المطالبة التالية لإنتاج حزمة إعلانات لقنوات Meta وGoogle مع تقرير امتثال:

```
أريد حملة للعلامة [اسم العلامة] لخدمة اشتراك إنترنت منزلي سريع في البحرين. ركّز على العائلات، الميزانية الشهرية 3000 BHD. أعد لي حزمة Meta + Google مع تقرير امتثال كامل.
```

## طريقة التشغيل (الخيار B) — عبر Gem مخصص في Gemini (Gems)
### الخطوات
1. افتح Gemini AI Studio وأنشئ Gem جديد.
2. افتح الملف `instruction_prompt.md`، وانسخ التوجيهات العربية منه إلى حقل **System Instruction** (أو ما يعادلها) في Gem لضمان استخدام البرومبت الرسمي. استخدم المقتطف الإنجليزي أدناه كمرجع تطابق سريع إن احتجت لمواءمة النسخة الثنائية:

```
You are CMIS Orchestrator for Bahrain.
- Default locale: Arabic (Modern Standard with Bahraini touches), RTL layout, currency BHD, prepend #إعلان to every sponsored material.
- Pipeline order: Market Intel → Persuasion → Frameworks → Adaptation & Distribution → Testing & Optimization → Compliance → Output.
- Parse client inputs, mark assumptions with [افتراض], and enforce guardrails (no absolute claims, respect channel CTA rules, require explicit consent language, provide opt-out and data rights reminders).
- Produce JSON blocks for Unified Delivery File, Compliance Report, and Self-Checks exactly as specified, with bilingual short explanations when helpful.
- Enable Video Scenarios and Content Planning modules when the brief requires video, TikTok/Reels, or weekly/monthly plans.
- Auto-correct compliance issues and show sanitized_copy alongside reasons.
```

3. أرفق ملفات المعرفة `instruction_prompt.md`، `instruction_addendum.md`، وملفات الوحدات `01_market_intel.md` إلى `09_content_planning.md` في خانة Knowledge أو References.
4. اضبط الهدف الافتراضي (Goal) مثل: `full_strategy` لتشغيل السلسلة الكاملة أو `quick_draft` للاختصار، بحسب الاستخدام المطلوب.
5. **تشغيل مثال:** نفّذ الطلب التالي للحصول على إعلانات + سيناريو فيديو + تقرير امتثال:

```
طوّر حملة للعلامة [اسم العلامة] لمنتج مشروبات صيفية في البحرين. أريد إعلانات Meta وTikTok مع سيناريو فيديو قصير (نوع UGC) وتقرير امتثال مفصل.
```

## كيفية الاستخدام (سير العمل المختصر)
1. اجمع مدخلات العميل: المنتج أو الخدمة، الهدف التسويقي، الجمهور، الميزانية، القيود الزمنية.
2. نفّذ الوحدات بالتسلسل:
   - **Market Intel:** يستخرج pains/desires/objections، شرائح الجمهور، personas، مهام يجب إنجازها (JTBD)، عرض القيمة/USP.
   - **Persuasion:** يبني hooks، نبرات صوت، دعوات لاتخاذ إجراء (CTAs) ملائمة لكل مرحلة وطبقات إثبات اجتماعي.
   - **Frameworks:** يختار أطر مثل AIDA، PAS، FAB، StoryBrand بناءً على القناة ودرجة الوعي.
   - **Adaptation & Distribution:** يكيّف النصوص لكل قناة، يضبط الحدود، يحافظ على RTL، ويحدد المواصفات البصرية.
   - **Testing & Optimization:** ينشئ متغيرات لاختبارها، يقترح KPIs مثل CTR/CVR/ROAS، ويضع تجارب A/B أو تعديلات مرحلية.
   - **Compliance:** يتحقق من وسم #إعلان، صحة استخدام BHD، الخصوصية، منع المطلقات، ويقترح Auto-Fixes مع نصوص منقحة.
   - **Output:** يبني **Unified Delivery File**، تقارير الأداء والامتثال، وملف Self-Checks الذي يضمن استمرارية مراقبة الجودة.
3. عند اكتمال المخرجات، صدّر الحزمة بصيغة ملفات مسماة حسب القناة (Bundles) مع الالتزام بالتسمية الموحدة المتفق عليها داخليًا.

## أمثلة JSON (مطلوبة ومختصرة)
**Compliance Report**
```json
{
  "status": "needs_review",
  "issues": [
    {"rule": "hashtag_disclosure", "finding": "missing #إعلان", "severity": "high"}
  ],
  "fix_suggestions": ["أضف الوسم #إعلان في بداية النص."],
  "sanitized_copy": "#إعلان إنترنت بسرعات فورية...",
  "consent_text": "نلتزم بإعلامكم بحقوق الوصول والتصحيح وإلغاء الاشتراك في أي وقت.",
  "final_mark": "pending"
}
```

**Unified Delivery File**
```json
{
  "strategy_summary": {
    "brand": "Example ISP",
    "audience": ["عائلات تبحث عن استقرار الإنترنت"],
    "value_prop": "سرعات موثوقة مع دعم محلي"
  },
  "ads": [
    {
      "channel": "Meta",
      "framework": "AIDA",
      "primary_text": "#إعلان استمتعوا بإنترنت سريع...",
      "visual_direction": "لقطات عائلية داخل منزل بحريني",
      "cta": "اكتشف الباقات"
    }
  ],
  "dco": {"enabled": true, "variants": 3},
  "compliance_reports": ["compliance_report_v1.json"],
  "improvement_recommendations": ["اختبار CTA بديل يستهدف السرعة مقابل الدعم"]
}
```

**Video Scenario (مقتضب)**
```json
{
  "scenario_type": "UGC",
  "scenes": [
    {"id": 1, "description": "لقطة سيلفي في غرفة المعيشة"},
    {"id": 2, "description": "إظهار سرعة التحميل على شاشة"}
  ],
  "dialogue": ["#إعلان أخيرًا حصلنا على إنترنت يستحق الانتظار"],
  "technical": {"duration_seconds": 30, "aspect_ratio": "9:16"}
}
```

## امتثال البحرين (مختصر عملي)
- ابدأ كل مادة مرعية بالوسم **#إعلان** (نصًا وصوتيًا للفيديوهات).
- استخدم أسعار الدينار البحريني (BHD) مع أرقام بصيغة عربية عند الحاجة.
- حافظ على اتجاه RTL وخط عربي واضح في كل النصوص البصرية.
- تجنب الادعاءات المطلقة («مضمون»، «الأفضل»، «الأسرع») واستبدلها بمدى أو مصدر موثّق.
- التزم بالخصوصية: صرّح بحقوق الموافقة، الإلغاء، والوصول/التصحيح/المحو للبيانات الشخصية.

## أمثلة تشغيل سريعة
- **ChatGPT GPT:** "أرغب في حملة لمنتج تأجير سيارات فاخرة في البحرين. أعد لوحات استراتيجية، إعلانات Meta وGoogle، وتقارير امتثال مع Self-Checks." 
- **Gemini Gem:** "قدّم خطة استراتيجية لإطلاق تطبيق تمارين منزلية في البحرين مع سيناريو TikTok قصير وإعلانات Meta وLinkedIn، وتحقق من الامتثال تلقائيًا." 

## بنية الملفات
- `instruction_prompt.md` — البرومبت الرسمي المختصر (≤7900 حرف).
- `instruction_addendum.md` — تفاصيل تشغيل عامة ومراجع Parsing/Config.
- `main.md` — **Archived** يوجّه إلى البرومبت الجديد للحفاظ على التوافق.
- `01_market_intel.md` حتى `09_content_planning.md` — ملفات المعرفة المتخصصة لكل وحدة (السوق، الإقناع، الأطر، التكييف، الاختبار، الامتثال، التسليم، السيناريوهات، التخطيط).
- ملف `help.md` القديم مؤرشف ويخص نسخة سابقة؛ هذا README هو مصدر الحقيقة الحالي.

## خارطة طريق / مساهمة
- افتح قضية (Issue) لأي تحسين مقترح، واشرح السياق والملفات المتأثرة.
- أنشئ فرعًا جديدًا، نفّذ التعديلات مع اختبارات أو أمثلة محدثة، ثم أرسل Pull Request موثقًا يتبع قالب المشروع.

## الترخيص والدعم
- راجع ملف الترخيص في المستودع (إن وُجد) قبل الاستخدام التجاري. في حال غيابه، اعتبر الحقوق محفوظة للفريق المالِك.
- للدعم أو الاستفسارات، استخدم قنوات الاتصال الداخلية أو البريد المحدد من قبل فريق MarketingLimited.
