# ஆலயங்கள் இணையதளம் – தரவு சேகரிப்பு form

Intha form-a yaar vendumaanaalum login illaama fill pannalaam. Data Firebase Firestore-la save aagum, photo-vum athe record-kulla save aagum. Athaala Firebase-oda free **Spark** plan pothum, card details thevai illai.

| File | Enna |
|---|---|
| `index.html` | Public form. Intha link-aiyum QR code-aiyum thaan share pannanum. |
| `admin.html` | Ungalukku mattum: ellaa entries, search, district filter, delete, CSV download |
| `firebase-config.js` | Ungada Firebase keys inga podanum |
| `firestore.rules` | Database security rules |
| `style.css`, `districts.js` | Design, 25 maavattangal |

## 1. Firebase project create pannunga (5 nimisham)
1. https://console.firebase.google.com-la **Add project**-a click pannunga. Name: `aalayangal`. Google Analytics thevai illai.
2. **Build → Firestore Database → Create database**-a click pannunga. Location `asia-south1 (Mumbai)`, **production mode**.
3. **Build → Authentication → Get started → Sign-in method → Google → Enable**. Ithu admin page login-ukku mattum.
4. **Project settings (⚙) → General → Your apps → Web (</>)**-la app register pannunga. Varra `firebaseConfig` values-a `firebase-config.js`-la paste pannunga.
5. Athe `firebase-config.js`-la `ADMIN_EMAILS`-kku ungada Gmail-a podunga.

## 2. Security rules podunga
**Firestore → Rules** tab-la `firestore.rules` file-la irukkira content-a muzhusaa paste pannunga. Athula `your-email@gmail.com`-a ungada Gmail-aa maathi **Publish** pannunga.
- Ellaarum *puthu pathivu* mattum seyyalaam (fields-oda size check pannum).
- Data-va **paakka, maatha, neekka ungalaala mattum thaan mudiyum.** Athaala mobile numbers public-aa veliya theriyaathu.

## 3. GitHub Pages-la podunga
1. GitHub-la `aalayangal` endu oru puthu **public** repo create pannunga.
2. Intha folder-la irukkira ellaa files-aiyum upload pannunga (`README.md` venumnaa vidalaam).
3. **Settings → Pages → Source: Deploy from a branch → main / (root) → Save**.
4. 1–2 nimishathula link ready aagidum: **https://tvpriyangan.github.io/aalayangal/**
5. Firebase **Authentication → Settings → Authorized domains**-la `tvpriyangan.github.io`-a add pannunga. Illaati admin login vela seyyaathu.

## 4. Test pannunga
- Form link-a phone-la thirandu oru test entry podunga.
- `https://tvpriyangan.github.io/aalayangal/admin.html`-la Google login pannunga. Entry anga theriyanum.

## Kurippu
- Photo client side-laye ~650 KB-kku keezha chinnathaakkappadum. Free plan 1 GB storage tharum, athaala sumaar 1,500+ photos-oda entries save pannalaam.
- CSV-la photos irukkaathu, "படம் உள்ளதா" endu oru column mattum varum. Photos-a admin page-la paakkalaam.
- Spam vanthaa Firebase **App Check** (reCAPTCHA)-a on pannalaam.
