# QuizSphere

MERN assessment platform with real-time tab-switch monitoring and offline auto-recovery.

## Run locally
1. Install Node.js (LTS) from https://nodejs.org
2. Backend:
   cd backend
   copy .env.example to .env and fill MONGO_URI and JWT_SECRET
   npm install
   npm run dev
3. Frontend (new terminal):
   cd frontend
   npm install
   npm run dev
4. Open http://localhost:5173

## Deploy to Render
This project is set up as a single Render web service: Render builds the React app and the Express server serves it together with the API.

1. Push the contents of this `quizsphere` folder to a GitHub repository, with `render.yaml` at the repository root. Do not upload `.env` files or `node_modules`.
2. In Render, choose **New +** → **Blueprint**, connect the GitHub repository, and deploy the `quizsphere` Blueprint.
3. In the service's environment settings, set `MONGO_URI` to your MongoDB Atlas connection string. Render generates `JWT_SECRET` automatically.
4. In MongoDB Atlas, allow connections from Render (for a quick setup, add `0.0.0.0/0` to the project's network access list) and ensure the database user and password in the connection string are correct.
5. Wait for the deployment and open the `onrender.com` URL shown on the service. You can check the API at `/api/health`.

The first deployment can take a few minutes. Render's free web service may spin down when idle and take a little while to wake up.

## Folders
- backend/  Express + MongoDB API (auth, questions, quizzes, attempts)
- frontend/ React + Vite + Tailwind web app
- sample_questions.csv  ready file for the bulk upload feature

Never upload backend/.env to GitHub (it is already in .gitignore).
