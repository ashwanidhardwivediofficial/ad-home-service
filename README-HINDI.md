# AD HOME SERVICE – Professional Demo Package

## इस package में
- `index.html`: self-contained responsive website (CSS और JavaScript इसी फाइल में हैं)
- Customer, Service Provider और Admin के अलग-अलग demo panels
- Demo booking, provider approval, assignment, booking status update, complaint demo
- Booking / Work Order / Payment Receipt / Admin report PDF download
- Mobile responsive layout

## Demo चलाने का तरीका
1. ZIP extract करें।
2. `index.html` को Chrome में खोलें। CSS/JS इसी फाइल में हैं, इसलिए local `content://` viewer में भी design टूटना नहीं चाहिए।
3. Login / Register खोलें।
4. Customer / Provider / Admin role चुनें।
5. `Try Demo` दबाएँ।

## GitHub Pages पर publish
1. GitHub में नया public/private repository बनाएँ।
2. ZIP extract करके `index.html` और README को repository root में upload करें।
3. Commit करें।
4. Settings → Pages → Deploy from branch → `main` → `/ (root)` → Save।
5. GitHub Pages URL खुलने पर मोबाइल और desktop दोनों पर जाँचें।

## ईमानदार स्थिति / Production से पहले जरूरी
यह deliverable **working interactive front-end demo** है, पूर्ण live marketplace backend नहीं।
- Demo data browser memory में है; refresh पर reset होगा।
- Live user authentication, registration, password reset और persistent database के लिए Supabase project, SQL schema, RLS review और frontend integration अलग से पूरा करना होगा।
- Razorpay live payments, server-side order creation, signature verification, webhook और refund workflow अभी इस demo में connected नहीं हैं।
- Provider KYC upload/verification और admin CMS live नहीं हैं।
- PDF generation के लिए jsPDF CDN internet connection चाहता है।
- Aadhaar या अन्य sensitive identity documents इस demo में collect नहीं किए जाते।
- Production admin role public signup से कभी assign न करें। Secrets (Supabase service role / Razorpay secret) browser या GitHub repository में न रखें।

यह package वेबसाइट का professional interactive preview है, production deployment की पूर्णता का प्रमाण नहीं।


## PWA / Web App (Android पर Install करने के लिए)
इस पुराने वेबसाइट डिज़ाइन में PWA सपोर्ट जोड़ा गया है:
- `manifest.json` — ऐप का नाम, आइकन और standalone display
- `service-worker.js` — बेसिक offline app-shell cache
- `assets/app-icon-192.png` और `assets/app-icon-512.png` — ऐप आइकन
- वेबसाइट में Install App बटन

### मोबाइल में ऐप इंस्टॉल कैसे करें
1. ZIP extract करके सभी files GitHub repository के root में upload करें।
2. GitHub Pages चालू करें। वेबसाइट HTTPS पर खुलनी चाहिए।
3. Android Chrome में वेबसाइट खोलें।
4. `Install App` बटन दबाएँ। यदि बटन से prompt न खुले तो Chrome के ⋮ मेन्यू में `Install app` / `Add to Home screen` चुनें।

ध्यान दें: PWA वेबसाइट को मोबाइल की home screen पर app की तरह install करता है; यह Play Store वाला native APK नहीं है। Offline mode में website का मूल shell खुल सकता है, लेकिन booking, login, payment और बाहरी PDF library जैसी online/backend सुविधाएँ इंटरनेट और backend पर निर्भर रहेंगी। इस पैकेज में वास्तविक Supabase authentication/database या Razorpay live payment अभी configured नहीं है।
