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
