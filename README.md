# SS Beauty Salon Website

A complete website for **SS Beauty Salon** owned by **Amrit Singh Charak**.

## Features

- Beautiful, responsive design
- Online booking system with 30-minute time slots
- Real-time slot availability checking
- Online payment via UPI QR code (like Amazon checkout)
- Cash payment option
- Google Sheets integration for booking management
- Automatic email confirmations
- Cancellation tracking in spreadsheet
- Gallery section with salon photos
- Contact information display

## Owner Details

- **Name:** Amrit Singh Charak
- **Phone:** +91 8082815770
- **Email:** vuranimation767@gmail.com
- **UPI ID:** rajputveena177@oksbi
- **Shop Hours:** 9:00 AM - 5:00 PM (Mon-Sat)

## Services Offered

- Body Waxing
- Bridal Services
- Eyebrow Shaping
- Eyebrow Threading
- Facials
- Haircut
- Hairstyling
- Make-up
- Make-up Services
- Manicure
- Massage
- Mobile Salon Service
- Online Booking
- Pedicure
- Shampoo & Conditioning
- Tanning
- Waxing
- Wedding and Event Preparation

---

## Setup Instructions

### Step 1: Upload Images

1. Rename your salon photo to `salon.jpg`
2. Rename your QR code image to `qr-code.png`
3. Place both images in the same folder as `index.html`

### Step 2: Set Up Google Apps Script Backend

1. Go to [Google Apps Script](https://script.google.com)
2. Create a new project
3. Delete the default `Code.gs` file
4. Create a new file and paste the contents of `Code.gs` from this package
5. Save the project

### Step 3: Deploy as Web App

1. Click **Deploy** → **New deployment**
2. Click the gear icon ⚙️ and select **Web app**
3. Set:
   - **Description:** SS Salon Booking API
   - **Execute as:** Me
   - **Who has access:** Anyone
4. Click **Deploy**
5. Copy the **Web App URL**
6. Authorize the script when prompted

### Step 4: Update HTML

1. Open `index.html`
2. Find this line:
   ```javascript
   const GAS_URL = 'YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE';
   ```
3. Replace with your actual Web App URL:
   ```javascript
   const GAS_URL = 'https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec';
   ```

### Step 5: Update Google Apps Script

1. Open your Google Apps Script project
2. Find this line:
   ```javascript
   const SPREADSHEET_ID = 'YOUR_SPREADSHEET_ID_HERE';
   ```
3. Run the `getSpreadsheet()` function once to create the spreadsheet
4. Open the created spreadsheet and copy its ID from the URL
5. Update the SPREADSHEET_ID variable

### Step 6: Upload to GitHub

1. Create a new repository on GitHub
2. Upload these files:
   - `index.html`
   - `salon.jpg` (your salon photo)
   - `qr-code.png` (your UPI QR code)
3. Enable GitHub Pages:
   - Go to **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** → **/(root)**
   - Click **Save**
4. Your website will be live at `https://yourusername.github.io/repository-name`

---

## How the Booking System Works

### For Customers:
1. Visit the website
2. Fill in name, phone, email
3. Select a service
4. Pick a date
5. Choose an available 30-minute time slot (booked slots are disabled)
6. Select payment method:
   - **Cash:** Pay at the salon
   - **Online:** Scan UPI QR code and pay
7. Submit booking
8. Receive confirmation email

### For Owner (Spreadsheet):
The Google Sheet automatically records:
- Booking ID
- Timestamp
- Customer details
- Service & time
- Payment method & status
- Booking status (Confirmed/Cancelled)
- Cancellation date & reason (if cancelled)

### Cancellation Process:
1. Open the Google Sheet
2. Use the **SS Salon Admin** menu
3. Click **Cancel Booking**
4. Enter the Booking ID
5. Enter the reason
6. The spreadsheet updates and emails are sent

---

## File Structure

```
ss-beauty-salon/
├── index.html          # Main website file
├── salon.jpg           # Salon interior photo
├── qr-code.png         # UPI QR code image
├── Code.gs             # Google Apps Script backend
└── README.md           # This file
```

---

## Customization

### Change Colors:
Edit the CSS variables in `<style>`:
```css
:root {
    --primary: #e91e63;    /* Main pink color */
    --secondary: #ff4081;  /* Secondary pink */
    --gold: #ffd700;       /* Accent gold */
}
```

### Add More Services:
Edit the `<select>` element in the booking form and add more `.service-card` divs.

### Change Shop Hours:
Modify the `generateTimeSlots()` function:
```javascript
const startHour = 9;  // Opening time
const endHour = 17;   // Closing time (5 PM)
```

---

## Support

For any issues or questions, contact:
- **Amrit Singh Charak**
- **Phone:** +91 8082815770
- **Email:** vuranimation767@gmail.com

---

## License

This website is created exclusively for SS Beauty Salon.
© 2026 SS Beauty Salon. All rights reserved.
