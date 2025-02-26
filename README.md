# BabySteps Appointment Booking System

## Overview
The **BabySteps Appointment Booking System** is a full-stack application that allows users to book prenatal care appointments with doctors. It ensures that appointment slots are correctly calculated based on a doctor's working hours and existing bookings, preventing double-booking issues.

### Tech Stack
- **Backend:** Node.js, Express, MongoDB
- **Frontend:** React.js
- **State Management:** React Context API / Redux (optional)
- **Date Handling:** date-fns / moment.js
- **UI Library:** Material-UI / Bootstrap (optional)

---
## Features
### Backend (Node.js + Express + MongoDB)
- **Doctor Management**
  - View all available doctors
  - Fetch available time slots for a doctor on a given date
- **Appointment Management**
  - View all appointments
  - View details of a specific appointment
  - Create a new appointment with time slot validation
  - Update an appointment while ensuring no slot conflicts
  - Cancel an appointment
- **Validation & Error Handling**
  - Prevents overlapping appointments
  - Validates required fields and date formats
- **(Optional) Real-time Updates**
  - Uses WebSockets (Socket.io) to update available slots in real-time

### Frontend (React.js)
- **Doctor Selection**: View and select a doctor
- **Calendar & Slot View**: Displays available time slots dynamically for a selected date
- **Appointment Booking**
  - Book an appointment with patient details
  - View and manage upcoming appointments
  - Edit or cancel appointments
- **Loading States & Error Handling**
  - Handles API errors gracefully
  - Displays loading indicators when fetching data

---
## Installation & Setup
### Prerequisites
Ensure you have the following installed:
- Node.js & npm
- MongoDB (local or cloud instance)

### Backend Setup
1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/babysteps-appointment-system.git
   cd babysteps-appointment-system/backend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Set up environment variables (`.env` file):
   ```sh
   MONGO_URI=your_mongodb_connection_string
   PORT=5000
   ```
4. Start the server:
   ```sh
   npm index.js
   ```
   The backend will run on `http://localhost:5000`

### Frontend Setup
1. Navigate to the frontend directory:
   ```sh
   cd ../frontend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Start the development server:
   ```sh
   npm run dev
   ```
   The frontend will run on `http://localhost:3000`

---
## API Endpoints
### **Doctor Endpoints**
- `GET /doctors` - Retrieve all doctors
- `GET /doctors/:id/slots?date=YYYY-MM-DD` - Get available slots for a doctor on a specific date

### **Appointment Endpoints**
- `GET /appointments` - Retrieve all appointments
- `GET /appointments/:id` - Get details of a specific appointment
- `POST /appointments` - Create an appointment (with slot validation)
- `PUT /appointments/:id` - Update an appointment
- `DELETE /appointments/:id` - Cancel an appointment

---
## Assumptions & Design Decisions
- **No User Authentication:** The system does not require user login.
- **Fixed Interval Appointments:** Appointments start every 30 minutes.
- **Uniform Working Hours:** Doctors have the same working hours every day.
- **Error Handling:** API responses include detailed error messages.

---
## Optional Enhancements
- **Real-time Updates**: Notify users about newly booked appointments using WebSockets.
- **Improved UI**: Integrate a third-party calendar component for better date selection.
- **Advanced Validation**: Implement additional input checks for better UX.

---
## Contributing
Contributions are welcome! Feel free to submit a PR or open an issue.

