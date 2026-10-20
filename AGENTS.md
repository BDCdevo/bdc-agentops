# AGENTS.md — BDC AgentOps repository

Read `SKILL.md` and `references/policy.md` before changing routing, approval,
delegation, permission, or usage behavior.

Repository invariants:

- Project work requiring tools must stop after shallow bootstrap and obtain an
  explicit per-task Solo or Delegated economy choice before substantive work.
- Delegation-mode consent and protected-model approval are separate decisions.
- Economy-first routing remains the default.
- Protected, higher-cost, and unknown-cost model selection requires explicit,
  task-specific user approval before execution.
- A manager may propose an escalation but may not approve its own proposal.
- Delegation never broadens the user's authority.
- Preserve deterministic validation in `scripts/validate.py` and update tests when
  intentionally changing a governed invariant.
- Do not add provider credentials, account identifiers, usage exports, or private
  project data.
- Run `python3 scripts/validate.py` and the unit tests before declaring changes
  complete.

## سياسة تحديث Press: التحديث في المكان أولًا
كل تحديث كود لتطبيق موجود على bench قائم يمر عبر In-place update في Press وفق [السياسة المركزية](https://github.com/bdcbiz/almadrasa-press-infra/blob/main/docs/ops/PRESS-UPDATE-POLICY.ar.md).
التفعيل مشروط بنجاح staging على bench-0005 ثم موقع إنتاجي واحد؛ حتى تنجح التجربتان يبقى البناء الكامل.
البناء الكامل للحالات غير المدعومة أو التي يمنعها التحفظ وفق السياسة؛ وتغييرات التبعيات تتطلب staging أولًا.
صنّف الفرق الكامل بين SHA المنشور والهدف، واحجز bench ومواقعه وموارده المشتركة في LIVE-WRITER؛ bench واحد في كل مرة.
قبل migrate: نسخة حديثة مع اختبار استرجاع معزول وفحص الأقفال؛ وثّق last-good image وdigest واحمِها من GC.
تحقق من نجاح Agent Job وتطابق hashes وصحة العمليات وsmoke tests؛ عند الفشل استعد وتحقق من قاعدة البيانات ولا تعاود قبل المراجعة.
ممنوع تعديل الكود يدويًا داخل الحاويات؛ كل دمج عبر PR ومراجعة مستقلة، بلا force-push أو --no-verify أو أسرار.
