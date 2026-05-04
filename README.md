# 📚 StudyShare – Study Resource Sharing Platform

A full-stack web platform where students can upload, share, browse, and download study materials such as notes, PDFs, and useful links.

---

## 🌐 Live Demo

👉 [View Live Project](https://study-resource-sharing-platform-frontend.onrender.com)

> ⚠️ **Note:** The backend is hosted on Render's free tier. If the site hasn't been visited in a while, it may take **10–20 seconds** to wake up on the first load.

---

## 🗂 Project Structure

```
study-share/
├── backend/          ← Node.js + Express API
│   ├── middleware/
│   │   ├── db.js         ← PostgreSQL connection pool
│   │   ├── auth.js       ← JWT middleware
│   │   └── schema.js     ← DB table initialization
│   ├── routes/
│   │   ├── auth.js       ← Signup / Login
│   │   ├── resources.js  ← Upload, browse, download, rate, comment
│   │   └── admin.js      ← Admin stats, manage resources & users
│   ├── uploads/          ← Uploaded files stored here
│   ├── server.js         ← Express entry point
│   ├── .env              ← Environment variables
│   └── package.json
└── frontend/         ← Vanilla HTML/CSS/JS
    ├── index.html    ← Browse & search resources
    ├── upload.html   ← Upload files or links
    ├── profile.html  ← User profile + saved items
    ├── admin.html    ← Admin dashboard
    ├── css/style.css
    └── js/app.js     ← Shared auth, API helper, nav
```

---

## ✨ Features

### 1. 🔐 User Authentication
- Signup & login with JWT tokens
- Password hashing with bcryptjs
- Admin role: sign up with `admin@studyshare.com`

### 2. 📤 Upload Study Resources
- Upload PDFs, DOCX, PPTX, TXT, images, ZIP (max 20MB)
- Share links (Google Drive, YouTube, etc.)
- Add title, subject, description and tags
- Drag & drop file upload with progress bar

### 3. 🔍 Browse & Download
- Resource grid with type, subject, rating, downloads
- Click any card to open detail modal
- Download files or open links
- Save/bookmark resources

### 4. 🎯 Search by Subject
- Filter by subject (Math, Physics, Chemistry, etc.)
- Full-text search by title, description or tags
- Sort by newest, oldest, most downloaded, top rated

### 5. ⚙️ Admin Control
- Dashboard with stats overview
- Remove inappropriate resources (soft delete)
- Restore removed resources
- View all registered users

### 6. ⭐ Bonus Features
- 1–5 star ratings per resource
- Comments on resources
- Save/bookmark resources
- Subject breakdown chart in admin panel

---

## 🛠 Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | HTML5, CSS3, Vanilla JS |
| Backend | Node.js, Express |
| Database | PostgreSQL (Render) |
| Auth | JWT + bcryptjs |
| File Upload | Multer |
| Hosting | Render (Backend + Frontend) |
| Fonts | Syne + DM Sans (Google Fonts) |

---

## 🚀 Run Locally

### Backend
```bash
cd backend
npm install
npm start
# API runs at http://localhost:5000
```

### Frontend
Open `frontend/index.html` with VS Code Live Server or:
```bash
cd frontend
python3 -m http.server 3000
# Visit http://localhost:3000
```

---

## 🔌 API Endpoints

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| POST | `/api/auth/signup` | – | Register |
| POST | `/api/auth/login` | – | Login |
| GET | `/api/resources` | – | List/search resources |
| GET | `/api/resources/:id` | – | Resource details |
| POST | `/api/resources/upload` | ✅ | Upload resource |
| POST | `/api/resources/:id/download` | – | Increment downloads |
| POST | `/api/resources/:id/rate` | ✅ | Rate resource |
| POST | `/api/resources/:id/comment` | ✅ | Add comment |
| POST | `/api/resources/:id/save` | ✅ | Toggle save |
| DELETE | `/api/resources/:id` | ✅ | Delete own resource |
| GET | `/api/admin/stats` | 🔐 | Admin stats |
| GET | `/api/admin/resources` | 🔐 | All resources |
| PATCH | `/api/admin/resources/:id/remove` | 🔐 | Remove resource |
| PATCH | `/api/admin/resources/:id/restore` | 🔐 | Restore resource |
| GET | `/api/admin/users` | 🔐 | All users |

✅ = requires login &nbsp;&nbsp; 🔐 = requires admin

---

## 👤 Author

*Udit U Gunagi*
- GitHub: [@Udit-Gunagi](https://github.com/Udit-Gunagi)