# वेबसाइट LIVE करने की आसान गाइड (Android मोबाइल के लिए)

कोई कोडिंग या टर्मिनल नहीं। नीचे के 4 भाग क्रम से करें। हर भाग के लिए Chrome खोलें और **⋮ मेनू → "Desktop site"** चालू कर लें (बटन आसानी से दिखेंगे)।

## भाग 1 — Supabase (डेटाबेस) — लगभग 10 मिनट
1. **supabase.com** → Sign up → **New project**। नाम: `vanshkehanumanji`, Region: **Mumbai (ap-south-1)**, एक मज़बूत Database Password डालकर कहीं लिख लें।
2. बाईं ओर **SQL Editor → New query**। इस ZIP के `supabase/schema.sql` फ़ाइल को खोलें, पूरा कॉपी करें, यहाँ पेस्ट करें, **Run** दबाएँ। "Success" दिखना चाहिए।
3. **Authentication → Users → Add user → Create new user**: अपना **ईमेल** और **मज़बूत पासवर्ड** डालें, "Auto Confirm User" चुनें।
4. **SQL Editor → New query**: `supabase/create-admin.sql` की दो लाइनें पेस्ट करें, `YOUR-EMAIL@example.com` की जगह अपना वही ईमेल लिखें, **Run**।
5. **Authentication → Sign In / Providers → Email** में **"Allow new users to sign up" बंद (OFF)** करें, Save।
6. **Project Settings → API** से दो चीज़ें कॉपी करके रखें:
   - **Project URL**
   - **anon public key** (`service_role` key कभी कहीं न डालें)

## भाग 2 — GitHub पर कोड डालना — लगभग 15 मिनट
Vercel केवल GitHub से कोड लेता है, इसलिए यह ज़रूरी है।
1. **github.com** पर खाता बनाएँ → **New repository** → नाम `vanshkehanumanji-website` → Create।
2. ZIP को फ़ोन में **Extract** करें (Files by Google / ZArchiver)।
3. रिपॉज़िटरी में **Add file → Upload files**। फ़ोन में फ़ोल्डर एक साथ नहीं चढ़ते, इसलिए **फ़ोल्डर-दर-फ़ोल्डर** चढ़ाएँ: पहले मुख्य फ़ोल्डर की फ़ाइलें (`package.json`, `index.html`, `vite.config.js`, `vercel.json`, `.gitignore`, `.env.example`, `README.md`), फिर `public`, `supabase` की फ़ाइलें, फिर `src` की। हर फ़ोल्डर के लिए **Add file → Create new file** में नाम `src/pages/admin/x` जैसा लिखने पर फ़ोल्डर अपने-आप बन जाता है।
   - **आसान रास्ता:** यह थोड़ा लंबा है। किसी जानकार मित्र के कंप्यूटर से यह काम 5 मिनट में हो जाता है (फ़ोल्डर सीधे खींचकर डाल सकते हैं)।
4. **Commit changes** दबाएँ।

## भाग 3 — Vercel पर LIVE करना — लगभग 5 मिनट
1. **vercel.com** → "Continue with GitHub" → **Add New → Project** → अपनी `vanshkehanumanji-website` चुनें → Import।
2. **Environment Variables** में दो चीज़ें जोड़ें:
   - नाम `VITE_SUPABASE_URL` → मान: आपका Project URL
   - नाम `VITE_SUPABASE_ANON_KEY` → मान: आपकी anon public key
3. **Deploy**। 1–2 मिनट में वेबसाइट लाइव। Project का नाम `vanshkehanumanji` रखें, ताकि पता `vanshkehanumanji.vercel.app` मिल सके (यदि कोई और ले चुका हो तो `vanshkehanumanji-team` आज़माएँ)।
4. Supabase → **Authentication → URL Configuration → Site URL** में अपना वेबसाइट पता डालें।

## भाग 4 — लोगो और फ़ोटो (कोई कोडिंग नहीं)
1. अपनी वेबसाइट पर `/admin/login` खोलें → ईमेल/पासवर्ड से साइन-इन।
2. बाएँ मेनू **Logo** → अपना **असली लोगो** अपलोड → Save।
3. **Founder** → अपनी असली फ़ोटो अपलोड → Save। **Homepage** → मुख्य (hero) फ़ोटो अपलोड → Save।
4. बाकी सब (टीम सदस्य, गैलरी, सूचनाएँ, सेवा) भी इसी डैशबोर्ड से जुड़ेगा।
5. टैब-आइकन (favicon) के लिए GitHub में `public/logo.png` नाम से वही लोगो चढ़ा दें (वैकल्पिक)।

## जाँच (वेबसाइट लाइव होने के बाद)
- सभी मेनू खोलकर देखें, हिन्दी/English बदलकर देखें।
- Join Us फ़ॉर्म खुद भरकर भेजें → Admin → Applications में दिखना चाहिए।
- यदि कुछ ठीक न चले तो जो संदेश दिखे उसका स्क्रीनशॉट भेज दें।
