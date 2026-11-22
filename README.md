# 🎓 Campus Event Management System

A modern, responsive, and fully functional **College Campus Event Management System** built exclusively with **pure HTML5, CSS3, and Vanilla JavaScript** — without any external frameworks (No React, Angular, Vue, Bootstrap, or Tailwind CSS).

---

## 🌟 Key Features

### 1. 🛡️ Admin Panel
- **Secure Authentication & Route Protection**:
  - Protected admin dashboard (`/admin/dashboard.html`) inaccessible to unauthenticated or student users.
  - Automatic redirect with return URL support.
  - Demo Admin Credentials:
    - **Email:** `admin@campus.com`
    - **Password:** `admin123`
- **Real-time Analytics Dashboard**:
  - Metric cards: **Total Events**, **Total Students**, **Total Registrations**, **Upcoming Events**, and **Pending Registrations** (with pulse alert).
  - Dynamic visual breakdown of events across academic categories.
  - Registration status distribution (Approved, Pending, Rejected percentages).
  - Quick-action moderation table for instant 1-click approvals and rejections.
  - Next upcoming events list with capacity tracking.
- **Full Event CRUD Management (`/admin/manage-events.html`)**:
  - **Create New Events**: Title, category, organizer, description, date, time, registration deadline, venue, maximum capacity, and home-page spotlight toggle.
  - **Image Poster Upload**: Supports uploading local images via `FileReader` (converted to Base64 data URLs) or picking from curated college event themes.
  - **Edit & Update**: Modify any existing event details in real-time.
  - **Delete Events**: Safe deletion with custom confirmation modals and automatic cleanup of associated registrations.
- **Registration Moderation (`/admin/manage-registrations.html`)**:
  - View all student registrations with full attendee profiles (Name, Email, Student Roll No, Department, Mobile).
  - **Approve / Reject Registrations**: Approving or rejecting instantly updates the student's pass status. Rejections support optional administrative feedback notes.
  - Search by student name, roll number, email, or event title.
  - Filter by status (`Pending`, `Approved`, `Rejected`) and by specific event.
  - **Export to CSV**: Download student registration lists for attendance rosters.

---

### 2. 🎓 Student (Client) Panel
- **Student Authentication**:
  - Student Signup (`signup.html`) with academic validation (Name, College Email, Roll No, Department, Mobile, Password match).
  - Student Login (`login.html`) with quick 1-click demo credential autofill.
  - Demo Student Credentials:
    - **Email:** `alex@student.campus.edu`
    - **Password:** `student123`
  - Dynamic navigation bar: Displays logged-in student name, initials avatar, active registration count badge, and quick logout.
- **Modern Home Page (`index.html`)**:
  - High-impact Hero section with university statistics and floating digital pass cards.
  - Spotlight Featured Upcoming Events grid.
  - Category showcase (Technical, Cultural, Sports, Workshops, Seminars, Community).
  - "About Campus Life" section with core pillars.
  - Interactive "Contact Event Administration" form with instant feedback toast notifications.
  - Comprehensive university footer with newsletter subscription.
- **Explore Events Catalog (`events.html`)**:
  - Live search bar (searches titles, descriptions, venues, and organizers).
  - Category filter pills: *All Events, Technical Events, Cultural Events, Sports Events, Workshops, Seminars, Other Events*.
  - Sort by Date (Soonest / Furthest), Title (A-Z), or Capacity.
  - Event cards featuring category badges, venue, date/time, seat availability gauge, and quick-action buttons.
- **Event Details & Real-Time Booking (`event-details.html`)**:
  - Full event brief, guidelines, and organizer details.
  - Dynamic seat capacity bar showing real-time filled percentage.
  - **Smart Registration Validations**:
    - ⛔ Prevents duplicate registrations by the same student.
    - ⛔ Prevents registration if the deadline has passed.
    - ⛔ Prevents registration if maximum capacity is reached (Sold Out).
    - ⚠️ Prompts guest visitors to log in or create an account.
  - Registration modal pre-filled with student profile information.
- **My Registrations & Digital Passes (`my-registrations.html`)**:
  - Summary metrics: *Total Applied, Approved Passes, Pending Review, Rejected*.
  - Filter by registration status.
  - Digital Ticket Card with colored status strip, attendee details, and admin notes.
  - **Print Campus Pass**: Generates a clean, printable entry token with QR mockup for physical check-in at event gates.
  - **Cancel Registration**: Allows cancelling pending applications with confirmation modal.

---

## 📁 Project Structure

```text
Campus-Event/
│
├── index.html                   # Student Home Page & Landing Experience
├── events.html                  # Explore Events Catalog with Category Filters
├── event-details.html           # Full Event Details & Registration Modal
├── my-registrations.html        # Student Registrations & Digital Entry Passes
├── login.html                   # Unified Login (Student & Admin) with 1-Click Demo Fill
├── signup.html                  # Student Registration Form
│
├── admin/
│   ├── dashboard.html           # Admin Overview Dashboard & Statistics
│   ├── manage-events.html       # Admin Event CRUD & Poster Upload
│   └── manage-registrations.html# Registration Moderation (Approve/Reject/CSV Export)
│
├── css/
│   ├── style.css                # Core Design System, Variables, Modals, Toasts & Cards
│   ├── admin.css                # Admin Sidebar Layout, Stat Cards & Management Tables
│   └── responsive.css           # Full Mobile & Tablet Media Query Adaptations
│
├── js/
│   ├── storage.js               # LocalStorage Data Layer & Sample Seed Data
│   ├── auth.js                  # Authentication, Session Guard & Navbar State
│   ├── events.js                # Events Catalog, Filters, Search & Details Logic
│   ├── registrations.js         # Student Registrations Portal & Ticket Printing
│   └── admin.js                 # Admin Dashboard Metrics, Event CRUD & Moderation
│
└── assets/
    └── images/
        ├── default-event.svg    # Vector Event Banner Fallback
        └── default-event.jpg    # Raster Image Fallback
```

---

## ⚡ How Data Synchronization Works

Both the **Admin Panel** and the **Student Panel** share the same browser `localStorage` engine:
1. **Initial Seeding**: If `localStorage` is empty, `storage.js` automatically populates realistic sample events, demo users, and sample registrations.
2. **Instant Event Visibility**: When an admin creates or edits an event in `admin/manage-events.html`, it immediately updates the event catalog and appears on `index.html` and `events.html`.
3. **Instant Registration Visibility**: When a student submits a registration, it instantly reflects in `admin/dashboard.html` and `admin/manage-registrations.html`.
4. **Instant Status Reflection**: When the admin clicks **Approve** or **Reject**, the student immediately sees their updated status banner and ticket pass under `my-registrations.html`.

---

## 🚀 Running the Project Locally

No build tools, npm packages, or bundlers are required!

### Option 1: Using Python (Recommended)
1. Open PowerShell or Terminal in the `Campus-Event` folder.
2. Run:
   ```bash
   python -m http.server 8080
   ```
3. Open your browser and navigate to:
   ```text
   http://localhost:8080
   ```

### Option 2: VS Code Live Server
1. Open the `Campus-Event` folder in VS Code.
2. Right-click `index.html` and select **"Open with Live Server"**.

### Option 3: Direct File Opening
- You can directly double-click `index.html` to open it in Chrome, Edge, Firefox, or Safari.

---

## 🔑 Demo Credentials

| Role | Email | Password | Access |
|---|---|---|---|
| **Admin** | `admin@campus.com` | `admin123` | Full Admin Dashboard, Event CRUD, Registrations |
| **Student** | `alex@student.campus.edu` | `student123` | Event Registrations, My Passes, Profile |
| **New Student** | *Sign up on `signup.html`* | *Any (min 6 chars)* | Custom student profile |
