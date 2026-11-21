# دليل Git

النسخة الإنجليزية هي المرجع الأساسي: [GIT_GUIDE.md](GIT_GUIDE.md).

## اللغة

تستخدم وثائق المستودعات الإنجليزية أو العربية فقط. الإنجليزية هي المصدر المعتمد، والعربية تعكسها. لا تضف لغات أخرى.

## الفروع

`main` هو الفرع الوحيد طويل الأمد. اعمل في فرع قصير وافتح طلب سحب.

```bash
git switch -c fix/winget-cache
git add .
git commit
git push -u origin fix/winget-cache
```

احذف الفرع بعد الدمج بأسلوب squash.

## الالتزامات

استخدم عنواناً مختصراً بأسلوب Conventional Commit:

```text
feat(sway): add greetd autologin toggle
fix(iot): handle missing winget cache
docs: standardize repo health files
chore: add gitattributes
ci: add read-only validation
security: enable push protection
```

القواعد:

- الالتزام الواحد يمثل فكرة كاملة واحدة.
- العنوان قصير وأمري ولا ينتهي بنقطة.
- النص يشرح سبب التغيير.
- لا تعِد كتابة تاريخ مدفوع. استخدم `git revert`.
- أعد التأسيس (rebase) للفروع المحلية فقط.

## طلبات السحب

- اذكر ما تغيّر ولماذا.
- اجعل التغيير مركّزاً.
- اترك الفحوصات الأربعة للقراءة فقط تنجح: shell وPowerShell والبيانات والوثائق.
- استخدم دمج squash. التاريخ الخطي يجعل التراجع بسيطاً.

لا توجد اختبارات. التحقق يعني محللات الصياغة وفحوصات الصيغة ونقطة التحقق الحالية في المستودع للقراءة فقط مثل `Verify` أو `-Verify` أو `Validate.ps1` أو `run.sh --verify`.

## الإعداد المحلي

```bash
git config --global user.name "SOSMLG"
git config --global user.email "$(gh api user --jq .id)+SOSMLG@users.noreply.github.com"
git config --global init.defaultBranch main
git config --global pull.rebase true
git config --global core.autocrlf false
git config --global core.quotepath false
git config --global fetch.prune true
git config --global push.autoSetupRemote true
```

Windows PowerShell 5.1 يقرأ UTF-8 بدون BOM كـ ANSI. أبقِ ملفات `.ps1` بـ ASCII.

## قبل الدفع

```bash
git diff --check
bash -n path/to/script.sh
./run.sh --verify    # حيث يوجد
```

على Windows:

```powershell
.\Validate.ps1 -Profile daily
.\install-Win-Iot.ps1 -DryRun
```

ابلّغ فقط عمّا نفّذته فعلاً. إن تعذّر فحص على الجهاز، قل ذلك.

## الإصدارات

- `CHANGELOG.md` يتبع Keep a Changelog مع قسم `Unreleased`.
- الإصدارات تتبع SemVer.
- `fix` تعني patch، و`feat` تعني minor، و`BREAKING CHANGE` تعني major.
- الوسوم annotated وتُدفع بعد تنظيم سجل التغيير.

## الأمان

- تبقى الأسرار في البيئة أو في GitHub Secrets.
- لا تضف مفاتيح أو كلمات مرور أو رموزاً إلى المستودع.
- أبلغ عن الثغرات عبر تبويب Security لا عبر issue عام.
- يبقى Microsoft Defender كما هو. لا تكتب أي سكربت إعداداته.
