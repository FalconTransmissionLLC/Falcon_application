[README (3).md](https://github.com/user-attachments/files/26249607/README.3.md)
# 🦅 Falcon Transmission LLC — Digital Shop Manager

> A complete mobile-first shop management system for Falcon Transmission LLC. Built as a single-page web app with real-time cloud sync powered by Firebase Firestore.

---

## 🔗 Live App

**[https://falcontransmissionllc.github.io/Falcon_application/](https://falcontransmissionllc.github.io/Falcon_application/)**

---

## ✨ Features

- **📊 Dashboard** — Live overview of open repair orders and unpaid invoices
- **🛠️ Repair Orders** — Create, track, and manage repair orders with full service checklists
- **✍️ Digital Signatures** — Customers can sign work orders directly on screen
- **🧾 Invoices** — Auto-generate invoices from repair orders with PDF download
- **👥 Customer Management** — Store customer contact info and vehicle history
- **☁️ Cloud Sync** — All data saved to Firebase Firestore, syncs across every device in real time
- **📱 Mobile-First** — Designed to be used on a phone or tablet at the shop

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, JavaScript (Vanilla) |
| Database | Firebase Firestore |
| Hosting | GitHub Pages |
| PDF Export | html2pdf.js |
| Fonts | Barlow Condensed, IBM Plex Mono |

---

## 🚀 Getting Started

This app runs entirely in the browser — no server or build step required.

### Run locally
1. Clone the repo:
   ```bash
   git clone https://github.com/FalconTransmissionLLC/Falcon_application.git
   ```
2. Open `index.html` in any modern browser

### Deploy changes
1. Edit `index.html`
2. Commit and push to the `main` branch
3. GitHub Pages auto-deploys within ~2 minutes

---

## 🗂️ Project Structure

```
Falcon_application/
├── index.html      # Complete app — all HTML, CSS, and JS in one file
└── README.md       # This file
```

---

## ☁️ Firebase Configuration

The app connects to a Firebase Firestore database. All shop data (customers, repair orders, invoices) is stored under:

```
Collection: falcon
Document:   shopdata
```

To use your own Firebase project, update the `firebaseConfig` object inside `index.html`:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  ...
};
```

---

## 📋 How to Use

### Add a Customer
1. Tap **Customers** tab → **+ Add Customer**
2. Enter name, phone, and email
3. Tap **Save Customer**

### Create a Repair Order
1. Tap **Repair Orders** tab → **+ New Repair Order**
2. Select customer, enter vehicle info
3. Check off services performed
4. Add line items with pricing
5. Get customer signature → **Save**

### Generate an Invoice
1. Open any repair order
2. Tap **🧾 Create Invoice**
3. Invoice is auto-created from the repair order
4. Tap **📥 Download PDF** to save or print

---

## 📞 Contact

**Falcon Transmission LLC**  
Professional Transmission Service  

---

*Built with ❤️ for Falcon Transmission LLC*
