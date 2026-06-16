# 💰 Expensify — Split Expenses with Ease

A modern, browser-based expense tracking application designed to simplify the process of splitting bills and managing shared expenses among friends, roommates, and colleagues. Works fully offline and can be installed on any device as a native app.

---

## 🚀 Features

✨ **Smart Expense Splitting**
- Effortlessly add and manage shared expenses
- Automatically calculate individual contributions
- Support for equal and custom splits
- Pick any date for each expense with the built-in date picker

👥 **Member Management**
- Add multiple participants to expense groups
- Store member profiles with custom avatar photos
- Edit and remove members anytime

💳 **Payment Tracking**
- Track who owes whom with real-time calculations
- Mark individual payments as paid
- Monitor payment status at a glance
- Visualize settlement workflows with optimized transaction minimization

📊 **Visual Analytics (Chart.js)**
- Interactive doughnut chart — spending breakdown by category with percentages
- Bar chart — total amount paid per member, colored by avatar color
- Summary stats: total spent, average expense, top payer

📅 **Expense Date Picker**
- Assign a specific date to every expense
- Edit dates at any time via the edit modal
- Dates displayed in day/month/year format throughout the app

📲 **QR Code Group Sharing**
- Generate a QR code encoding all members and expenses
- Anyone who scans it instantly loads the full group on their device
- Download the QR as a PNG image
- Share via the native device share sheet (WhatsApp, Messages, Gmail, etc.) using the Web Share API
- Falls back to clipboard copy on desktop

📱 **Progressive Web App (PWA)**
- Install Expensify on your phone or desktop like a native app
- Works **fully offline** after first load — no internet connection needed
- Service worker caches all assets including CDN libraries
- "Install App" button appears automatically when your browser supports installation

🎨 **Modern User Interface**
- Elegant purple & gold theme with parchment-toned backgrounds
- Smooth animations, spring transitions, and micro-interactions
- Fully responsive — adapts to any screen size
- Speed-dial floating action button on mobile (tap to fan out actions)
- Slide-out mobile menu with member management

💾 **Persistent Local Storage**
- All data saved automatically in the browser
- No account, no server, no signup required
- Data survives page refreshes and browser restarts

---

## 📂 Project Structure

```
expence_tracker-main/
├── index.html              ← Full app (HTML + CSS + JS, ~100 KB)
├── manifest.json           ← PWA manifest for home screen install
├── sw.js                   ← Service Worker for offline caching
└── expensify-logo.png.png  ← App logo asset
```

| File | Description |
|------|-------------|
| **index.html** | Complete single-file application — all HTML, CSS, and JavaScript |
| **manifest.json** | PWA configuration: app name, icons, theme color, display mode |
| **sw.js** | Cache-first service worker — enables full offline functionality |
| **expensify-logo.png.png** | Application logo and branding asset |

---

## 🛠️ Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- No additional software required — just open the file

### Quick Start (Basic)

1. **Open the Application**
   - Double-click `index.html`, or
   - Drag and drop into your browser, or
   - Use "File → Open" in your browser menu

2. **Add Members**
   - Type a name in the Members panel and press **Add** (or hit Enter)
   - Click **Edit** on any member to upload a profile photo

3. **Add Expenses**
   - Fill in description, amount, who paid, category, and date
   - Select who to split with using the chip selector
   - Click **Add Expense ₨**

4. **Track & Settle**
   - Switch to **Balances** tab to see who owes what
   - Switch to **Settlement** tab for the minimum number of payments needed
   - Mark payments as paid directly on each expense card

5. **Export or Share**
   - Click **PDF Export** in the sidebar to download a professional report
   - Click **Share via QR** to generate a QR code for sharing the group

### Local Development (Recommended for PWA & QR features)

> **Note:** PWA installation and QR sharing require the app to be served over HTTP, not opened as a local file.

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js
npx http-server .

# Using Node.js serve package
npx serve .
```

Then open `http://localhost:8000` in your browser.

For LAN sharing (so other phones on the same WiFi can scan the QR):
```bash
# Find your local IP (e.g. 192.168.1.5) and share:
http://192.168.1.5:8000
```

---

## 📲 QR Code Sharing — How It Works

1. Click **📲 Share via QR** in the sidebar (or via the mobile speed-dial FAB)
2. A QR code is generated encoding all group data as a compressed URL
3. On **mobile**: tap **📤 Share** to open your system share sheet (WhatsApp, Messages, etc.)
4. On **desktop**: tap **📤 Share** to copy the link to clipboard
5. The recipient opens the link → the app **auto-loads** all members and expenses instantly

> ⚠️ For QR sharing to work across devices, the app must be served via HTTP (not `file://`). Use any of the local server commands above.

---

## 📱 Installing as a Mobile App (PWA)

1. Serve the app via a local server or deploy it online
2. Open it in **Chrome** (Android) or **Safari** (iOS)
3. A gold **"📱 Install App"** button will appear in the sidebar or speed-dial menu
4. Tap it → confirm installation → the app appears on your home screen
5. From that point it works **completely offline**

---

## 💡 Usage Tips

- **Date Picker**: Assign the actual date of each expense — not just today's date
- **QR Share**: Best used when the app is hosted on a server or local network
- **Charts**: Switch to the **Stats** tab to see interactive spending charts
- **Offline**: Once installed as a PWA, all features work without internet
- **Speed-Dial FAB**: On mobile, tap the ☰ button (bottom-right) to access QR, PDF, Install, and Menu
- **Profile Photos**: Tap **Edit** on any member to upload a photo
- **Settlement**: The app calculates the minimum number of payments needed to settle all debts

---

## 🎨 Design & Technology

| Layer | Technology |
|-------|-----------|
| Frontend | Pure HTML5, CSS3, Vanilla JavaScript |
| Typography | Playfair Display & DM Sans (Google Fonts) |
| Charts | Chart.js v4.4 (CDN) |
| QR Code | qrcodejs (CDN) |
| PDF Export | html2pdf.js (CDN) |
| Offline | Service Worker + Cache API |
| PWA | Web App Manifest |
| Sharing | Web Share API (with clipboard fallback) |
| Storage | localStorage (auto-save) |

---

## 📋 Browser Compatibility

| Browser | Basic App | PWA Install | QR Share | Charts |
|---------|-----------|-------------|----------|--------|
| Chrome (Android) | ✅ | ✅ | ✅ | ✅ |
| Safari (iOS 15+) | ✅ | ✅ | ✅ | ✅ |
| Chrome (Desktop) | ✅ | ✅ | ✅ | ✅ |
| Edge (Desktop) | ✅ | ✅ | ✅ | ✅ |
| Firefox | ✅ | ❌ | ✅ | ✅ |
| Samsung Internet | ✅ | ✅ | ✅ | ✅ |

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork, improve, and submit pull requests.

---

## 📄 License

This project is open source and available for personal and commercial use.

---

**Made with ❤️ for expense management**

---

*Last Updated: June 2026*
