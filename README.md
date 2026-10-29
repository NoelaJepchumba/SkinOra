
# SkinOra 🌸

SkinOra is an AI-powered skincare web application designed to help users understand their skin and explore personalized skincare recommendations. It aims to make skincare more accessible by connecting AI-powered skin analysis with skincare routines, product discovery, and clinic-related services.

## ✨ Features

- **AI Skin Analysis:** Take or upload a facial photo to analyze visible skin concerns using the Perfect Corp. YouCam API.
- **Skincare Routines:** Explore skincare routine guidance.
- **Product Discovery:** Browse skincare products and recommendations.
- **Clinic Services:** Access clinic-related features available in the application.
- **User Authentication:** Create an account and sign in securely.
- **Google Sign-In:** Authenticate using Firebase Authentication.
- **Profile Management:** Manage your account and personal profile.

## 🛠️ Technologies Used

- React
- Vite
- Node.js
- JavaScript
- Perfect Corp. YouCam API
- Firebase Authentication

## 🚀 Getting Started

### Prerequisites

Before running SkinOra, ensure you have installed:

- Node.js
- npm
- A Perfect Corp. YouCam API key
- A Firebase project configured for authentication

### Installation

**1. Clone the repository**

```bash
git clone YOUR_REPOSITORY_URL
```

**2. Navigate to the project directory**

```bash
cd YOUR_PROJECT_DIRECTORY
```

**3. Install dependencies**

```bash
npm install
```

**4. Configure environment variables**

Create a `.env` file using the project's `.env.example` as a reference. Add your YouCam API key and other required configuration values.

Example:

```env
YOUCAM_API_KEY=your_api_key_here
YOUCAM_API_BASE_URL=https://yce-api-01.makeupar.com
PORT=8787
```

Configure Firebase using the project's existing configuration and enable Google sign-in in the Firebase Console if required.

**5. Start the application**

```bash
npm run dev
```

Open the local URL displayed in your terminal, typically:

http://localhost:5173/

## 📱 How It Works

1. Open SkinOra in your browser.
2. Create an account or sign in.
3. Navigate to the skin-scanning feature.
4. Take a facial photo or upload an existing image.
5. Allow the YouCam API to process the image.
6. View the available skin analysis results.
7. Explore skincare routines, product recommendations, and other available features.

## 🎯 Project Goal

SkinOra aims to make skincare guidance more personal and accessible. It recognizes that skincare products and services vary by location and that users need recommendations relevant to their individual needs and local availability.

## 🔒 Privacy and Security

- API keys and credentials should be stored securely in environment variables.
- Never commit your `.env` file or private credentials to GitHub.
- Obtain consent before analyzing another person's facial image.
- SkinOra provides informational skincare insights and does not replace professional medical advice.

## 🚧 Challenges

Developing SkinOra involved integrating an external AI API, troubleshooting communication between the frontend and backend, and ensuring that the skin-scanning process returned and displayed results reliably.

These challenges highlighted the importance of API integration, error handling, and testing the complete user experience.

## 🔮 Future Improvements

- Improve location-aware skincare product recommendations.
- Expand clinic discovery and booking capabilities.
- Enhance skincare progress tracking.
- Improve scan reliability and user experience.
- Continue strengthening privacy and accessibility.

## 🙌 Acknowledgements

- [Perfect Corp. YouCam API](https://www.perfectcorp.com/business)
- [React](https://react.dev/)
- [Vite](https://vite.dev/)
- [Firebase](https://firebase.google.com/)

---

**SkinOra** — Making skincare more personal, accessible, and easier to navigate.
