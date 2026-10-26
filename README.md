# Marlin – Dubai taxi website (static, no build step)

Files: index.html, vercel.json, robots.txt, firestore.rules

## 1. Deploy on Vercel
1. Push this folder to a GitHub repo (or drag it into vercel.com/new).
2. Import the repo in Vercel. Framework preset: **Other**. No build command, no output directory.
3. Click Deploy. Add your domain under Project > Settings > Domains.

## 2. Save bookings in Firebase (optional, free tier is enough)
1. console.firebase.google.com > Add project.
2. Build > Firestore Database > Create database (production mode).
3. Firestore > Rules > paste firestore.rules > Publish.
4. Project settings > Your apps > Web (</>) > register app, copy the config.
5. In index.html find `const FB={apiKey:"",...}` and paste your values.
6. Authentication is not needed. Bookings appear in Firestore > bookings.
7. Without Firebase, bookings are only kept in the visitor's browser and the WhatsApp message.

Firebase web keys are not secrets; the rules protect your data. Also set an allowed-domain restriction on the key in Google Cloud Console.

## 3. Replace before launch
Search index.html for: +97140000000 / 97140000000 (phone and WhatsApp), drivers@marlin.example, prices, "Marlin Transport".
Add real car photos by replacing the inline <svg> in the hero with <img src="car.jpg" alt="Marlin sedan">.
Dubai taxi operators need an RTA licence.
