# 🏛️ AI Campus Ops
### *Autonomous Real-Time Resource & Facility Allocation System*

[![React 19](https://img.shields.io/badge/React-19.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-8.3-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS v4](https://img.shields.io/badge/Tailwind_CSS-v4.0-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-v20+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express 5](https://img.shields.io/badge/Express-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 🔗 Quick Project Links & Live Access

| Resource | Direct Link | Description |
|:---|:---|:---|
| 🌐 **Unified Web App (Production)** | [http://localhost:5000](http://localhost:5000) | Full Stack Application (Express + React Dist) |
| ⚡ **Dev Server (Fast Refresh)** | [http://localhost:5173](http://localhost:5173) | Vite Hot-Reloading Development Interface |
| 📡 **API Health Check** | [http://localhost:5000/health](http://localhost:5000/health) | Backend Service Status & Server Uptime |
| 📊 **Live Telemetry & Analytics** | [http://localhost:5000/api/analytics](http://localhost:5000/api/analytics) | Real-Time Campus Load & Utilization API |
| 🏢 **Facilities Directory API** | [http://localhost:5000/api/facilities](http://localhost:5000/api/facilities) | REST API for Classrooms, Labs, & Halls |
| 🚀 **Cloud Production Hosting** | `https://ai-campus-ops.onrender.com` | 1-Click Deploy via included `render.yaml` |
| 💻 **GitHub Repository** | `https://github.com/kavin-108/ai-campus-ops` | Source Code, Issues & PRs |

---

## 📌 Executive Summary
**AI Campus Ops** is an enterprise-grade campus operations platform designed to solve one of higher education's most persistent bottlenecks: **inefficient facility scheduling, double-booking conflicts, and underutilized infrastructure**. 

Built for modern academic institutions, it combines a **multi-constraint AI heuristic scoring engine** with **live simulated telemetry**, an interactive **Conflict Resolution Command Center**, comprehensive **Facility CRUD Management**, and a clean **Pure White engineering interface** with real-time interactive notification popups.

---

## 🚀 Key Features

### 1. 🧠 Multi-Factor AI Allocation Engine
- **Constraint Heuristic Scoring**: Evaluates candidate rooms against student count, room type, required hardware/network, and availability.
- **Underutilization Penalty**: Prevents assigning small batches (e.g., 20 students) to large auditoriums (150+ seats), maximizing campus throughput.
- **Automated Alternatives**: If a preferred facility is booked, the AI instantly scores and suggests top ranked substitute rooms with percentage match scores.
- **Explainable AI (XAI)**: Generates human-readable reasoning explaining *why* a particular facility was recommended.

### 2. ⚡ Real-Time Conflict Detection & Auto-Resolution
- **Temporal Overlap Scanner**: Evaluates start/end timestamps down to the minute to detect collisions before booking confirmation.
- **One-Click Mitigation**: Faculty and administrators can resolve overlaps by dynamically re-routing sessions to idle spaces.

### 3. 🏢 End-to-End Facility & Schedule CRUD
- **Full Asset Control**: Add new classrooms, labs, or seminar halls with granular specs (chairs, workstations, floor, network speed, projector, smartboard).
- **Instant Status Toggle**: Switch rooms between `Available`, `Occupied`, or `Maintenance` with live visual indicators.
- **Dynamic Filtering**: Search and filter facilities by building, capacity, department, and equipment.

### 4. 📊 Live Telemetry & Campus Rhythm Analytics
- **Occupancy Rhythm Bell Curve**: Hourly trend tracking campus peak windows (e.g., 10:00 AM - 01:00 PM computer lab surges).
- **Utilization Heat Metrics**: Real-time KPI cards displaying Total Facilities, Average Utilization Rate, Active Bookings, and Overlap Count.

### 5. 🎨 Pure White Engineering UI & Micro-Interactions
- **High-Contrast Theme**: Clean white cards, bold slate typography, subtle borders, and zero dark black blocks.
- **Interactive CAD Blueprint Particle Canvas**: Subtle particle nodes and grid parallax reacting smoothly to mouse motion.
- **Live Toast Notification Popups**: Interactive bell dropdown with unread badge counter and floating notification banners on every confirmed booking.

---

## 📐 AI Allocation Algorithm Formulation

The suitability score $S(F, R)$ for facility $F$ matching request $R$ is formulated as:

$$S(F, R) = w_c \cdot C(F, R) + w_t \cdot T(F, R) + w_e \cdot E(F, R) + w_u \cdot U(F) + w_a \cdot A(F)$$

Where:
- **Capacity Efficiency $C(F, R)$ [Weight: 35%]**: Ratio of requested students to facility capacity. Penalizes both overflow ($\text{Count} > \text{Capacity}$) and extreme underutilization.
- **Equipment & Spec Fulfillment $E(F, R)$ [Weight: 25%]**: Verifies availability of mandatory hardware (PCs, projector, 1 Gbps LAN, audio).
- **Historical Load Balance $U(F)$ [Weight: 20%]**: Favors under-booked facilities to balance campus wear-and-tear.
- **Accessibility & Proximity $A(F)$ [Weight: 10%]**: Evaluates floor level and building proximity.
- **Time Availability $T(F, R)$ [Weight: 10%]**: Hard constraint (rejection if binary overlap occurs).

---

## 🛠️ Architecture & Tech Stack

```text
┌─────────────────────────────────────────────────────────────┐
│                    REACT 19 FRONTEND (Vite)                 │
│  - Tailwind CSS v4       - Recharts Telemetry Charts        │
│  - Lucide React Icons    - Custom CAD Parallax Canvas       │
│  - Context API (Auth, Theme, Notifications)                 │
└──────────────────────────────┬──────────────────────────────┘
                               │ RESTful API (Axios)
┌──────────────────────────────▼──────────────────────────────┐
│                    NODE.JS / EXPRESS 5 BACKEND              │
│  - Allocation Engine Service                                │
│  - Conflict Resolution Controller                           │
│  - In-Memory High-Speed Cache & Seed Store                  │
│  - Unified Static Asset Production Serving                  │
└─────────────────────────────────────────────────────────────┘
```

| Layer | Technology |
|:---|:---|
| **Frontend Framework** | React 19 + Vite 8 |
| **Styling** | Tailwind CSS v4, Custom CSS Variables |
| **Icons & Charts** | Lucide React, Recharts |
| **Backend Runtime** | Node.js (v18+) |
| **Web Framework** | Express 5.x |
| **State & Data Store** | In-Memory Relational Mock Engine (MongoDB/PostgreSQL drop-in ready) |

---

## 📂 Project Directory Structure

```text
8-hour-hackathon/
├── backend/
│   ├── src/
│   │   ├── controllers/      # REST API handlers
│   │   ├── data/             # Realistic campus facilities & bookings seed
│   │   ├── routes/           # Express endpoint routers
│   │   └── services/         # AllocationEngine, ConflictDetector, Store
│   └── server.js             # Express 5 entrypoint (serves API + client dist)
├── frontend/
│   ├── public/
│   │   └── favicon.svg       # Custom cyan AI Campus Ops glowing icon
│   ├── src/
│   │   ├── components/       # Layouts, Sidebar, Navbar, ParticleCanvas
│   │   ├── context/          # Auth, Theme, Notification Context providers
│   │   ├── pages/            # Dashboard, SmartAllocation, Facilities, Schedule, Conflicts, Analytics, Login
│   │   └── services/         # Axios API client
│   ├── index.html            # App shell with custom title & meta tags
│   └── vite.config.js        # Vite 8 config
├── DEPLOYMENT_GUIDE.md       # Step-by-step production hosting manual
├── Dockerfile                # Multi-stage production container build
├── render.yaml               # Infrastructure-as-code for Render cloud
├── vercel.json               # Vercel deployment configuration
└── README.md                 # Complete documentation
```

---

## ⚡ Quick Start Guide

### Prerequisites
- Node.js (v18.0 or higher)
- npm (v9.0 or higher)

### Method 1: Concurrent Development Mode (Hot Reload)

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kavin-108/ai-campus-ops.git
   cd ai-campus-ops
   ```

2. **Start Backend Server:**
   ```bash
   cd backend
   npm install
   node server.js
   ```
   *Backend running on:* `http://localhost:5000`

3. **Start Frontend Server:**
   ```bash
   cd ../frontend
   npm install
   npm run dev
   ```
   *Frontend dev app accessible at:* `http://localhost:5173`

---

### Method 2: Single-Port Production Mode (Express + React Dist)

Run the entire application (frontend + API) on a single port (`5000`):

```bash
# Build the production frontend assets
cd frontend
npm install
npm run build

# Start the unified Express server
cd ../backend
npm install
node server.js
```
*Unified production web app accessible at:* **`http://localhost:5000`**

---

## 🔌 API Endpoints Reference

| Method | Endpoint | Description |
|:---:|:---|:---|
| `GET` | `/health` | Server health check and uptime status |
| `GET` | `/api/facilities` | Retrieve all campus facilities with live status |
| `POST` | `/api/facilities` | Register a new campus facility |
| `PUT` | `/api/facilities/:id` | Update an existing facility's specifications |
| `DELETE` | `/api/facilities/:id` | Remove a facility from the campus directory |
| `POST` | `/api/facilities/allocate` | Run the AI allocation algorithm for a request |
| `GET` | `/api/allocations` | Fetch all confirmed bookings & session schedules |
| `POST` | `/api/allocations` | Confirm and lock in a new facility booking |
| `DELETE` | `/api/allocations/:id` | Cancel a booking and release room to available pool |
| `GET` | `/api/conflicts` | Detect all overlapping time slots across campus |
| `POST` | `/api/conflicts/resolve` | Automatically resolve conflict by reassigning room |
| `GET` | `/api/analytics` | Fetch utilization rates, peak window, and stats |
| `GET` | `/api/notifications` | Fetch unread system telemetry alerts |

---

## 🏆 Hackathon Demonstration Script (For Judges)

1. **Sign-In Flow**:
   - Access `http://localhost:5000/login`.
   - Click **"Continue as Admin"** or **"Continue as Faculty Member"** with one-click instant demo credentials.
2. **Explore Campus Telemetry**:
   - Review the **Smart Campus Command Center** with real-time facility counts (20 facilities, 61% utilization).
   - Observe **Real-Time AI Operational Insights** rendered in pure crisp white cards with dark legible text.
3. **Execute Smart AI Allocation**:
   - Navigate to **Smart Allocation**.
   - Input: **"55 Students"**, Type: **"Computer Lab"**, Requirements: **"Computers + Projector + Internet"**, Time: **"10:00 - 12:00"**.
   - Click **"Run Smart Allocation"**. The engine evaluates campus inventory in under 50ms and presents the highest match score with full reasoning.
   - Click **"Confirm Allocation"** — notice the instant floating notification alert and automatic schedule lock.
4. **Inspect Conflict Center**:
   - Head to **Conflict Center** to observe proactive clash detection.
   - Click **"Auto-Resolve"** to view real-time alternative suggestion and one-click schedule realignment.
5. **Manage Campus Facilities**:
   - Visit **Facilities** to view the live grid, toggle availability, edit room capacities, or create new spaces.

---

## 🚢 Deployment Ready

This application includes ready-to-deploy configurations for all major cloud providers:
- **Render**: `render.yaml` blueprint included for auto-deploying the full-stack web service.
- **Vercel**: `vercel.json` included for zero-config frontend hosting.
- **Docker**: Production-ready multi-stage `Dockerfile` with minimal footprint.

Refer to [`DEPLOYMENT_GUIDE.md`](./DEPLOYMENT_GUIDE.md) for step-by-step production rollout instructions.

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE). Built with ❤️ during the 8-Hour Hackathon.

