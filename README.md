<div align="center">

# 🧠 NotesMind

### AI-Powered Smart Note-Taking Web Application

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com/)
[![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io/)

> **Write less. Capture more. Remember everything.**  
> NotesMind is a full-stack MERN note-taking app with AI-assisted summarization, smart tagging, and a clean dark-themed UI — built for students and developers who think fast.

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-Click_Here-FFD54F?style=for-the-badge)](https://github.com/sanjay-p/notesmind)
[![Report Bug](https://img.shields.io/badge/🐛_Report_Bug-Issues-red?style=for-the-badge)](https://github.com/sanjay-p/notesmind/issues)
[![Request Feature](https://img.shields.io/badge/💡_Request_Feature-Issues-blue?style=for-the-badge)](https://github.com/sanjay-p/notesmind/issues)

</div>

---

## 📸 Preview

> *Screenshot placeholder — add your app screenshots here*

| Dashboard | Note Editor | Search & Filter |
|-----------|-------------|-----------------|
| ![Dashboard](./screenshots/dashboard.png) | ![Editor](./screenshots/editor.png) | ![Search](./screenshots/search.png) |

---

## ✨ Features

### 📝 Core Note Management
- **Create, Read, Update, Delete** notes with a rich text editor
- **Pin important notes** to the top of your dashboard
- **Note status** — Active / Archived / Deleted (soft delete with recovery)
- **Character & word count** displayed in real time

### 🤖 AI-Powered
- **Auto-Summary** — generate a quick TL;DR of any note with one click
- **Smart Tag Suggestions** — AI detects topics and proposes relevant tags
- **Content categorization** — notes are grouped by detected subject

### 🔍 Search & Organization
- **Full-text search** across all notes — instant results
- **Filter by tag**, date, or category
- **Sort by** last modified, created date, or title
- **Color labels** for visual organization

### 🔐 Authentication & Security
- **JWT-based auth** with secure HTTP-only cookies
- **Refresh token** rotation for persistent sessions
- **Password hashing** with bcrypt
- **Protected routes** — all notes are user-scoped

### 🎨 UI / UX
- **Dark-themed interface** — easy on the eyes, built for long sessions
- **Responsive design** — works on desktop, tablet, and mobile
- **Smooth animations** with CSS transitions
- **Toast notifications** for all user actions

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React.js, React Router v6, Axios |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB, Mongoose ODM |
| **Auth** | JWT, bcryptjs |
| **AI** | OpenAI API / Groq API (summarization & tagging) |
| **Styling** | CSS Modules / Tailwind CSS |
| **Dev Tools** | Vite, ESLint, Postman |

---

## 📁 Project Structure

```
notesmind/
├── client/                    # React frontend
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   │   ├── NoteCard/
│   │   │   ├── NoteEditor/
│   │   │   ├── SearchBar/
│   │   │   └── TagFilter/
│   │   ├── pages/             # Route-level pages
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Login.jsx
│   │   │   └── Register.jsx
│   │   ├── hooks/             # Custom React hooks
│   │   ├── context/           # Auth & Notes context
│   │   ├── services/          # API call functions
│   │   └── utils/
│   └── package.json
│
├── server/                    # Express backend
│   ├── controllers/
│   │   ├── authController.js
│   │   └── noteController.js
│   ├── models/
│   │   ├── User.js
│   │   └── Note.js
│   ├── routes/
│   │   ├── auth.routes.js
│   │   └── note.routes.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   └── errorHandler.js
│   ├── config/
│   │   └── db.js
│   └── server.js
│
├── .env.example
├── README.md
└── package.json
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js v18+
- MongoDB (local or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- npm or yarn

### 1. Clone the Repository
```bash
git clone https://github.com/sanjay-p/notesmind.git
cd notesmind
```

### 2. Set Up Environment Variables

Create a `.env` file in the `/server` directory:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_REFRESH_SECRET=your_refresh_secret_key
GROQ_API_KEY=your_groq_api_key      # For AI summarization
NODE_ENV=development
```

Create a `.env` file in the `/client` directory:
```env
VITE_API_BASE_URL=http://localhost:5000/api
```

### 3. Install Dependencies

```bash
# Install server dependencies
cd server
npm install

# Install client dependencies
cd ../client
npm install
```

### 4. Run the Application

```bash
# Start the backend (from /server)
npm run dev

# Start the frontend (from /client)
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 🔌 API Endpoints

### Auth Routes — `/api/auth`
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/register` | Register a new user | ❌ |
| `POST` | `/login` | Login and receive tokens | ❌ |
| `POST` | `/refresh` | Refresh access token | ❌ |
| `POST` | `/logout` | Logout and clear session | ✅ |

### Note Routes — `/api/notes`
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `GET` | `/` | Get all notes for current user | ✅ |
| `GET` | `/:id` | Get single note by ID | ✅ |
| `POST` | `/` | Create a new note | ✅ |
| `PUT` | `/:id` | Update note content or metadata | ✅ |
| `DELETE` | `/:id` | Soft-delete a note | ✅ |
| `POST` | `/:id/summarize` | AI summarize note content | ✅ |
| `POST` | `/:id/tag` | AI suggest tags for note | ✅ |

---

## 🗺️ Roadmap

- [x] Core CRUD notes
- [x] JWT Authentication
- [x] Search & filter
- [x] AI summarization
- [x] Pin notes
- [ ] Rich text editor (Quill / TipTap)
- [ ] Note sharing via public link
- [ ] Folder/notebook organization
- [ ] Export notes as PDF / Markdown
- [ ] Collaborative editing (Socket.IO)
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

Contributions are welcome! Here's how:

```bash
# 1. Fork the repo
# 2. Create your feature branch
git checkout -b feature/your-feature-name

# 3. Commit your changes
git commit -m "feat: add your feature"

# 4. Push to the branch
git push origin feature/your-feature-name

# 5. Open a Pull Request
```

Please follow the [Conventional Commits](https://www.conventionalcommits.org/) standard.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](./LICENSE) file for details.

---

## 👨‍💻 Author

**Sanjay P**  
Full Stack Developer | Java + MERN | Graduating 2026

[![Portfolio](https://img.shields.io/badge/Portfolio-sanjay--dev--portfolio.netlify.app-FFD54F?style=flat-square)](https://sanjay-dev-portfolio.netlify.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/sanjay-p-dev)
[![GitHub](https://img.shields.io/badge/GitHub-@sanjay--p-181717?style=flat-square&logo=github)](https://github.com/sanjay-p)
[![Email](https://img.shields.io/badge/Email-sanjay.pdev@gmail.com-EA4335?style=flat-square&logo=gmail)](mailto:sanjay.pdev@gmail.com)

---

<div align="center">

⭐ **If NotesMind helped you, leave a star — it means a lot!**

*Built with ☕ and way too many notes by Sanjay P*

</div>
