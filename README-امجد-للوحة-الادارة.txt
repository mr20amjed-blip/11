إعداد لوحة AMJAD PROGRAMS

الملفات: admin.html لوحة المدير، index.html (النسخة المربوطة بقاعدة البيانات داخل الحزمة) واجهة الزوار، supabase-config.js إعداد الاتصال، supabase-setup.sql قاعدة البيانات والصلاحيات، amjad-programs-login.html شاشة دخول الزوار.

خطوات الإعداد:
1) أنشئ مشروعاً في Supabase.
2) افتح SQL Editor والصق supabase-setup.sql ثم Run.
3) فعّل Email في Authentication، وعطّل التسجيل العام Signups.
4) من Authentication > Users أنشئ حساب المدير ببريد وكلمة مرور قوية.
5) انسخ UUID للحساب، ثم نفّذ في SQL Editor: insert into public.admin_users(user_id) values ('UUID-المدير-هنا');
6) من Project Settings > API انسخ Project URL و anon/public key وضعهما في supabase-config.js. لا تستخدم service_role key.
7) ارفع الملفات في نفس مجلد GitHub Pages. داخل الحزمة اسم صفحة الزوار هو index.html.
8) افتح admin.html لتسجيل دخول المدير وإدارة البرامج والروابط.

الأمان: سياسات RLS تمنع الزوار من الإضافة والتعديل والحذف. لا توجد واجهة لإنشاء مدير جديد. شاشة دخول الزوار القديمة ذات الرمز داخل HTML ليست حماية حقيقية؛ حماية الإدارة والبيانات تعتمد على Supabase Auth وRLS.
