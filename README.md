# 🍊 OrangeSense: Orange Yield Estimation

Mobile application to monitor orange harvests detected by a camera-equipped drone.
It shows how many oranges were counted, how many are good or defective, and how production changes over time.

This app is the user interface of a drone-based fruit detection project. Oranges are detected in images with a YOLO model (`assets/yolo11n.pt`), and the results are displayed in the app.

## Features

| Screen | What it shows |
|---|---|
| **Dashboard** | Entry point to all sections of the app |
| **Summary** | Total oranges, share of good vs. defective oranges, and storage quality tips |
| **Trend analysis** | Evolution of the production over time |
| **History** | Monthly data: total, good, bad, quality rate and change |
| **Drone tracking** | Flight information (battery, altitude, speed, signal) and mission details |
| **Account** | Registration and login (JWT authentication) |

> The drone tracking screen currently uses demo values.

## Tech stack

- **Mobile app:** React Native with Expo, React Navigation, Axios
- **Backend API:** Node.js, Express, MongoDB (Mongoose), JWT authentication, Multer for image uploads
- **Detection model:** YOLO11n (Ultralytics)

## Project structure

```
├── App.js, index.js          # App entry points
├── *Screen.js                # App screens (Dashboard, Summary, Trends, History, Tracking)
├── components/               # Shared UI components (Navbar)
├── store/                    # Authentication state
├── api.js                    # API client (Axios)
├── assets/                   # Images, fonts and the YOLO model
└── backend/
    ├── server.js             # Express server
    ├── routes/               # API routes (auth, users, data, activities)
    ├── controllers/          # Route logic
    ├── models/               # MongoDB models
    ├── middlewares/          # Auth and CORS
    └── config/               # Database connection
```

## Getting started

### Backend

```bash
cd backend
npm install
cp .env.example .env    # then fill in your own values
npm start
```

### Mobile app

```bash
npm install
npx expo start
```

Open the app with Expo Go on your phone, or in an Android/iOS emulator.

## Author

Skandar Makari · [GitHub](https://github.com/MakariSkander)
