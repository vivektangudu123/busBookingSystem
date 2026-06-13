# 🚌 ShuttleRide — Bus Booking System

A full-stack bus/shuttle ticket-booking web application. Users sign in with a one-time password (OTP), search for buses between two stops on a chosen date, pick a seat, book it, and manage or cancel their bookings — all from a clean React interface.

<p align="left">
  <img alt="React" src="https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black">
  <img alt="React Router" src="https://img.shields.io/badge/React_Router-6-CA4245?logo=reactrouter&logoColor=white">
  <img alt="Axios" src="https://img.shields.io/badge/Axios-HTTP-5A29E4?logo=axios&logoColor=white">
  <img alt="JWT" src="https://img.shields.io/badge/Auth-JWT-000000?logo=jsonwebtokens&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-green">
</p>

---

## ✨ Features

- **OTP-based authentication** — passwordless login with a mobile number and role; a JWT is issued on verification and stored client-side.
- **Bus search** — find available buses between a source and destination for given travel dates.
- **Seat booking** — select a specific seat on a bus and confirm the booking.
- **Manage bookings** — view all of your bookings with bus name, seat number and booking time.
- **Cancel bookings** — cancel any successful booking directly from the bookings table.
- **Protected sessions** — the stored JWT is validated against the backend before granting access.

## 🛠️ Tech Stack

| Layer | Technology |
|------|------------|
| Frontend | React 18, React Router DOM 6 |
| HTTP | Axios / Fetch API |
| Auth | JWT (stored in `localStorage`), OTP verification |
| Tooling | Create React App (react-scripts 5) |
| Backend API | REST service expected at `http://localhost:5001` (separate repository) |

## 🧭 Application Routes

| Route | Page | Description |
|-------|------|-------------|
| `/` , `/LandingPage` | Landing | Entry / role selection |
| `/login` | Login | OTP login by mobile number |
| `/register` | Register | New user registration |
| `/Home` | Home | Search buses & book seats |
| `/manage-bookings` | Manage Bookings | View / cancel bookings |

## 🔌 Backend API

The frontend (in [`shuttle_ride/`](./shuttle_ride)) talks to a REST backend at `http://localhost:5001`:

| Method | Endpoint | Purpose |
|--------|----------|---------|
| `POST` | `/auth/send_otp` | Send OTP for a mobile number + role |
| `POST` | `/auth/verify_otp` | Verify OTP, return a JWT |
| `POST` | `/auth/jwt` | Validate a JWT |
| `POST` | `/users/search` | Search buses (source, destination, dates) |
| `POST` | `/users/seat-booking` | Book a seat on a bus |
| `POST` | `/users/bookings` | List the logged-in user's bookings |
| `POST` | `/users/cancel-booking` | Cancel a booking |

## 🚀 Getting Started

```bash
# clone and enter the frontend
git clone https://github.com/vivektangudu123/busBookingSystem.git
cd busBookingSystem/shuttle_ride

# install dependencies
npm install

# start the dev server (http://localhost:3000)
npm start
```

> The app expects the booking backend to be running at `http://localhost:5001`.

### Available scripts

| Command | Description |
|---------|-------------|
| `npm start` | Run the app in development mode |
| `npm run build` | Build an optimized production bundle |
| `npm test` | Run the test runner |

## 📁 Project Structure

```
busBookingSystem/
└── shuttle_ride/            # React frontend
    ├── src/
    │   ├── pages/           # LandingPage, login, register, home, bookings
    │   ├── apicalls/        # user.js — auth, search, booking API calls
    │   └── App.js           # routes
    └── package.json
```

## 👤 Author

**Vivek Tangudu**

- GitHub: [@vivektangudu123](https://github.com/vivektangudu123)
- LinkedIn: [vivektangudu](https://www.linkedin.com/in/vivektangudu)
- Email: [vivektangudu@outlook.com](mailto:vivektangudu@outlook.com)

## 📄 License

Released under the MIT License.
