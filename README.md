# 🌿 GreenMarket — Farmer's Digital Marketplace

A complete, hostable static website for Indian farmers. No backend required for the UI — connect APIs for live data.

---

## 📁 File Structure

```
greenmarket/
├── index.html          ← Homepage
├── marketplace.html    ← Crop buying/selling listings
├── prices.html         ← Live mandi price tracker
├── storage.html        ← Cold storage booking
├── rentals.html        ← Machinery rental + pesticide/seed shop
├── schemes.html        ← Government schemes directory
├── login.html          ← Login page
├── register.html       ← Registration page
├── style.css           ← All styles (shared)
├── app.js              ← Shared JS: language switcher, nav, translations
└── README.md           ← This file
```

---

## 🚀 How to Host (Free Options)

### Option 1: GitHub Pages (Recommended — Free)
1. Create a GitHub account at github.com
2. Create a new repository (e.g. `greenmarket`)
3. Upload all files to the repository
4. Go to Settings → Pages → Source: "main branch / root"
5. Your site goes live at: `https://yourusername.github.io/greenmarket`

### Option 2: Netlify (Free — Drag & Drop)
1. Go to netlify.com → Sign up free
2. Drag the entire `farmer-marketplace` folder onto the Netlify dashboard
3. Done! You get a live URL like `https://greenmarket.netlify.app`

### Option 3: Vercel (Free)
1. Go to vercel.com → Sign up free
2. Import your GitHub repo OR use `vercel deploy` CLI
3. Live at `https://greenmarket.vercel.app`

---

## 🌐 Language Support
- English and Hindi are built in (toggle appears on first visit and in nav)
- Language preference is saved in browser localStorage
- To add more languages: open `app.js`, copy the `en` block in `TRANSLATIONS`, 
  translate all strings, and add a new button in `showLangModal()`

---

## 📡 Making It Fully Live (Backend Integrations)

To make data real (not demo), connect these free/affordable APIs:

### 1. Live Mandi Prices
- **Source**: data.gov.in (Government of India Open Data)
- API: `https://api.data.gov.in/resource/9ef84268-d588-465a-a308-a864a43d0070`
- Free API key at: data.gov.in/user/register
- Replace the static `prices` object in `prices.html` with a `fetch()` call

### 2. User Authentication & Database
- **Firebase (Google)** — Free tier is very generous
  - Authentication: OTP login via mobile (perfect for farmers)
  - Firestore: Store listings, bookings, user profiles
  - Setup: console.firebase.google.com
- **Supabase** — Open source Firebase alternative (free tier)

### 3. Crop Listings (Marketplace)
- Store in Firebase Firestore or Supabase
- Each listing: { crop, qty, price, state, farmer_id, phone, timestamp }
- Use Firestore real-time listeners to show new listings instantly

### 4. SMS Notifications (OTP Login + Booking Confirmations)
- **Twilio** (paid, ₹1–2 per SMS) 
- **MSG91** (Indian provider, cheaper, ₹0.15–0.25 per SMS)
- **Fast2SMS** (cheapest Indian option, ₹0.10 per SMS)

### 5. Maps (Cold Storage & Equipment Location)
- **Google Maps API** — Show storage units on map (free up to 28,000 loads/month)
- Add in storage.html: `<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_KEY">`

### 6. Payment Gateway (When Farmers Pay for Premium)
- **Razorpay** — Most popular in India, easy integration, 2% transaction fee
- **PayU India** — Alternative option

### 7. WhatsApp Business API
- Farmers prefer WhatsApp over email
- Use **Twilio WhatsApp API** or **WATI** to send booking confirmations

---

## 📱 Mobile App (Next Step)
Convert this website to a mobile app using:
- **Progressive Web App (PWA)** — Add manifest.json + service worker (works offline)
- **React Native** or **Flutter** — Native Android/iOS app
- Most Indian farmers use Android → prioritize Android APK

---

## 🔒 Security Checklist Before Going Live
- [ ] Validate all form inputs on the server side
- [ ] Never expose API keys in frontend code (use environment variables)
- [ ] Add rate limiting on listing/booking APIs (prevent spam)
- [ ] Verify phone numbers via OTP before account activation
- [ ] Sanitize user-uploaded content (descriptions, images)
- [ ] Add HTTPS (Netlify/Vercel/GitHub Pages do this automatically)

---

## 💡 Suggested Feature Additions

### High Priority
1. **Farmer Dashboard** — My listings, bookings, earnings tracker
2. **Buyer Dashboard** — Order history, saved searches, price alerts
3. **Price Alerts** — SMS/WhatsApp when a crop hits target price
4. **Image Upload** — Farmers upload crop photos for listings
5. **Weather Widget** — 7-day forecast for farmer's location (OpenWeatherMap API — free)

### Medium Priority
6. **Crop Calendar** — Sowing/harvesting schedule by region and crop
7. **Loan Calculator** — EMI calculator for KCC and other farm loans
8. **Mandi Distance Calculator** — Nearest mandi + transport cost estimator
9. **FPO Directory** — Find and join a Farmer Producer Organization
10. **Language Expansion** — Punjabi, Marathi, Telugu, Tamil

### Future / Advanced
11. **AI Crop Disease Detector** — Upload leaf photo → diagnose disease
12. **Yield Predictor** — ML model using soil, weather, seed variety
13. **Logistics Integration** — Book a truck/mini-truck for crop transport
14. **Digital Weighbridge** — QR-based weight receipt system

---

## 📞 Support & Helplines to Add on Site
- Kisan Call Centre: 1800-180-1551 (free, 24x7)
- PM-KISAN Helpline: 155261 / 011-24300606
- PMFBY (Crop Insurance): 14447
- Soil Health Card: 1800-180-1551

---
