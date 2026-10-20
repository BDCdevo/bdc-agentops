## Agent governance

Before model selection or delegation, load the `bdc-agentops` skill and apply
its economy-first policy. The current project's product and security rules remain
authoritative.

Before substantive project inspection or tools, show the user two execution modes:
Solo with the current approved manager, and Delegated economy with every proposed
worker/model/task and relative extra usage. Recommend one and wait for an explicit
choice. Before consent, only read instruction files, locate the repository, inspect
worktree status, and perform a shallow file inventory. Do not inspect feature code,
run tests, edit files, or take external actions. Skip the question only when the
user already selected a mode for this task or no project tools are needed.

Do not use a protected, higher-cost, or unknown-cost model without first naming
the exact model and task, explaining the expected benefit and cheaper fallback,
and receiving explicit task-specific approval from the user.

Delegation consent does not approve a higher or unknown-cost model.

Default to single-agent execution. When delegation is justified, use at most two
concurrent workers, one delegation level, two attempts, and one writer per file.
Workers cannot broaden scope or perform root-only external actions.

## سياسة تحديث Press: التحديث في المكان أولًا
كل تحديث كود لتطبيق موجود على bench قائم يمر عبر In-place update في Press وفق [السياسة المركزية](https://github.com/bdcbiz/almadrasa-press-infra/blob/main/docs/ops/PRESS-UPDATE-POLICY.ar.md).
التفعيل مشروط بنجاح staging على bench-0005 ثم موقع إنتاجي واحد؛ حتى تنجح التجربتان يبقى البناء الكامل.
البناء الكامل للحالات غير المدعومة أو التي يمنعها التحفظ وفق السياسة؛ وتغييرات التبعيات تتطلب staging أولًا.
صنّف الفرق الكامل بين SHA المنشور والهدف، واحجز bench ومواقعه وموارده المشتركة في LIVE-WRITER؛ bench واحد في كل مرة.
قبل migrate: نسخة حديثة مع اختبار استرجاع معزول وفحص الأقفال؛ وثّق last-good image وdigest واحمِها من GC.
تحقق من نجاح Agent Job وتطابق hashes وصحة العمليات وsmoke tests؛ عند الفشل استعد وتحقق من قاعدة البيانات ولا تعاود قبل المراجعة.
ممنوع تعديل الكود يدويًا داخل الحاويات؛ كل دمج عبر PR ومراجعة مستقلة، بلا force-push أو --no-verify أو أسرار.
