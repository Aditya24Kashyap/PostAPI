# PostAPI

<p align="center">
  <img src="./public/post-man-clone.png" alt="PostAPI" width="600"/>
</p>

A modern, open-source **Postman alternative** built with **Next.js 15, TypeScript, Prisma, TailwindCSS, shadcn/ui, TanStack Query, and Zustand**.
It provides a sleek UI and developer-focused workflow to test and manage REST APIs and WebSocket connections efficiently.

Built by **[Aditya Kashyap](https://github.com/Aditya24Kashyap)** as a personal project to learn full-stack development with Next.js, Prisma, and OAuth authentication.

---

## ✨ Features

### 🔹 REST API Client
- Send HTTP requests with **methods (GET, POST, PUT, DELETE, etc.)**
- Manage **request parameters, headers, and body (raw JSON / text)**
- **Request response viewer** with pretty JSON formatting
- Track **response time, size, and status**
- Save requests inside **collections** for reusability
- Request history & response persistence

### 🔹 WebSocket Client
- Connect to **ws://** and **wss://** endpoints
- Send and receive messages in real time
- Support for multiple protocols
- View messages with metadata (**direction, payload, size, timestamp**)
- Save messages for later inspection

### 🔹 Workspace & Collaboration
- Create and manage **multiple workspaces**
- **Invite team members** via unique invite links
- Role-based workspace access (Admin, Member)
- View workspace members with overlapping avatars and hover tooltips

### 🔹 Additional Utilities
- Raw request body editor powered by **Monaco Editor**
- JSON pretty print & validation
- Copy to clipboard & auto-format options
- Persistent state management with **Zustand**
- Smooth and modern UI with **shadcn/ui + TailwindCSS**
- AI-assisted features powered by **Google Gemini**

---

## 🛠️ Tech Stack

- **Framework:** [Next.js 15](https://nextjs.org/) (App Router, Server Actions)
- **Language:** TypeScript
- **ORM & Database:** Prisma + PostgreSQL
- **State Management:** Zustand
- **API Caching/Fetching:** TanStack Query
- **UI Components:** shadcn/ui + TailwindCSS
- **Icons:** Lucide-react
- **Editor:** Monaco Editor
- **Auth:** Better Auth (GitHub + Google OAuth)
- **AI:** Google Gemini API

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Aditya24Kashyap/PostAPI.git
cd PostAPI
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root and add:

```env
# Local PostgreSQL connection
DATABASE_URL="postgresql://postgres:YOUR_PASSWORD@localhost:5432/postmanclone"

# Better Auth
BETTER_AUTH_SECRET=your_random_secret_string
BETTER_AUTH_URL=http://localhost:3000

# GitHub OAuth (from https://github.com/settings/developers)
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=

# Google OAuth (from https://console.cloud.google.com/apis/credentials)
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=

NEXT_PUBLIC_APP_URL=http://localhost:3000

# Google Gemini API key (from https://aistudio.google.com/apikey)
GOOGLE_GENERATIVE_AI_API_KEY=
```

> 💡 This project uses a **local PostgreSQL instance** (not Docker). Make sure PostgreSQL is installed and running on port `5432`, and that you've created a database named `postmanclone` before running migrations.

### 4. Setup Database
```bash
npx prisma migrate dev
```

### 5. Run the Development Server
```bash
npm run dev
```

App will be available at: [http://localhost:3000](http://localhost:3000)

Sign in at [http://localhost:3000/sign-in](http://localhost:3000/sign-in) using GitHub or Google.

---

## 📦 Project Structure

```
/app
  /(auth)          → Sign-in route
  /(workspace)     → Workspace-specific routes (requests, realtime)
  /api             → API routes (REST & WebSocket server actions)
  /invite          → Invite link pages
/components        → Reusable UI components
/modules           → Features (auth, workspace, collections, requests, realtime, invites, ai)
/lib               → Utilities (db, auth, env, ai-agents)
/prisma            → Database schema & migrations
```

---

## 🙏 Acknowledgements

This project was originally inspired by and built on top of the open-source [postman-clone](https://github.com/Aestheticsuraj234/postman-clone) by **Suraj** — huge thanks for the excellent foundation. This version (**PostAPI**) is my personal fork, set up and configured end-to-end as a learning project.

* **Postman** – for inspiring the core idea
* **Next.js & Vercel** – for providing a powerful fullstack framework
* **shadcn/ui** – for beautiful and accessible UI components
* **TanStack Query & Zustand** – for data and state management
* **Better Auth** – for a clean, simple authentication solution
* All open-source contributors & libraries used in this project 🙏

---

## 📜 License

This project is **MIT Licensed**.
Feel free to fork, contribute, and build your own features on top of it!