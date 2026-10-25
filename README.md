# Inkwell — Full-Stack Blog Platform
A responsive full-stack blog application with user registration/login, JWT authentication, private dashboards, create/edit/delete blog posts, search, categories and profile editing.

## Run locally
1. Install Node.js 20 or newer.
2. Open this folder in VS Code and terminal.
3. Run `npm install`.
4. Copy `.env.example` to `.env` (`copy .env.example .env` in Windows CMD).
5. Edit `.env` and set `JWT_SECRET` to a long random secret.
6. Run `npm start` and open http://localhost:3000.

The server creates `data/db.json` automatically. Passwords are hashed with bcryptjs. Never commit `.env` or real user data.

## GitHub
Create a public repository named `inkwell-blog-platform`, then run in this folder:
```
git init
git add .
git commit -m "Build Inkwell full-stack blog platform"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/inkwell-blog-platform.git
git push -u origin main
```
Replace `YOUR-USERNAME` with your GitHub username. If `origin` already exists, use `git remote set-url origin https://github.com/YOUR-USERNAME/inkwell-blog-platform.git`.

## Deployment
This project is a Node/Express server and uses a JSON file for storage. Deploy to Render as a Web Service with build command `npm install`, start command `npm start`, and environment variable `JWT_SECRET` set to a strong random value. Add persistent disk storage for the `data` directory if the chosen plan supports it; otherwise data may reset on redeploy/restart. For production, replace JSON storage with managed PostgreSQL. Vercel/Netlify need serverless adaptation and managed storage; this project is not a static-only site.

## API
`GET /api/health`, `POST /api/auth/register`, `POST /api/auth/login`, `GET/PUT /api/auth/me`, `GET /api/posts`, `GET /api/posts/mine`, `POST /api/posts`, `PUT /api/posts/:id`, `DELETE /api/posts/:id`.

## Production note
Learning project, not a production-ready service. Add rate limiting, email verification, password reset, additional security hardening, logging and a managed database before handling real users.
