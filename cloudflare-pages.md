# خطوات نشر على Cloudflare Pages - بدون أخطاء ✓

## المتطلبات:
- حساب Cloudflare (مجاني)
- حساب GitHub (لربط الـ Repository)

---

## الخطوة 1: إعداد GitHub

```bash
# في مجلد المشروع
git init
git add .
git commit -m "Initial commit - AM Store"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/am-store.git
git push -u origin main
```

---

## الخطوة 2: نشر على Cloudflare Pages

1. **ادخل إلى**: https://dash.cloudflare.com/
2. **اختر**: Account → Pages
3. **اضغط**: "Create a project"
4. **اختر**: "Connect to Git"
5. **سجل دخولك** إلى GitHub (إذا لم تكن مسجل)
6. **اختر Repository**: am-store
7. **اضغط**: "Connect Account"

---

## الخطوة 3: إعدادات البناء

في صفحة "Build configuration":

| الإعداد | القيمة |
|--------|--------|
| Framework preset | None |
| Build command | `npm run build` |
| Build output directory | `dist` |
| Environment variables | (اترك فارغ) |

---

## الخطوة 4: نشر

1. **اضغط**: "Save and Deploy"
2. **انتظر** البناء (2-3 دقائق)
3. ✓ **تم!** ستحصل على رابط مثل: `https://am-store.pages.dev`

---

## الملفات المطلوبة (موجودة):

✅ **dist/index.html** - ملف HTML الرئيسي  
✅ **dist/assets/index-*.js** - JavaScript المبني  
✅ **package.json** - معلومات المشروع  
✅ **vite.config.ts** - إعدادات البناء  

---

## حل المشاكل الشائعة:

### مشكلة: "Cannot find module"
**الحل**: تأكد من:
```bash
npm install
npm run build
```

### مشكلة: صفحة بيضاء
**الحل**: الملف الموجود صحيح، تحقق من:
- وجود `dist/index.html`
- وجود `dist/assets/` بالملفات

### مشكلة: الـ Routes لا تعمل
**الحل**: أضفنا `_redirects` للمجلد root

---

## التحديثات التلقائية

بعد النشر، أي push جديد على GitHub سيتم بناؤه ونشره **تلقائياً** ✓

```bash
git add .
git commit -m "Update"
git push  # سيتم النشر تلقائياً!
```

---

## الدعم:
- Cloudflare Status: https://www.cloudflarestatus.com/
- Cloudflare Docs: https://developers.cloudflare.com/pages/
