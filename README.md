# Falcon Transmission - Shop Management System

A professional, mobile-responsive web application for transmission shop management, quote generation, and parts cataloging.

🔗 **Live Demo**: <https://falcontransmissionllc.github.io/Falcon_application/>

-----

## Features

### 📋 Quote Management

- **Create Professional Quotes** - Generate detailed transmission repair quotes with customer and vehicle information
- **Line Item Management** - Add multiple parts, labor, and services with automatic total calculation
- **Quote Numbering** - Auto-generated quote numbers with date tracking
- **Tax Calculation** - Automatic 8% tax computation (configurable)
- **Quote History** - Search and retrieve past quotes by number, customer, or vehicle

### 🔧 Parts Catalog

- **Multi-Transmission Support** - Browse parts for:
  - AW 450-43LE
  - 4L60E (GM)
  - 4L80E (GM)
  - TH400 (GM Classic)
- **Real-time Inventory Status** - Track parts as “In Stock,” “Special Order,” or “Unavailable”
- **Price Lookup** - Full pricing on all transmission components
- **Parts Search** - Quickly find specific parts by transmission type

### 🚗 Vehicle Information

- **VIN Lookup Integration** - Links to external VIN decoder tools:
  - Transend.us
  - WitTrans
- **Detailed Vehicle Entry** - Capture year, make, model, engine, drive type, and VIN

### 🖨️ Print & Export

- **Professional Print Layout** - Clean, printer-friendly quote formatting
- **HTML Export** - Save quotes as standalone HTML files
- **Mobile Printing** - Full support for mobile print-to-PDF workflows

### 🔗 Quick Links

Built-in access to industry resources:

- Transend (transmission modification kits)
- WitTrans (transmission training/tools)
- TransGo (shift correction kits)
- Sonnax (transmission parts)
- RockAuto (parts pricing)
- eBay (secondary marketplace)

-----

## Technical Stack

- **Frontend**: Vanilla JavaScript (ES6+)
- **Styling**: CSS3 with responsive design
- **State Management**: In-memory state object
- **Storage**: Browser localStorage ready (for future phases)
- **Framework**: None - zero dependencies

### Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

-----

## Installation

### Option 1: GitHub Pages (Live)

The app is already deployed and live at:

```
https://falcontransmissionllc.github.io/Falcon_application/
```

### Option 2: Local Development

1. Clone the repository:

```bash
git clone https://github.com/falcontransmissionllc/Falcon_application.git
cd Falcon_application
```

1. Open `index.html` in your browser:

```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

Or use a local server:

```bash
# Python 3
python -m http.server 8000

# Node.js (with http-server)
npx http-server

# Then visit: http://localhost:8000
```

-----

## Usage

### Creating a Quote

1. Click **“New Quote”** from the home screen
1. Enter quote number and date (auto-populated)
1. **Customer Information**:
- Name, phone, email
1. **Vehicle Information**:
- Year, make, model, engine, drive type
- VIN (optional - use VIN Lookup tool)
- Select transmission type
1. **Add Line Items**:
- Click “+ Add Item”
- Enter description, quantity, price
- Item types: Part, Service, or Labor
- Items update automatically with totals
1. **Print or Export**:
- Print: Click “Print Quote” (Ctrl+P)
- Export: Click “Save as PDF” (saves as HTML)

### Searching Parts

1. Click **“Parts Search”**
1. Select a transmission from the dropdown
1. Browse available parts with pricing and availability
1. Parts automatically update when transmission changes

### Viewing Quote History

1. Click **“Quote History”**
1. Use the search bar to filter by:
- Quote number
- Customer name
- Vehicle model

-----

## File Structure

```
Falcon_application/
├── index.html              # Main application (all-in-one file)
├── README.md               # This file
└── SETUP_GUIDE.md          # Deployment troubleshooting
```

The entire application is contained in a single `index.html` file for:

- ✅ Easy deployment
- ✅ No build process needed
- ✅ Works on GitHub Pages directly
- ✅ Simple to maintain and update

-----

## Roadmap

### Phase 2 (Planned Features)

- 📅 **Calendar/Scheduling** - Job scheduling and appointment management
- ⚙️ **Settings Panel** - Configurable tax rates, labor rates, and branding
- 💾 **Data Persistence** - Save quotes to localStorage or cloud database
- 📊 **Analytics** - Revenue tracking and quote statistics
- 👥 **Multi-user Support** - Team management and quote assignment
- 🔐 **Authentication** - User login and access control

### Phase 3 (Future)

- 📱 **Mobile App** - Native iOS/Android applications
- 💳 **Payment Integration** - Accept deposits and payments
- 📧 **Email Integration** - Send quotes to customers automatically
- 🌐 **API** - RESTful API for third-party integrations
- 📞 **CRM Integration** - Connect with customer management systems

-----

## Data Management

### Quote Data Structure

```javascript
{
  id: 1,
  quoteNumber: 'FL-001234',
  customer: 'John Doe',
  vehicle: '2015 Chevy Silverado',
  transmission: '4L60E',
  status: 'pending', // or 'approved'
  total: 3450.00,
  date: '2024-01-15',
  lineItems: [
    { id: 1, description: 'Forward Clutch Pack', quantity: 1, price: 145.00 },
    { id: 2, description: 'Labor - 8 hours', quantity: 8, price: 85.00 }
  ]
}
```

### Parts Catalog Structure

```javascript
{
  '4L60E': {
    name: '4L60E (GM)',
    parts: [
      { id: 'GM-1', name: 'Forward Clutch Pack', qty: 1, price: 145.00, availability: 'in_stock' },
      // ... more parts
    ]
  }
}
```

-----

## Customization

### Update Business Information

Edit the app title and branding:

```html
<h1 class="home-title">FALCON TRANSMISSION</h1>
<p class="home-subtitle">Shop Management Suite</p>
```

### Add/Edit Parts

Modify the `PARTS_CATALOG` object in the JavaScript section:

```javascript
'4L60E': {
  name: '4L60E (GM)',
  parts: [
    { id: 'GM-1', name: 'Forward Clutch Pack', qty: 1, price: 145.00, availability: 'in_stock' },
    // Add more parts here
  ]
}
```

### Change Tax Rate

Find this line and adjust the percentage:

```javascript
const tax = subtotal * 0.08; // Change 0.08 to your rate
```

### Update Quick Links

Edit the `QUICK_LINKS` array to add/remove vendor links:

```javascript
const QUICK_LINKS = [
  { name: 'Transend', url: 'https://transend.us', icon: '🔧' },
  // Add more links
];
```

### Customize Colors

Change the primary color from orange (#FF6B35) to your brand color:

- Search for `#FF6B35` in the `<style>` section
- Replace with your color hex code

-----

## Performance

- **Load Time**: < 1 second (single file, no network requests for core features)
- **File Size**: ~70KB (uncompressed HTML)
- **Mobile Optimized**: Responsive design works on all screen sizes
- **Offline Ready**: Works without internet connection (data saved to memory)
- **No Dependencies**: Zero external libraries or frameworks

-----

## Browser Compatibility

|Browser            |Support|
|-------------------|-------|
|Chrome             |✅ Full |
|Firefox            |✅ Full |
|Safari             |✅ Full |
|Edge               |✅ Full |
|Mobile Safari (iOS)|✅ Full |
|Chrome Android     |✅ Full |
|Samsung Internet   |✅ Full |

-----

## Keyboard Shortcuts

|Shortcut      |Action                 |
|--------------|-----------------------|
|Ctrl+P / Cmd+P|Print current page     |
|Escape        |Close modal dialogs    |
|Tab           |Navigate between fields|
|Enter         |Submit forms           |

-----

## Mobile Installation

Users can save the web app to their home screen:

**iOS (Safari)**:

1. Open in Safari
1. Tap Share button
1. Select “Add to Home Screen”

**Android (Chrome)**:

1. Open in Chrome
1. Tap menu (three dots)
1. Select “Install app”

-----

## Support & Issues

### Troubleshooting

See <SETUP_GUIDE.md> for detailed troubleshooting steps.

### Common Issues

- **Page won’t load**: Clear browser cache (Ctrl+Shift+Delete)
- **Styling looks wrong**: Hard refresh (Ctrl+Shift+R)
- **GitHub Pages not updating**: Wait 2-3 minutes after pushing

### Report a Bug

Create an issue on GitHub with:

- Browser and version
- Steps to reproduce
- Expected vs. actual behavior
- Screenshots if applicable

-----

## Contributing

To contribute improvements:

1. Fork the repository
1. Create a feature branch: `git checkout -b feature/your-feature`
1. Make your changes to `index.html`
1. Commit: `git commit -m "Add your feature"`
1. Push: `git push origin feature/your-feature`
1. Create a Pull Request

-----

## License

This project is proprietary software owned by Falcon Transmission LLC.

-----

## About Falcon Transmission

Falcon Transmission LLC is a professional transmission repair and rebuilding shop specializing in high-performance transmission solutions.

- 📍 **Location**: [Your Location]
- 📞 **Phone**: [Your Phone Number]
- 📧 **Email**: [Your Email]
- 🌐 **Website**: [Your Website]

-----

## Version History

### v1.0.0 - Launch (March 2024)

- ✅ Quote generation system
- ✅ Parts catalog with 4 transmission types
- ✅ Quote history and search
- ✅ VIN lookup integration
- ✅ Print and export functionality
- ✅ Mobile-responsive design
- ✅ GitHub Pages deployment

-----

## Frequently Asked Questions

**Q: Where is my data saved?**  
A: Currently, data is stored in the browser’s memory. When you refresh, sample quotes remain but new quotes created are lost. Phase 2 will add persistent storage.

**Q: Can I use this offline?**  
A: Yes! Once loaded, the app works without internet. External links (VIN lookup, quick links) require internet.

**Q: Can I customize the parts list?**  
A: Yes! Edit the `PARTS_CATALOG` in the HTML file to add/remove/update parts and pricing.

**Q: Is this secure?**  
A: The current version stores data client-side only. Phase 2 will add backend security for production use.

**Q: Can multiple users access this simultaneously?**  
A: Currently, it’s designed for single-user use. Multi-user support is planned for Phase 2.

-----

## Acknowledgments

Built with vanilla JavaScript, CSS3, and a focus on simplicity and usability.

-----

**Last Updated**: March 2024  
**Status**: Active Development  
**Maintained By**: Falcon Transmission LLC
