الشطرنجي: تطبيق أندرويد (APK)
==============================
الطريقة الأسهل: بناء الـ APK على GitHub (من غير ما تنزّل Android Studio)
------------------------------------------------------------------
1) اعمل حساب على github.com (لو مفيش) وأنشئ Repository جديد (Private أو Public).
2) ارفع كل محتويات المجلد ده فيه (من غير node_modules لو ظهر). أسهل طريقة: زر "uploading an existing file"
   واسحب كل الملفات والمجلدات (لازم المجلد .github يترفع كمان. لو مش ظاهر عندك في الويندوز، فعّل "إظهار الملفات المخفية").
   أو من PowerShell داخل المجلد:
       git init
       git add .
       git commit -m "shatranji"
       git branch -M main
       git remote add origin https://github.com/USERNAME/REPO.git
       git push -u origin main
3) افتح تبويب Actions في الـ Repository ← "Build APK" ← Run workflow (أو هيشتغل لوحده بعد الرفع).
4) بعد ~5 دقايق افتح التشغيل الناجح ← Artifacts ← نزّل shatranji-apk (ملف zip فيه app-debug.apk).
5) انقل app-debug.apk للموبايل وافتحه. لو أندرويد سأل، اسمح بالتثبيت من مصدر غير معروف.

الطريقة التانية: بناء محلي بـ Android Studio
------------------------------------------
1) نزّل Node.js و Android Studio.
2) في PowerShell داخل المجلد:   npm install   ثم   npx cap sync android   ثم   npx cap open android
3) في Android Studio: Build ← Build Bundle(s)/APK(s) ← Build APK(s).
   الملف بيطلع في android/app/build/outputs/apk/debug/app-debug.apk

ملاحظات
-------
- ده APK تجريبي (debug) بيتثبّت على أي موبايل مباشرة. لو عاوز تنشره على Google Play محتاج نسخة موقّعة (release) و AAB.
- اللعبة بتشتغل بدون إنترنت. الخط العربي IBM Plex بيتحمّل من الإنترنت لو متاح، وإلا بيتعرض بخط النظام.
- لتحديث اللعبة: استبدل www/index.html بالنسخة الجديدة وارفع تاني.
