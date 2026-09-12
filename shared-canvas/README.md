# 🎨 Real-Time Collaborative Shared Canvas

A web-based, device-agnostic collaborative drawing board powered by HTML5 Canvas and Firebase Realtime Database. This application allows multiple users to draw on a shared canvas in real-time, regardless of their device's screen size.

## ✨ Features

- **Real-Time Synchronization:** Instant drawing updates across all connected devices using Firebase Realtime Database.
- **Auto-Scaling (Responsive Canvas):** Uses relative coordinate scaling (0 to 1 ratios) to ensure the drawing remains perfectly aligned and proportioned across different screen sizes (e.g., Mobile vs. Tablet vs. Desktop).
- **Glassmorphism UI:** A sleek, modern user interface with blurred backgrounds and a lock-screen aesthetic.
- **Dynamic Neon Brush:** Adjustable brush size with built-in shadow/glow effects for a neon drawing experience.
- **Magic Color Picker:** Choose custom colors or use the random color generator 🎲.
- **Custom Backgrounds:** Users can upload their own images to set as the canvas background.
- **Undo & Clear:** Revert your last drawn stroke or clear the entire canvas for everyone.

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript (Canvas API)
- **Backend/Database:** Firebase Realtime Database (BaaS)

## 🚀 Setup & Installation

To run this project locally or host it yourself, you need to configure your own Firebase project.

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/shared-canvas.git](https://github.com/your-username/shared-canvas.git)


1) Set up Firebase:

   Go to the Firebase Console and create a new project.
   
   Navigate to Build > Realtime Database and click Create Database.
   
   Start in Test Mode (or ensure your Rules are set to ".read": true and ".write": true).
   
   Register a Web App in your Firebase project settings to get your configuration keys.


2) Configure the App:

   Open index.html.
   
   Locate the firebaseConfig object around line 125.
   
   Replace the placeholder values with your actual Firebase configuration keys:
   
   JavaScript
   const firebaseConfig = {
       apiKey: "YOUR_API_KEY",
       authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
       databaseURL: "YOUR_DATABASE_URL",
       projectId: "YOUR_PROJECT_ID",
       // ...
   };

3) Run the App:
   
   Simply open index.html in any modern web browser.
   
   No local server is strictly required, though you can use tools like Live Server in VS Code.
   
   To test collaboration, open the same file (or hosted link) on two different devices!

💡 How Auto-Scaling Works
Instead of saving absolute pixel values (e.g., x: 500px, y: 400px), the application calculates the touch/mouse position as a ratio of the current screen dimensions (e.g., x: 0.5, y: 0.4). When retrieving data, these ratios are multiplied by the viewing device's screen size, ensuring the drawing is perfectly reconstructed on any display.
