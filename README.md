# 💊 Medication Dispenser Backend API

This is the backend service for a smart **medication dispenser system** built using **Node.js**, **Express**, and **PostgreSQL**. It allows medical staff to schedule medicine doses for patients and provides APIs for **ESP32** devices to fetch the schedules.

---

## ⚙️ Features

- 🧠 Add patient medication schedules (date + time in **IST**)
- 🔄 ESP32-compatible API to fetch today’s schedule
- ⏰ Timezone handling using **Luxon** (IST support)
- 🧪 Debug route to view recent DB entries

---

## 📁 Folder Structure
      medication-dispenser/
      ├── db.js # PostgreSQL connection setup
      ├── server.js # Express app with API routes
      ├── package.json
      ├── .env # DB credentials (not uploaded to GitHub)
      ├── .gitignore
      └── README.md


---

## 🚀 Getting Started

1. Clone the Repo
   
           git clone https://github.com/22bsm070/medication-dispenser.git
           cd medication-dispenser
2. Install Dependencies

           npm install
3.Set up .env File
        Create a .env file in the root with the following content:

        DB_USER=postgres
        DB_PASSWORD=yourpassword
        DB_HOST=localhost
        DB_PORT=5432
        DB_NAME=newdb
⚠️ Replace yourpassword with your actual PostgreSQL password.

4. Create the Required Table
         Run this SQL command in your PostgreSQL client:

           CREATE TABLE medication_schedule (
                          id SERIAL PRIMARY KEY,
                          patient_name TEXT,
                          device INTEGER,
                          pod INTEGER,
                          dose_time TIMESTAMP
                        );


5. Start the Server

        npm start

🌐 Server will run at: http://localhost:3000

🧪 API Endpoints
➕ POST /add-patient
Add a new patient schedule.
        
        Content-Type: application/json
        
                   {
                  "name": "John Doe",
                  "device": 1,
                  "pod": 2,
                  "time": "14:30"  // IST time in HH:mm
                }
## 📅 GET /api/schedule?device=1&pod=2
   Returns today's schedule for the specified device and pod in IST.



## 🐞 GET /debug/show-times
   Returns the last 10 records in the database for debugging purposes.

## 🛠️ Built With
        Node.js

        Express.js

        PostgreSQL

        Luxon

## 👨‍💻 Author
 
 Yash Raj 
 
 GitHub: @22bsm070
        
        
