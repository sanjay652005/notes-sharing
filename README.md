<div align="center">

<img src="https://img.shields.io/badge/NotesMind-v2.0.0-A78BFA?style=for-the-badge&logoColor=white" alt="NotesMind" />

# NOTESMIND

### Sanjay P — AI Notes Platform

**Full Stack Developer · MERN + Groq AI**

[![Live Demo](https://img.shields.io/badge/LIVE-sanjay652005--notes--sharing.vercel.app-A78BFA?style=for-the-badge&logo=vercel&logoColor=white)](https://sanjay652005-notes-sharing.vercel.app)
[![API](https://img.shields.io/badge/Backend_API-Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://notes-sharing-q98k.onrender.com)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev)
[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)

*Upload a PDF. Chat with it. Generate a quiz. Share with friends. All in one place.*

</div>

---

## ⚡ Overview

NotesMind is a full-stack AI-powered notes platform built around a single workflow — **upload → understand → share**. Drop any PDF, TXT, or Markdown file and instantly get an AI summary, contextual chat, auto-generated quizzes, and smart tags — all powered by Groq's LPU inference engine running Llama 3.1 70B.

Built with the **MERN stack**, containerized with **Docker**, and deployed on **Vercel + Render**.

> **Note:** Backend is on Render free tier — first request may take ~30s to wake up.

---

## ✨ Features

### 🤖 AI Core
| Feature | Description |
|---|---|
| 💬 **AI Chat** | Contextual Q&A with your uploaded notes via Groq AI (Llama 3.1 70B) |
| 📝 **Auto Summary** | Instant TL;DR generated on every upload |
| 🧩 **Quiz Generator** | Auto-generate MCQs and flashcards from any note |
| 🏷️ **Auto-Tagging** | Smart tags extracted from note content |
| 🔍 **Semantic Search** | Search by meaning across your entire knowledge base |

### 📁 Notes Management
| Feature | Description |
|---|---|
| 📂 **File Upload** | Upload PDF, TXT, and MD files via Multer |
| 🔖 **Bookmarks** | Save and organize important notes |
| 🔗 **Note Sharing** | Share notes via unique public links |
| 🗂️ **Note Library** | Browse, filter, and manage all uploaded content |

### 🔐 Security & Infrastructure
| Feature | Description |
|---|---|
| 🔐 **JWT Auth** | Secure signup / login with token-based authentication |
| 🚦 **Rate Limiting** | Server-side API protection via Express middleware |
| 🐳 **Docker Support** | Fully containerized with Docker Compose |
| 📱 **Responsive** | Mobile-first design across all screen sizes |

---

## 🛠 Tech Stack

```
Frontend      React.js · Vite · Tailwind CSS · Axios
Backend       Node.js · Express.js · Multer · Express Rate Limiter
Database      MongoDB Atlas · Mongoose
Auth          JWT (JSON Web Tokens)
AI            Groq SDK · Llama 3.1 70B · Semantic Search
DevOps        Docker · Docker Compose · Vercel · Render
```

### Why Groq + Llama 3.1?
- **Groq's LPU inference** delivers ultra-fast AI responses vs standard GPU APIs
- **Llama 3.1 70B** provides accurate, context-aware note analysis
- Summaries generate in under 2 seconds — no cold-start delay

---

## 🚀 Getting Started

```bash
# Clone
git clone https://github.com/sanjay652005/notes-sharing.git
cd notes-sharing
```

### Backend

```bash
cd backend
npm install
```

Create `/backend/.env`:

```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_uri
JWT_SECRET=your_super_secret_jwt_key
GROQ_API_KEY=your_groq_api_key
NODE_ENV=development
```

```bash
npm run dev
# Server starts at http://localhost:5000
```

### Frontend

```bash
cd ../frontend
npm install
```

Create `/frontend/.env`:

```env
VITE_API_URL=http://localhost:5000
```

```bash
npm run dev
# App starts at http://localhost:5173
```

### Docker (one command)

```bash
docker-compose up --build
# Frontend → http://localhost:5173
# Backend  → http://localhost:5000
```

---

## 🔌 API Reference

### Auth — `/api/auth`

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| `POST` | `/register` | Register new user | ❌ |
| `POST` | `/login` | Login, receive JWT | ❌ |
| `GET` | `/me` | Get current user profile | ✅ |
| `POST` | `/logout` | Logout and clear session | ✅ |

### Notes — `/api/notes`

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| `GET` | `/` | Get all notes (current user) | ✅ |
| `GET` | `/:id` | Get single note by ID | ✅ |
| `POST` | `/upload` | Upload a new note file | ✅ |
| `PUT` | `/:id` | Update note title / tags | ✅ |
| `DELETE` | `/:id` | Delete a note | ✅ |

### AI — `/api/ai`

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| `POST` | `/chat` | Chat with a note (context-aware) | ✅ |
| `POST` | `/summarize/:id` | Generate AI summary for note | ✅ |
| `POST` | `/quiz/:id` | Generate quiz from note | ✅ |
| `POST` | `/tags/:id` | Auto-generate tags for note | ✅ |

### Search — `/api/search`

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| `GET` | `/?q=query` | Semantic search across notes | ✅ |

---

## 📁 Project Structure

```
notes-sharing/
├── backend/
│   ├── controllers/
│   │   ├── authController.js     # Register, login, profile
│   │   ├── noteController.js     # CRUD for notes
│   │   └── aiController.js       # Groq AI — chat, summary, quiz
│   ├── middleware/
│   │   ├── authMiddleware.js     # JWT verification
│   │   └── rateLimiter.js        # Express rate limiting
│   ├── models/
│   │   ├── User.js               # User schema
│   │   └── Note.js               # Note schema (content, tags, summary)
│   ├── routes/
│   │   ├── auth.routes.js
│   │   ├── note.routes.js
│   │   ├── ai.routes.js
│   │   └── search.routes.js
│   ├── uploads/
│   └── server.js
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   └── App.jsx
│   └── vite.config.js
├── docker-compose.yml
├── .env.example
└── README.md
```

---

## 🗺️ Roadmap

- [x] File upload (PDF, TXT, MD)
- [x] JWT Authentication
- [x] AI Chat with notes (Groq / Llama 3.1)
- [x] Auto-summary on upload
- [x] Quiz generation
- [x] Auto-tagging
- [x] Semantic search
- [x] Note sharing via public link
- [x] Bookmarks
- [x] Docker support
- [ ] Rich text editor (TipTap / Quill)
- [ ] Folder / notebook organization
- [ ] Export notes as PDF or Markdown
- [ ] Real-time collaborative editing (Socket.IO)
- [ ] Note version history
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

```bash
git checkout -b feature/your-feature-name
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) and open an issue before major changes.

---

## 📬 Contact

**Sanjay P** — Full Stack Developer · Java + MERN · Graduating 2026

[![Email](https://img.shields.io/badge/sanjay.pdev@gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:sanjay.pdev@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/sanjay-p-90999a307)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/sanjay-p)
[![Portfolio](https://img.shields.io/badge/Portfolio-A78BFA?style=flat&logo=netlify&logoColor=white)](https://sanjay-dev-portfolio.netlify.app)

---

<div align="center">

*Designed & developed by Sanjay P*
*Anna University · B.Tech Information Technology · 2026*

**NotesMind v2.0.0**

</div>
