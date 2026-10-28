# ملف المشروع | Project Profile

## العربية

### الغرض المدعوم بالأدلة
هذا المستودع نسخة ويب ثابتة، مكتوبة بالعربية وذات اتجاه RTL، لموقع تعريفي/تسويقي لعلامة ZMRT. توصف الصفحة الرئيسية في `index.html` كصفحة لسياسة الخصوصية، بينما يعرّف `README.md` نطاق التسليم المقصود بأنه صفحات الرئيسية والخصوصية والشروط وحذف الحساب والدعم و404. لذلك لا يمكن تأكيد أن محتوى المستودع الحالي يطابق هذا النطاق كاملًا: شجرة الملفات المتتبعة لا تحتوي إلا على سبعة ملفات في الجذر، ولا توجد مجلدات تلك الصفحات. النصوص في `README.md` و`index.html` تصف تطبيقًا للتواصل والمكالمات الصوتية والمرئية؛ هذه أوصاف لمحتوى الموقع وليست تحققًا مستقلًا من وظائف تطبيق فعلي.

### المكوّنات والتدفقات الأساسية
- `index.html`: مستند HTML عربي باتجاه RTL، يتضمن روابط الأصول المشتركة ويمثل في نسخته الحالية صفحة الخصوصية ومسودة قانونية. تشير الروابط فيه إلى `privacy/` و`terms/` و`delete-account/` و`support/`، لكن هذه الصفحات غير موجودة في الشجرة الحالية.
- `app.js`: JavaScript دون إطار عمل. يفتح/يغلق قائمة الهاتف، ويغلقها عند اختيار رابط أو ضغط Escape، ويضبط روابط التنزيل والدعم اعتمادًا على `window.ZMRT_CONFIG`.
- `styles.css`: تنسيقات الموقع المتجاوبة، بما فيها قواعد الشاشات الصغيرة والحركة المخفّضة.
- `404.html`: صفحة خطأ مستقلة، و`favicon.svg`: أيقونة الموقع، و`robots.txt`: يمنع الزحف لجميع الوكلاء (`Disallow: /`).

تدفق التهيئة المقصود في `app.js` يقرأ `GOOGLE_PLAY_URL` و`SUPPORT_EMAIL` من `window.ZMRT_CONFIG`، ويتحقق من أن رابط المتجر HTTPS على `play.google.com/store/apps/details` ويتضمن `id`، أو أن البريد يبدو صالحًا، قبل تفعيل الروابط. لكن الملفات المتتبعة لا تتضمن `config.js` رغم أن `index.html` و`404.html` يشيران إليه؛ لذلك لا يمكن تأكيد وجود إعداد فعّال في المستودع الحالي.

### شجرة مختصرة للملفات المهمة
```text
.
├── 404.html       صفحة غير موجودة؛ تستورد CSS وJavaScript وتهيئة المشار إليها
├── README.md      وصف النطاق وطريقة الفتح وإرشادات التهيئة والجودة
├── app.js         سلوك قائمة التنقل وروابط التنزيل والدعم
├── favicon.svg    أيقونة SVG
├── index.html     وثيقة HTML عربية حالية لسياسة الخصوصية
├── robots.txt     يمنع الفهرسة والزحف
└── styles.css     تنسيقات RTL المتجاوبة والحركة
```

### التقنية والإعداد والتشغيل والاختبار
بحسب `README.md` والملفات الفعلية، المشروع HTML/CSS/JavaScript ثابت بلا إطار عمل أو تبعيات بناء معلنة. لا يوجد `package.json` أو ملف قفل أو manifest أو إعداد بناء/اختبار أو CI متتبع؛ لذلك لا توجد إصدارات أدوات أو تبعيات يمكن توثيقها، ولا أوامر بناء أو اختبار مستنتجة. يذكر README فتح `index.html` مباشرة بعد استخراج الأرشيف، ويذكر استضافة ثابتة واعية بملفات `index.html` داخل المجلدات للحصول على المسارات النظيفة `/privacy` و`/terms`؛ لكن المجلدات غير موجودة حاليًا.

يسرد README أسماء مفاتيح الإعداد المقترحة التالية دون قيم: `GOOGLE_PLAY_URL`، `SUPPORT_EMAIL`، `DEVELOPER_NAME`، `SITE_URL`، `LEGAL_APPROVED`. يظهر استعمال المفتاحين الأولين في `app.js`، أما الثلاثة الأخرى فمذكورة في README فقط ولا يظهر استعمالها ضمن الملفات المتتبعة. لا توجد قيم إعدادات أو أسرار موثقة هنا.

### نقاط عملية لمطور جديد وغير محسومة
ابدأ بمقارنة قائمة الملفات الفعلية مع النطاق الموصوف في `README.md`، وتحقق من وجود صفحات الخصوصية والشروط وحذف الحساب والدعم وإعداد `config.js` قبل اعتبار الروابط أو التهيئة مكتملة. يذكر README صراحة أن مواد الصفحات القانونية مسودات غير معتمدة، وأن صندوق الدعم ورابط Google Play واسم المطور والنطاق وحالة الموافقة القانونية تحتاج تحققًا/تهيئة؛ كما يذكر أن الدعم عبر `mailto` لا ينفذ حذف الحساب. يوصي README بفحوص يدوية عند 360 و768 و1440 بكسل، والتنقل بلوحة المفاتيح والحركة المخفّضة، لكنه لا يورد نتائج تشغيل لهذه الفحوص في المستودع الحالي. لا توجد اختبارات آلية أو CI ظاهرة. يحظر `robots.txt` الزحف، وتستخدم صفحات HTML بيانات `noindex,nofollow`؛ لا ينبغي إزالة ذلك أو نشر الموقع قبل اعتماد المحتوى والتحقق من النطاق الفعلي. لا يثبت المستودع وحده تفاصيل backend أو سلوك التطبيق المحمول أو صحة البيانات القانونية.

## English

### Evidence-supported purpose
This repository is a static, Arabic, right-to-left web version for a ZMRT informational/marketing site. The current `index.html` is a privacy-policy page, while `README.md` describes the intended delivery as home, privacy, terms, account-deletion, support, and 404 pages. The current repository cannot be confirmed to contain that complete scope: its tracked tree has only seven root-level files and none of those page directories. Text in `README.md` and `index.html` describes an app for communication and audio/video calls; these are descriptions in site content, not independent verification of a functioning app.

### Main components and flows
- `index.html`: an Arabic, RTL HTML document that references shared assets and currently renders a privacy-policy page with draft legal text. Its links refer to `privacy/`, `terms/`, `delete-account/`, and `support/`, but those pages are absent from the current tree.
- `app.js`: framework-free JavaScript. It opens/closes the mobile menu, closes it when a link is chosen or Escape is pressed, and configures download and support links from `window.ZMRT_CONFIG`.
- `styles.css`: responsive site styling, including small-screen and reduced-motion rules.
- `404.html`: a standalone error page; `favicon.svg`: the site icon; `robots.txt`: blocks crawling for all agents (`Disallow: /`).

The configuration flow intended by `app.js` reads `GOOGLE_PLAY_URL` and `SUPPORT_EMAIL` from `window.ZMRT_CONFIG`. It enables a store URL only when it is HTTPS on `play.google.com/store/apps/details` and has an `id`, or enables support when the email has a plausible format. However, tracked files do not include `config.js` even though `index.html` and `404.html` reference it, so working configuration cannot be confirmed in the current repository.

### Short tree of important files
```text
.
├── 404.html       Not-found page; imports CSS, JavaScript, and the referenced configuration
├── README.md      Scope, opening, configuration, and quality guidance
├── app.js         Navigation-menu and download/support-link behavior
├── favicon.svg    SVG site icon
├── index.html     Current Arabic HTML privacy-policy document
├── robots.txt     Disallows crawling and indexing
└── styles.css     Responsive RTL styling and motion rules
```

### Technology, setup, running, testing, and build
According to `README.md` and the actual files, this is a static HTML/CSS/JavaScript project with no framework or declared build dependencies. There is no tracked `package.json`, lockfile, manifest, build/test configuration, or CI; therefore no tool versions or dependencies can be documented, and no build or test commands should be inferred. The README says to extract the ZIP and open `index.html` directly, and describes an `index.html`-aware static host for clean `/privacy` and `/terms` paths; the corresponding directories are currently absent.

The README lists these proposed configuration key names without values: `GOOGLE_PLAY_URL`, `SUPPORT_EMAIL`, `DEVELOPER_NAME`, `SITE_URL`, and `LEGAL_APPROVED`. The first two are read in `app.js`; the other three are mentioned only in the README and have no visible use in tracked files. No configuration values or secrets are documented here.

### Practical notes for a new developer and unresolved points
Start by comparing the actual file list with the scope described in `README.md`, and verify that the privacy, terms, account-deletion, and support pages and `config.js` exist before treating links or configuration as complete. The README explicitly says the legal material is an unapproved draft and that the support inbox, Google Play URL, developer name, site domain, and legal-approval status need verification/configuration; it also says support via `mailto` does not implement account deletion. The README recommends manual checks at 360, 768, and 1440 pixels, keyboard navigation, and reduced motion, but the repository does not record results for those checks. No automated tests or CI are visible. `robots.txt` blocks crawling, and the HTML pages use `noindex,nofollow`; do not remove these or publish before content approval and verification of the production domain. The repository alone does not establish backend details, mobile-app behavior, or the accuracy of legal statements.
