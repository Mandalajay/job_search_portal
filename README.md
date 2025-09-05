# JobPortal

A full-stack job application portal with a **Node.js/Express** backend and a **Vite + React + Tailwind CSS** frontend.  
Users can register, log in, and browse job listings. Recruiters can manage jobs and companies.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Scripts](#scripts)
- [Notes & Tips](#notes--tips)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- 🔐 JWT-based authentication (login/signup)
- 👤 User roles (student/job-seeker) vs. recruiter
- 📋 Browse, create, update, and manage jobs
- 🏢 Company management for recruiters
- ☁️ Optional Cloudinary integration for media
- ⚡ Fast dev experience with Vite

---

## Tech Stack

**Frontend:** Vite, React, Tailwind CSS  
**Backend:** Node.js, Express  
**Database:** MongoDB (Atlas or self-hosted)  
**Media (optional):** Cloudinary

---

## Prerequisites

- **Node.js** (includes npm): https://nodejs.org/  
- **npm** or **Yarn**  
- **MongoDB connection string** (e.g., MongoDB Atlas)  
- *(Optional)* **Cloudinary** account for media uploads

---

## Getting Started

### Backend Setup

The backend is built using **Node.js**, **Express**, and **MongoDB**.

1) Navigate to the backend directory:

```bash
cd backend
```

2) Install dependencies:

```bash
npm install
# or
yarn install
```

3) Create a `.env` file in `backend/` and add the required variables (see [Environment Variables](#environment-variables)).

> Generate a strong `SECRET_KEY` via:
>
> ```bash
> node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
> ```
>
> Get your Cloudinary credentials from your Cloudinary dashboard.

4) Start the backend dev server:

```bash
npm run dev
# or
yarn dev
```

The server should now be running locally (typically on **http://localhost:5000**).

---

### Frontend Setup

The frontend uses **Vite**, **React**, and **Tailwind CSS**.

1) Navigate to the frontend directory:

```bash
cd frontend
```

2) Install dependencies:

```bash
npm install
# or
yarn install
```

3) Start the frontend dev server:

```bash
npm run dev
# or
yarn dev
```

The frontend will be available at **http://localhost:5173** (or another port if 5173 is in use).

---

## Environment Variables

Create a `.env` file **inside the `backend/` folder** with the following keys:

```env
DB_CONN_STRING=
CLOUDINARY_HOST_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET= 
SECRET_KEY=

```

> ❗ Do **not** commit `.env` files to version control. Ensure `.gitignore` includes `.env`.

---

## Project Structure

```text
JobPortal/
├─ backend/
│  ├─ controllers/
│  ├─ middlewares/
│  ├─ models/
│  ├─ routes/
│  ├─ utils/
│  ├─ package.json
│  ├─ .env
│  ├─ .gitignore
│  └─ server.js
│
├─ frontend/
│  ├─ public/
│  ├─ src/
│  ├─ package.json
│  └─ vite.config.js
│
├─ README.md
└─ .gitignore
```

---

## Usage

1. Start both **backend** and **frontend** dev servers.
2. Open the app in your browser (frontend URL, e.g., `http://localhost:5173`).
3. **Register** a new account or **log in** with existing credentials.
4. As a **student/job-seeker**, browse and view job listings.  
   As a **recruiter**, create and manage jobs and company profiles.

---

## Scripts

From `backend/`:

```bash
npm run dev     # starts the backend in development mode
```

From `frontend/`:

```bash
npm run dev     # starts the Vite dev server
```

*(Your `package.json` may include additional scripts such as `build` or `start`.)*

---

## Notes & Tips

- If your frontend and backend run on different ports, ensure API requests point to the correct backend base URL.  
  > With Vite, you can use environment variables like `VITE_API_BASE_URL` (in `frontend/.env`) and reference via `import.meta.env.VITE_API_BASE_URL`.
- For Cloudinary usage, verify your credentials and integration code paths (upload endpoints, signed uploads, etc.).
- Use a robust MongoDB Atlas connection string (with proper IP allow-listing or VPC peering as needed).

---

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a PR.

---

## License

Add your preferred license (e.g., MIT) and include a `LICENSE` file in the project root.
