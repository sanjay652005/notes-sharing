<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:6366f1,100:8b5cf6&height=200&section=header&text=NotesMind&fontSize=60&fontColor=ffffff&fontAlignY=38&desc=AI-Powered%20Notes%20Platform&descAlignY=58&descSize=20" width="100%"/>

<p>
  <a href="https://sanjay652005-notes-sharing.vercel.app" target="_blank">
    <img src="https://img.shields.io/badge/🚀 Live Demo-Vercel-black?style=for-the-badge&logo=vercel" />
  </a>
  <a href="https://notes-sharing-q98k.onrender.com" target="_blank">
    <img src="https://img.shields.io/badge/⚙️ API-Render-46e3b7?style=for-the-badge&logo=render" />
  </a>
  <img src="https://img.shields.io/badge/Stack-MERN-61dafb?style=for-the-badge&logo=mongodb" />
  <img src="https://img.shields.io/badge/AI-Groq%20%7C%20Llama%203.1-ff6b35?style=for-the-badge" />
</p>

</div>

---

## 🧠 What is NotesMind?

**NotesMind** is a full-stack AI-powered notes platform where you can upload documents, chat with them, generate quizzes, get summaries, and semantically search across your knowledge base — all in one place.

Built with the **MERN stack** and powered by **Groq AI (Llama 3.1)**, it's designed to transform passive notes into an active learning tool.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📂 **File Upload** | Upload PDF, TXT, and MD files |
| 🤖 **AI Chat** | Chat with your notes using Groq AI |
| 📝 **Auto Summary** | Instant AI-generated summaries |
| 🧩 **Quiz Generator** | Auto-generate quizzes from your notes |
| 🏷️ **Auto-Tagging** | Smart tags generated from content |
| 🔍 **Semantic Search** | Search by meaning, not just keywords |
| 🔖 **Bookmarks** | Save and organize your important notes |
| 🔗 **Note Sharing** | Share notes with unique public links |
| 🔐 **JWT Auth** | Secure signup/login with token-based auth |
| 🚦 **Rate Limiting** | API protection with request throttling |
| 🐳 **Docker Support** | Containerized for easy deployment |
| 📱 **Mobile Responsive** | Fully responsive across all devices |

---

## 🛠️ Tech Stack

**Frontend**
- React.js + Vite
- Tailwind CSS
- Axios

**Backend**
- Node.js + Express.js
- MongoDB Atlas + Mongoose
- JWT Authentication
- Multer (file uploads)
- Express Rate Limiter

**AI**
- Groq SDK (Llama 3.1 70B)
- Semantic search via embeddings

**DevOps**
- Docker + Docker Compose
- Deployed on Vercel (frontend) + Render (backend)

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB Atlas URI
- Groq API Key

### 1. Clone the repo

```bash
git clone https://github.com/sanjay652005/notes-sharing.git
cd notes-sharing
```

### 2. Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file in `/backend`:

```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_uri
JWT_SECRET=your_jwt_secret
GROQ_API_KEY=your_groq_api_key
```

```bash
npm run dev
```

### 3. Setup Frontend

```bash
cd ../frontend
npm install
```

Create a `.env` file in `/frontend`:

```env
VITE_API_URL=http://localhost:5000
```

```bash
npm run dev
```

### 4. Or use Docker

```bash
docker-compose up --build
```

---

## 📁 Project Structure

```
notes-sharing/
├── backend/
│   ├── controllers/       # Route handlers
│   ├── middleware/        # Auth, rate limiter
│   ├── models/            # Mongoose schemas
│   ├── routes/            # Express routes
│   └── server.js
├── frontend/
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── pages/         # Route-level pages
│   │   └── App.jsx
└── docker-compose.yml
```

---

## 🌐 Live URLs

| Service | URL |
|---|---|
| Frontend | [sanjay652005-notes-sharing.vercel.app](https://sanjay652005-notes-sharing.vercel.app) |
| Backend API | [notes-sharing-q98k.onrender.com](https://notes-sharing-q98k.onrender.com) |

---

## 👨‍💻 Author

**Sanjay P**
- GitHub: [@sanjay652005](https://github.com/sanjay652005)
- LinkedIn: [sanjayp-dev](https://linkedin.com/in/sanjayp-dev)
- Portfolio: [sanjay-dev-portfolio.netlify.app](https://sanjay-dev-portfolio.netlify.app)

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:8b5cf6,100:6366f1&height=100&section=footer" width="100%"/>
</div>
