# MediMind - Smart Medicine Management System

A comprehensive web-based medicine management application built with React.js that helps patients manage their medications with smart features like OCR text extraction, voice reminders, stock tracking, and emergency alerts.

## 🚀 Features

### Core Features

- **Medicine Management**: Add medicines manually or using OCR text extraction from medicine strip photos
- **Smart Reminders**: Customizable reminder schedules with voice alerts and browser notifications
- **Stock Tracking**: Automatic stock reduction and refill alerts 3 days before depletion
- **Emergency Detection**: SMS alerts to caregivers for missed doses (3 consecutive, 24 hours, or 5 consecutive misses)
- **Adherence Analytics**: Weekly/monthly adherence graphs and statistics
- **PDF Reports**: Doctor-friendly medication adherence reports
- **Multi-language Support**: English, Spanish, and French translations
- **Voice Reminders**: Text-to-speech for medication reminders

### Technical Features

- **OCR Engine**: Tesseract.js for extracting text from medicine images
- **Local Storage**: IndexedDB for offline data storage
- **Responsive Design**: Works on desktop and mobile devices
- **PWA Ready**: Can be installed as a Progressive Web App
- **Accessibility**: Large buttons and high contrast design for elderly users

## 🛠️ Technology Stack

- **Frontend**: React.js 18, React Router, React i18next
- **Database**: Dexie.js (IndexedDB wrapper)
- **OCR**: Tesseract.js
- **Charts**: Chart.js with React-Chartjs-2
- **PDF Generation**: jsPDF
- **Icons**: Lucide React
- **Styling**: Custom CSS with responsive design

## 📦 Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd smart-medicine-reminder
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start the development server**

   ```bash
   npm start
   ```

4. **Open your browser**
   Navigate to `http://localhost:3000`

## 🏗️ Project Structure

```
src/
├── components/           # Reusable UI components
│   ├── Navigation.js    # Main navigation component
│   └── ReminderPopup.js # Medicine reminder modal
├── pages/               # Main application pages
│   ├── Home.js         # Today's medicines dashboard
│   ├── AddMedicine.js  # Add new medicine form
│   ├── History.js      # Adherence analytics and charts
│   └── Settings.js     # App configuration
├── services/           # Core business logic modules
│   ├── database.js     # IndexedDB operations
│   ├── ocrEngine.js    # OCR text extraction
│   ├── reminderEngine.js # Reminder scheduling
│   ├── stockEngine.js  # Stock tracking
│   ├── emergencyEngine.js # Emergency detection
│   ├── smsEngine.js    # SMS alert system (mock)
│   ├── graphGenerator.js # Chart data generation
│   └── pdfGenerator.js # PDF report creation
├── i18n/               # Internationalization
│   └── config.js       # Language configurations
├── App.js              # Main application component
├── index.js            # Application entry point
└── index.css           # Global styles
```

## 🎯 Usage Guide

### Adding a Medicine

1. **Navigate to "Add Medicine"**
2. **Upload Medicine Image** (optional)
   - Click "Choose Image" to upload a photo of the medicine strip
   - Click "Extract text from image" to use OCR
   - The system will auto-fill detected information
3. **Enter Medicine Details**
   - Medicine name (required)
   - Nickname for easy identification
   - Dosage information
   - Total quantity/stock
4. **Set Reminder Times**
   - Add multiple reminder times (e.g., 08:00, 14:00, 20:00)
   - Use 24-hour format
5. **Add Caregiver Phone** (optional)
   - Emergency SMS alerts will be sent to this number
6. **Save Medicine**

### Managing Reminders

- **Taking Medicine**: Click "Taken" when the reminder appears
- **Snoozing**: Click "Snooze 10 min" to delay the reminder
- **Skipping**: Click "Skip" if you intentionally skip the dose
- **Voice Reminders**: The app will speak the reminder message

### Viewing History & Analytics

1. **Navigate to "History"**
2. **Select Medicine**: Choose specific medicine or "All Medicines"
3. **Choose View**: Weekly, Monthly, or Time Pattern analysis
4. **Generate PDF Report**: Download comprehensive adherence report

### Configuring Settings

1. **Navigate to "Settings"**
2. **Personal Information**: Set patient and doctor names
3. **Emergency Contact**: Configure caregiver phone number
4. **Language**: Choose from English, Spanish, or French
5. **Notifications**: Enable/disable browser notifications, sounds, and voice
6. **Test Features**: Test SMS and voice functionality

## 🔧 Configuration

### SMS Integration (Production)

The current SMS implementation is a mock service. For production use, integrate with:

- **Twilio**: Uncomment and configure the Twilio service in `smsEngine.js`
- **AWS SNS**: Use the AWS SNS service example
- **Other SMS Gateways**: Implement custom SMS service

### Environment Variables

Create a `.env` file for production SMS services:

```env
REACT_APP_TWILIO_ACCOUNT_SID=your_account_sid
REACT_APP_TWILIO_AUTH_TOKEN=your_auth_token
REACT_APP_TWILIO_PHONE_NUMBER=your_phone_number
```

## 📱 Mobile & PWA Support

The application is fully responsive and can be installed as a PWA:

1. **Chrome/Edge**: Click the install icon in the address bar
2. **Safari**: Use "Add to Home Screen" from the share menu
3. **Android**: Use "Add to Home Screen" from the browser menu

## 🔒 Privacy & Security

- **Local Storage**: All data is stored locally in the browser
- **No Cloud Sync**: Data never leaves the user's device
- **HIPAA Considerations**: Suitable for personal use, consult legal for clinical use
- **Image Processing**: OCR processing happens locally in the browser

## 🧪 Testing

### Manual Testing Checklist

- [ ] Add medicine with OCR
- [ ] Add medicine manually
- [ ] Set multiple reminder times
- [ ] Test reminder popup actions
- [ ] Verify stock tracking
- [ ] Check refill alerts
- [ ] Test emergency detection
- [ ] Generate PDF reports
- [ ] Switch languages
- [ ] Test voice reminders
- [ ] Verify mobile responsiveness

### Browser Compatibility

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

### Deploy to Static Hosting

The built files in the `build/` directory can be deployed to:

- **Netlify**: Drag and drop the build folder
- **Vercel**: Connect your Git repository
- **GitHub Pages**: Use the `gh-pages` package
- **AWS S3**: Upload to S3 bucket with static hosting

### Docker Deployment

```dockerfile
FROM nginx:alpine
COPY build/ /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:

1. **Check the Issues**: Look for existing solutions
2. **Create an Issue**: Report bugs or request features
3. **Documentation**: Refer to code comments for technical details

## 🔮 Future Enhancements

- [ ] Medication interaction checker
- [ ] Integration with pharmacy APIs
- [ ] Wearable device notifications
- [ ] Machine learning for adherence prediction
- [ ] Telemedicine integration
- [ ] Family member dashboard
- [ ] Medication cost tracking
- [ ] Insurance integration

## 📊 Database Schema

### Medicines Table

- `id`: Primary key
- `name`: Medicine name
- `nickname`: User-friendly name
- `dosage`: Dosage information
- `timings`: JSON array of reminder times
- `quantity`: Total quantity
- `remaining`: Current stock
- `image_url`: Medicine image URL
- `caregiver`: JSON caregiver information
- `created_at`: Creation timestamp

### DoseLog Table

- `id`: Primary key
- `medicine_id`: Foreign key to medicines
- `date`: Dose date (YYYY-MM-DD)
- `time`: Dose time (HH:MM)
- `status`: taken/missed/skipped/emergency_alert
- `notes`: Additional information
- `created_at`: Log timestamp

### Settings Table

- `id`: Primary key
- `key`: Setting name
- `value`: Setting value

---

**Built with ❤️ for better medication adherence and patient health outcomes.**
