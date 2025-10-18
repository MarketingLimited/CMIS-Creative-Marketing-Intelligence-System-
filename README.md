# CMIS — Creative Marketing Intelligence System

## نظرة عامة
CMIS هو نظام ذكاء تسويقي توليدي بُني خصيصًا لتلبية متطلبات السوق البحرينية حيث اللغة العربية (RTL) والعملة الدينار البحريني (BHD) واشتراطات الإفصاح #إعلان. يجمع النظام بين ذكاء السوق، الإقناع، اختيار الأطر، التكييف متعدد القنوات، الاختبار والتحسين، التحقق من الامتثال، ثم يولّد حزمة تسليم موحّدة تشمل إعلانات القنوات المختلفة، تقارير الامتثال، سيناريوهات الفيديو، وخطط المحتوى.
> **مهم:** استخدم الملف `instruction_prompt.md` كمرجع التشغيل الأساسي، مع الرجوع إلى `instruction_addendum_and_playbooks.md` (تقويم السوق، قوالب JSON السريعة، الإعداد المتقدم) والوحدات 01–09 للتفاصيل التخصصية.

## Getting Started
ابدأ مع CMIS عبر الخطوات التالية المصمّمة للمستخدمين الجدد. *(لا تتوفر حاليًا لقطات شاشة داخل المستودع؛ أضف صورًا إلى هذا القسم عند تجهيزها لدعم التوجّه البصري.)*

1. **استنساخ المستودع وتنظيم الملفات:**
   - نفّذ `git clone` أو حمّل الأرشيف، ثم تأكد من بقاء الملفات الرئيسة ضمن المجلد ذاته:
     - `instruction_prompt.md`
     - `instruction_addendum_and_playbooks.md` (يتضمن الوحدة 07 «Output» بالكامل)
     - ملفات الوحدات المدمجة: `01_market_intel.md`, `02_persuasion.md`, `03_frameworks.md`, `04_adaptation_distribution.md`, `05_06_testing_and_compliance.md` (Modules 05 & 06)، `08_09_video_and_content.md` (Modules 08 & 09)
2. **قراءة دليل التشغيل الأساسي:**
   - استعرض `instruction_prompt.md` لفهم التسلسل الإجرائي، ثم راجع `instruction_addendum_and_playbooks.md` لتفاصيل السوق والقوالب الجاهزة.
3. **ضبط GPT أو Gem جديد:**
   - اتّبع جدول "إعداد مخصص سريع" أدناه لنقل التعليمات إلى ChatGPT أو Gemini، مع تفعيل خيارات التصفح ورفع الملفات.
4. **تجهيز ملفات المعرفة:**
   - ارفع جميع ملفات الوحدات والملحقات في قسم *Knowledge* أو ما يعادله، مع الحفاظ على أسماء الملفات لتسهيل التحديث اللاحق.
5. **اختبار أولي:**
   - استخدم أحد *Prompt Starters* الموصى بها لتشغيل سيناريو متكامل والتأكد من أن النظام يستدعي كل وحدة بالترتيب.
6. **توثيق الملاحظات:**
   - سجّل أي مخرجات تحتاج تخصيصًا إضافيًا، ثم عدّل الملفات الداعمة (مثل `instruction_addendum_and_playbooks.md`) قبل مشاركة النسخة مع الفريق.

## دليل توجيهي مختصر
- للاطلاع على التسلسل التشغيلي الكامل انتقل إلى [`instruction_prompt.md`](instruction_prompt.md) بوصفه مصدر الحقيقة اليومي.
- للحصول على القوالب المتقدمة وسيناريوهات الاستخدام، راجع [`instruction_addendum_and_playbooks.md`](instruction_addendum_and_playbooks.md) (يتضمن محتوى الملحق وPlaybooks المتقدمة في ملف موحّد، إضافة إلى الوحدة 07).
- إذا احتجت الوحدات المتخصصة، فاعتمد التوزيع الموحّد الحالي: ملفات منفصلة للوحدات 01–04، ملف مشترك للوحدتين 05 و06 (`05_06_testing_and_compliance.md`)، ملف مشترك للوحدتين 08 و09 (`08_09_video_and_content.md`)، بينما الوحدة 07 («Output») مستقرة داخل `instruction_addendum_and_playbooks.md` §MODULE_07_OUTPUT.
- يظل هذا README المرجع التوجيهي الحي؛ بعد دمج الملفات القديمة أُعيد تنظيم المحتوى داخل الأقسام الحالية الموضحة أعلاه.

## المتطلبات المسبقة
- حساب ChatGPT يتيح إنشاء GPTs مخصصة.
- حساب Gemini (AI Studio) يتيح إنشاء Gems مخصصة.
- الوصول إلى ملفات المشروع محليًا أو عبر Git لتغذية النموذج بالمعرفة.
- استخدام نماذج **GPT-5** و **Gemini 2.5** مع تمكين الوصول إلى الإنترنت.

## إعداد مخصص سريع: ChatGPT GPT مقابل Gemini Gem
| الخطوة | ChatGPT GPT | Gemini Gem |
| --- | --- | --- |
| 1 | ادخل إلى **ChatGPT → Explore → Create a GPT** واختر خيار البدء من الصفر. | افتح **Gemini AI Studio → Create a new Gem** وعيّن اسمًا واضحًا (مثال: CMIS Bahrain). |
| 2 | في تبويب **Instructions** الصق نسخة `instruction_prompt.md` الكاملة لضبط السلوك الأساسي. | في حقل **System Instruction** الصق المحتوى العربي لـ `instruction_prompt.md` للتأكد من اتباع تسلسل الوحدات. |
| 3 | ضمن **Knowledge** ارفع الملفات: `instruction_prompt.md`, `instruction_addendum_and_playbooks.md` (بما فيها الوحدة 07)، `01_market_intel.md`, `02_persuasion.md`, `03_frameworks.md`, `04_adaptation_distribution.md`, `05_06_testing_and_compliance.md`, `08_09_video_and_content.md`. | في قسم **Knowledge/References** ارفع الملفات نفسها وتأكد من تفعيل استخدامها في كل جلسة. |
| 4 | حدّث خانة **Profile → Description/Goal** لتعكس وضع التشغيل (مثل: `full_strategy` أو `quick_draft`). | استخدم حقل **Goal** المدمج لتحديد الوضع الافتراضي (مثال: `full_strategy`) ويمكن إنشاء أهداف إضافية لكل سيناريو. |
| 5 | أضف **Prompt Starters** من القوالب أدناه بحسب القناة لإرشاد المستخدمين الجدد. | أضف **Prompt Starters** في تبويب القنوات وحدد اللغة العربية المحلية لضمان المخرجات المناسبة. |
| 6 | فعّل قدرات **Web Browsing** و **File Upload** لضمان الوصول للإنترنت واستقبال مرفقات العملاء. | فعّل خيارات **Web Access** و **File Handling**، وحدد تنسيقات الإخراج المفضلة (JSON، نص) لكل هدف. |

### ضبط Knowledge وGoal وPrompt Starters لكل منصة
#### ChatGPT GPT
1. بعد رفع ملفات المعرفة، استخدم خيار **Replace** بدلًا من **Add** عند تحديث أي ملف لضمان مزامنة النسخة الأحدث.
2. في قسم **Goal** (الوصف القصير)، استخدم صيغة مثل: `full_strategy → تنفيذ كل الوحدات حتى Output.` ويمكن إنشاء هدف ثانوي `quick_draft → تلخيص السوق والإعلان فقط` لتبديله يدويًا عند الحاجة.
3. ضمن **Prompt Starters** أدرج قوالب القنوات، واحرص على إضافة أيقونة أو إيموجي بسيط لتمييز كل قناة (مثال: "📣 حملة Meta..."), ما يسهل على المستخدمين الاختيار السريع.

#### Gemini Gem
1. بعد رفع الملفات، استخدم زر **Sync to Gem** لضمان توافرها في وضع الإنتاج، ثم اختبر الاستدعاء بطرح سؤال تحقق قصير (مثل: "ما ترتيب وحدات CMIS؟").
2. فعّل خيار **Response Style → JSON** عندما تكون مخرجات CMIS مطلوبة بصيغة موحدة، واحتفظ بنسخة ثانية من الهدف `analysis_only` لإجابات تفسيرية.
3. أنشئ مجموعات **Prompt Starters** منفصلة لكل هدف (Full Strategy، Quick Draft، Compliance Only) بحيث يتم تحميل القالب المناسب تلقائيًا عند تغيير الهدف.

### قوالب Prompt Starters حسب القناة (لهجة خليجية بحرينية)
| القناة | قالب Prompt Starter |
| --- | --- |
| Meta | "📣 نبي حملة Meta لعلامة [اسم العلامة] داخل البحرين. عطنا نسخ RTL مع ذكر #إعلان، واستهدف العوائل اللي تصرف حدود 250 BHD شهريًا." |
| Google_RSA | "🔍 حضّر إعلانات Google RSA لباقات [الخدمة]، ركّز على كلمات البحث اللي يستخدمونها أهل البحرين وقت العروض، وخل الـ CTA يوجّه لصفحة هبوط عربية." |
| TikTok | "🎬 سوّي لنا سيناريو TikTok UGC قصير عن [المنتج] مع لهجة بحرينية خفيفة، واذكر هاشتاق #إعلان بالبداية." |
| LinkedIn | "💼 جهّز نسخة LinkedIn Ads موجهة لمدراء التسويق في البحرين عن [الحل]، ووضّح القيمة المهنية بلغة رسمية محلية." |
| Email | "✉️ أرسل سلسلة Emails بثلاث خطوات لمشتركين جدد في [الخدمة]، خلي التحية بحرينية ودلّل على العروض بالدينار." |
| WhatsApp_SMS | "📱 نحتاج رسائل WhatsApp/SMS سريعة لجمهور بحريني عن [العرض]، تضمّن #إعلان وتعليمات إلغاء الاشتراك." |
| OOH | "🛣 خطط محتوى لوحات OOH في المنامة عن [الحملة]، مع شعارات قصيرة تنقري من السيارة وتذكر الأسعار بالدينار." |
| Landing Page | "🌐 بنسوي صفحة هبوط لـ [الخدمة] بالعربي البحريني، عطنا العناوين، الأقسام، ونص CTA واضح مع إثبات اجتماعي محلي." |

## مقارنة تشغيلية بين ChatGPT وGemini
| البند | ChatGPT GPT | Gemini Gem |
| --- | --- | --- |
| رفع الملفات | يدعم حتى 20 ملفًا لكل GPT (بحد أقصى ~512MB لكل ملف) ويمكن استبدال الملفات لاحقًا. | يدعم مرفقات متعددة لكل Gem مع حد حجمي إجمالي ~100MB للجلسة، ويتطلب إعادة المزامنة بعد كل تحديث. |
| حجم المعرفة المدعوم | يعتمد على حد الملفات المذكور؛ يمكن تقسيم الملفات الكبيرة إلى وحدات أصغر لتسريع الاسترجاع. | يقبل ملاحظات نصية أطول في **Knowledge Cards**، لكن يُفضَّل الحفاظ على كل ملف <25MB لتفادي أخطاء الرفع. |
| دعم JSON | وضع **Structured Output/JSON** متاح عبر Response Format ويضمن الالتزام بمخططات CMIS. | يمكن فرض نمط JSON بالكامل وتحديد الحقول المطلوبة داخل الهدف لضمان التحقق المسبق. |
| إمكانيات الإنترنت | يتطلب تفعيل **Web Browsing** لكل GPT مخصص؛ يعتمد على سياسة OpenAI الحالية. | خيار **Web Access** متاح لكل هدف، ويمكن تقييده أو فتحه حسب الحاجة مع سجل استدعاءات مفصل. |

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

<!-- CMIS:START::README_CHATGPT_KNOWLEDGE -->
3. ضمن **Knowledge** (المرفقات) قم بتحميل `instruction_prompt.md` (البرومبت الرسمي المختصر)، `instruction_addendum_and_playbooks.md` (التفاصيل التكميلية + الوحدة 07)، وملفات الوحدات المتاحة (`01_market_intel.md`, `02_persuasion.md`, `03_frameworks.md`, `04_adaptation_distribution.md`, `05_06_testing_and_compliance.md`, `08_09_video_and_content.md`).
<!-- CMIS:END::README_CHATGPT_KNOWLEDGE -->
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

<!-- CMIS:START::README_GEMINI_KNOWLEDGE -->
3. أرفق ملفات المعرفة `instruction_prompt.md`، `instruction_addendum_and_playbooks.md` (متضمنة الوحدة 07)، ووثائق الوحدات المدمجة (`01_market_intel.md`, `02_persuasion.md`, `03_frameworks.md`, `04_adaptation_distribution.md`, `05_06_testing_and_compliance.md`, `08_09_video_and_content.md`) في خانة Knowledge أو References.
<!-- CMIS:END::README_GEMINI_KNOWLEDGE -->
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

## إدارة الإصدارات والمراجعة الدورية
### منهجية الترقيم
- اعتمد نظام **Semantic Versioning (SemVer)** بصيغة `MAJOR.MINOR.PATCH` لجميع ملفات التشغيل (`instruction_prompt.md`, `instruction_addendum_and_playbooks.md`, وحدات 01–09، وأي قوالب JSON).
- زد رقم **MAJOR** عند إجراء تغييرات جوهرية تغيّر تدفق العمل أو تتطلب إعادة تدريب المستخدمين.
- زد رقم **MINOR** عندما تضيف وحدات أو قدرات جديدة بدون كسر التوافق مع أسلوب العمل الحالي.
- استخدم رقم **PATCH** للتنقيحات الصغرى (تصحيح أخطاء، تحسينات لغوية، تحديثات امتثال) التي لا تستلزم تغييرًا في إجراءات التشغيل.
- دوّن رقم الإصدار داخل رأس الملفات الرئيسية وعند نشر نسخة جديدة في سجل التغييرات أدناه.

### دورة مراجعة ربع سنوية
1. حدّد بداية كل ربع سنة في تقويم العمليات وعيّن مالكًا مسؤولًا عن المراجعة.
2. اجمع ملاحظات فرق التسويق، الامتثال، وأصحاب المصلحة حول دقة المخرجات خلال الربع المنصرم.
3. راجع المقاييس الأساسية (دقّة الامتثال، معدل قبول الحملات، زمن التنفيذ) لرصد أي تراجع يستدعي تحديث البرومبتات.
4. حدّث `instruction_prompt.md` و `instruction_addendum_and_playbooks.md` بما يلزم، ثم أعد اختبار سيناريوهين قياسيين (حملة متكاملة + مراجعة امتثال فقط) للتأكد من الاستقرار.
5. وثّق النتائج والإصدار الجديد، وشارك ملخصًا بالتحديثات في قنوات الاتصال الداخلية.

### قائمة تحقق لتقييم تحديث البرومبتات
- ☐ هل ظهرت لوائح أو متطلبات إفصاح جديدة (#إعلان، خصوصية، بيانات) منذ آخر مراجعة؟
- ☐ هل تغيّرت استراتيجيات القنوات أو حدودها (مثل دعم صيغ فيديو جديدة أو متطلبات RTL)؟
- ☐ هل لوحظت فجوات في مخرجات النبرة أو الدقة الثقافية بناءً على تعليقات المستخدمين؟
- ☐ هل أضيفت منتجات/خدمات أو قطاعات جديدة تتطلب توسيع أمثلة الأطر أو القوالب؟
- ☐ هل تم تحديث أي مخططات JSON أو واجهات استيراد/تصدير يجب أن تنعكس في الملفات المرجعية؟
- ☐ هل طول `instruction_prompt.md` ما يزال تحت حد 8,000 حرف بعد التعديلات؟

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
- `instruction_addendum_and_playbooks.md` — تفاصيل تشغيل عامة ومراجع Parsing/Config (وتضمين كامل للوحدة 07: OUTPUT).
<!-- CMIS:START::README_FILE_LIST -->
- ملفات المعرفة المتخصصة حسب التوزيع الحالي: `01_market_intel.md`, `02_persuasion.md`, `03_frameworks.md`, `04_adaptation_distribution.md`, `05_06_testing_and_compliance.md` (MODULE_05 + MODULE_06)، `08_09_video_and_content.md` (MODULE_08 + MODULE_09).
<!-- CMIS:END::README_FILE_LIST -->
- ملف `support_and_templates.md §OPERATIONS_AND_SUPPORT` القديم مؤرشف ويخص نسخة سابقة؛ هذا README هو مصدر الحقيقة الحالي.

## خارطة طريق / مساهمة
- افتح قضية (Issue) لأي تحسين مقترح، واشرح السياق والملفات المتأثرة.
- أنشئ فرعًا جديدًا، نفّذ التعديلات مع اختبارات أو أمثلة محدثة، ثم أرسل Pull Request موثقًا يتبع قالب المشروع.

## الترخيص والدعم
- راجع ملف الترخيص في المستودع (إن وُجد) قبل الاستخدام التجاري. في حال غيابه، اعتبر الحقوق محفوظة للفريق المالِك.
- للدعم أو الاستفسارات، استخدم قنوات الاتصال الداخلية أو البريد المحدد من قبل فريق MarketingLimited.

<!-- CMIS:START::READMEA_REFERENCES_2025 -->
## ملفات مهمة
support_and_templates.md §USER_AND_TRAINING_GUIDES · support_and_templates.md §USER_AND_TRAINING_GUIDES · support_and_templates.md §QUALITY_AND_VARIATIONS · support_and_templates.md §USER_AND_TRAINING_GUIDES · support_and_templates.md §USER_AND_TRAINING_GUIDES · support_and_templates.md §OPERATIONS_AND_SUPPORT · support_and_templates.md §OPERATIONS_AND_SUPPORT
<!-- CMIS:END::READMEA_REFERENCES_2025 -->
