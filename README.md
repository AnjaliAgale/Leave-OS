# 🗓️ LeaveManager – Employee Leave Management System

LeaveManager is a full-stack web application designed to streamline employee leave requests and administrative approvals. It provides a clean, role-based experience for employees and admins, enabling transparent leave tracking, efficient approvals, and better resource planning.

---

## ✨ Key Features

### 👤 Employee
- Secure registration & login
- Apply for different leave types with date validation
- View leave history with real-time status updates
- Filter and search past leave requests
- Delete pending leave requests

### 🛡️ Admin
- Role-based admin login
- View all employee leave requests
- Approve or reject leave requests instantly
- Visual leave calendar (heatmap) for conflict detection
- Filter leaves by status, type, or employee

### 📊 Smart Leave Heatmap
- Color-coded leave visualization by leave type
- Helps detect overlapping leaves
- Enables better workforce planning and load balancing

---

## 🧠 Design & UX Decisions
- Minimal, distraction-free UI for quick actions
- Clear visual feedback for approvals and rejections
- Role-aware dashboards to reduce cognitive load
- Status colors for instant recognition (Approved / Pending / Rejected)

---

## 🛠️ Tech Stack

### Frontend
- React + TypeScript
- Vite
- Tailwind CSS
- React Query

### Backend
- Python (Flask)
- Flask-Login (Authentication)
- Flask-CORS
- SQLite + SQLAlchemy

---

## 🚀 Running the Project Locally (Windows / PowerShell)

### 📥 Clone the Repository
powershell
git clone <your-github-repo>
cd Leave-Manager


🔧 Backend Setup
cd backend
python -m venv venv
venv\Scripts\Activate.ps1
pip install -r requirements.txt
python app.py


Backend runs at: http://localhost:5000

🎨 Frontend Setup (New Terminal)
cd client
npm install
npm run dev


Frontend runs at: http://localhost:5173

<img width="1911" height="937" alt="image" src="https://github.com/user-attachments/assets/f55ef8f7-9ab8-4e50-91ca-bd130fb29568" />
1️⃣ Registration Screen – “Join the Team”

This screen allows new users to create an account with minimal friction.

Key elements:

Username input

Password input

Role selection (Employee or Admin)

Clear primary call-to-action (“Create Account”)

<img width="1914" height="930" alt="image" src="https://github.com/user-attachments/assets/56b4639e-6100-46fc-81d4-cf15bd17a5f4" />
2️⃣ Employee Login Screen

This screen is the default login entry point for regular employees.

Key elements:

Username and password fields

Password visibility toggle for usability

Clear “Sign In” button

Option to navigate to account creation

Option to switch to Admin Login

<img width="1900" height="933" alt="image" src="https://github.com/user-attachments/assets/163679b1-2e3f-4c60-b761-03b8ab55bc8f" />
3️⃣ Admin Login Screen – “Administrative Access Only”

The admin login screen is visually and contextually distinct from the employee login.

Key elements:

Dedicated admin branding and iconography

Clear messaging indicating restricted access

Secure login form

Navigation back to Employee Login

<img width="1267" height="856" alt="image" src="https://github.com/user-attachments/assets/f2514c9a-bd55-4864-b9ae-1f2ae1111392" />
📊 Employee Dashboard – Leave Overview

The Employee Dashboard provides a clear and structured overview of an individual’s leave activity. At the top, summary cards display the total number of leave requests along with their current status—approved, pending, and rejected—allowing employees to quickly understand their leave standing at a glance.

Below the summary, a searchable and filterable leave history table presents detailed information for each request, including leave type, date range, reason, and approval status. Status badges use color-coding to improve readability and instant recognition. A dedicated “New Request” action enables employees to apply for leave directly from the dashboard, ensuring a smooth and efficient workflow.

The overall design emphasizes clarity, minimalism, and transparency, helping employees track their time off without confusion or unnecessary steps.
<img width="1265" height="852" alt="image" src="https://github.com/user-attachments/assets/7314d62c-5c84-4deb-b6ec-7d235e60fb36" />
<img width="1260" height="861" alt="image" src="https://github.com/user-attachments/assets/31030834-6a72-4e83-8617-6ea4dfd08fb4" />
<img width="1262" height="808" alt="image" src="https://github.com/user-attachments/assets/a42788ef-d628-40b7-a2dd-50927ed5592a" />
🛠️ Admin Dashboard

The Admin Dashboard gives managers a complete overview of all employee leave requests with real-time status cards for Approved, Pending, and Rejected leaves 📊.

🗓️ Smart Leave Heatmap

The interactive leave heatmap calendar visualizes employee availability using color-coded leave types 🎨. It helps admins quickly spot overlaps, detect conflicts 🚨, and balance resources ⚖️ by identifying high-absence days.

With filters, search, and quick approve/reject actions ✅❌, the dashboard enables faster decisions and efficient workforce planning 🚀.
This heatmap enables:

Resource balancing ⚖️ by quickly identifying days with high employee absence

Conflict detection 🚨 through highlighted overlap indicators (e.g., 3+ conflicts)

Proactive planning 📅 by navigating across months and assessing workforce availability in advance
<img width="1264" height="836" alt="image" src="https://github.com/user-attachments/assets/d9e17161-fac2-4ab0-bfff-ba8c580e86b5" />
<img width="1202" height="275" alt="image" src="https://github.com/user-attachments/assets/3ee167c7-9532-491d-830d-c7b4e61a958d" />
🔍 Smart Filters & Search

Admins can quickly narrow down leave requests using search, status, and leave type filters. This makes it easy to locate specific requests, track pending approvals ⏳, or review historical data without clutter.

✅❌ Quick Approve / Reject Actions

Pending leave requests come with one-click approve and reject buttons, enabling fast decision-making. Once processed, the request is clearly marked as Approved or Processed, ensuring transparency and preventing duplicate actions 🔒.

Together, these features streamline leave management, reduce admin effort, and improve response time 🚀.







