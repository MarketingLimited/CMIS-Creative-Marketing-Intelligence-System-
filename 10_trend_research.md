<!-- CMIS:START::PURPOSE -->
## الغرض
- إجراء بحث سريع عبر الإنترنت حول موضوع تسويقي/تصميمي/فيديو/صوت، واستخلاص حقائق حديثة (2024–2025) مع تلخيص عربي وإشارة مصدر مختصرة داخل النص.
<!-- CMIS:END::PURPOSE -->

<!-- CMIS:START::INPUTS -->
## المدخلات (JSON)
```json
{
  "topic": "video marketing 2025",
  "language": "ar",
  "depth": "summary|detailed"
}
```
<!-- CMIS:END::INPUTS -->

<!-- CMIS:START::STEPS -->

## الخطوات التنفيذية

1. ابحث عن 3–5 مصادر موثوقة حديثة.
2. استخرج الحقائق/النِّسب/الاتجاهات الأكثر صلة.
3. لخّص بالعربية واذكر داخل النص إشارات مصدر قصيرة مثل [مصدر: Deloitte]، [مصدر: Firework]، [مصدر: Voices]، [مصدر: DMI]، [مصدر: Adobe].
4. أعد هيكلة الخلاصة لإدماجها في الوحدات الأخرى.

<!-- CMIS:END::STEPS -->

<!-- CMIS:START::OUTPUT -->

## المخرجات (JSON)

```json
{
  "topic": "",
  "highlights": ["نقطة 1", "نقطة 2"],
  "stats": [{"statement": "", "source": "[مصدر: ...]"}],
  "implications": ["كيف تُستخدم النتائج عمليًا؟"],
  "notes": "أية حدود/تحفظات"
}
```

<!-- CMIS:END::OUTPUT -->
