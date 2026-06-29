<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:090909,50:0d1f0d,100:090909&height=200&section=header&text=NotesMind&fontSize=60&fontColor=81C784&fontAlignY=38&desc=AI-Powered%20Notes%20%26%20Academic%20Resource%20Platform&descAlignY=58&descSize=18&descColor=ffffff" width="100%"/>

<br/>

[![Live Demo](https://img.shields.io/badge/Live_Demo-00C7B7?style=for-the-badge&logo=vercel&logoColor=white)](https://sanjay652005-notes-sharing.vercel.app)
[![API](https://img.shields.io/badge/Backend_API-46E3B7?style=for-the-badge&logo=render&logoColor=black)](https://notes-sharing-q98k.onrender.com)
[![Stack](https://img.shields.io/badge/Stack-MERN-61DAFB?style=for-the-badge&logo=mongodb&logoColor=white)](https://github.com/sanjay-p/notes-sharing)
[![AI](https://img.shields.io/badge/AI-Groq_%7C_Llama_3.1-FF6B35?style=for-the-badge)](https://groq.com)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://github.com/sanjay-p/notes-sharing)
[![License](https://img.shields.io/badge/License-MIT-81C784?style=for-the-badge)](./LICENSE)

<br/>

![GitHub stars](https://img.shields.io/github/stars/sanjay-p/notes-sharing?style=social)
![GitHub forks](https://img.shields.io/github/forks/sanjay-p/notes-sharing?style=social)
![GitHub last commit](https://img.shields.io/github/last-commit/sanjay-p/notes-sharing?color=81C784)

</div>

---

## 🧠 What is NotesMind?

**NotesMind** is a full-stack AI-powered notes platform where you can upload documents, chat with them, generate quizzes, get summaries, and semantically search across your knowledge base — all in one place.

Built with the **MERN stack** and powered by **Groq AI (Llama 3.1)**, it transforms passive notes into an active learning tool with server-side rate limiting, Docker support, and a fully mobile-responsive UI.

```
Upload a PDF → Get instant AI summary → Chat with it → Generate a quiz → Share with friends
```

---

## 🌐 Live Demo

| Service | URL | Status |
|---|---|---|
| 🖥️ Frontend | [sanjay652005-notes-sharing.vercel.app](https://sanjay652005-notes-sharing.vercel.app) | ![Vercel](https://img.shields.io/badge/deployed-brightgreen?style=flat-square) |
| ⚙️ Backend API | [notes-sharing-q98k.onrender.com](https://notes-sharing-q98k.onrender.com) | ![Render](https://img.shields.io/badge/deployed-brightgreen?style=flat-square) |

> **Note:** Backend is hosted on Render free tier — first request may take ~30s to wake up.

---

## ✨ Features

### 🤖 AI-Powered Core
| Feature | Description |
|---|---|
| 💬 **AI Chat** | Contextual Q&A with your uploaded notes via Groq AI (Llama 3.1 70B) |
| 📝 **Auto Summary** | Instant AI-generated TL;DR on every upload |
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

## 🛠️ Tech Stack

```
Frontend      React.js · Vite · Tailwind CSS · Axios
Backend       Node.js · Express.js · Multer · Express Rate Limiter
Database      MongoDB Atlas · Mongoose
Auth          JWT (JSON Web Tokens)
AI            Groq SDK · Llama 3.1 70B · Semantic Search
DevOps        Docker · Docker Compose · Vercel · Render
```

### Why Groq + Llama 3.1?
- **Groq's LPU inference** delivers ultra-fast AI responses (vs standard GPU APIs)
- **Llama 3.1 70B** provides accurate, context-aware note analysis
- **Zero cold-start** on AI responses — summaries generate in under 2 seconds

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB Atlas URI
- Groq API Key ([get one free at console.groq.com](https://console.groq.com))

### 1. Clone

```bash
git clone https://github.com/sanjay-p/notes-sharing.git
cd notes-sharing
```

### 2. Backend Setup

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

### 3. Frontend Setup

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

### 4. Docker (one command)

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
│   ├── uploads/                  # Multer upload destination
│   └── server.js
│
├── frontend/
│   ├── src/
│   │   ├── components/           # Reusable UI (NoteCard, ChatBox, etc.)
│   │   ├── pages/                # Dashboard, Login, Register, NoteView
│   │   ├── hooks/                # useAuth, useNotes
│   │   ├── services/             # Axios API calls
│   │   └── App.jsx
│   └── vite.config.js
│
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

Contributions are welcome!

```bash
# 1. Fork the repo
# 2. Create your feature branch
git checkout -b feature/your-feature-name

# 3. Commit with conventional commits
git commit -m "feat: add your feature"

# 4. Push and open a PR
git push origin feature/your-feature-name
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) and open an issue before major changes.

---

## 📄 License

Licensed under the **MIT License** — see [LICENSE](./LICENSE) for details.

---

## 👨‍💻 Author

**Sanjay P** — Full Stack Developer · Java + MERN · Graduating 2026

[![Portfolio](https://img.shields.io/badge/Portfolio-sanjay--dev--portfolio.netlify.app-FFD54F?style=flat-square&logo=netlify&logoColor=black)](https://sanjay-dev-portfolio.netlify.app)
[![GitHub](https://img.shields.io/badge/GitHub-@sanjay--p-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sanjay-p)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/sanjay-p-90999a307)
[![Email](https://img.shields.io/badge/Email-sanjay.pdev@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:sanjay.pdev@gmail.com)

---

<div align="center">

⭐ **Found NotesMind useful? Drop a star — it helps more people find it!**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:090909,50:0d1f0d,100:090909&height=100&section=footer" width="100%"/>

</div>
