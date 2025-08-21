# RecipeShare Backend

A Node.js/Express backend with MongoDB (Mongoose), JWT auth, and CRUD APIs for recipes.

## Quick Start

```bash
npm install
cp .env.example .env
# Edit .env
npm run dev
```

The API defaults to `http://localhost:4000`.

## Endpoints (summary)

- **Auth**
  - `POST /api/auth/register` { name, email, password }
  - `POST /api/auth/login` { email, password }
  - `GET /api/auth/me` (Bearer token) – current user

- **Recipes**
  - `POST /api/recipes` (auth) – create
  - `GET /api/recipes` – list with pagination & search
  - `GET /api/recipes/:id` – get one
  - `PATCH /api/recipes/:id` (auth & owner) – update
  - `DELETE /api/recipes/:id` (auth & owner) – delete

## Project Structure

```
src/
  app.js
  server.js
  config/db.js
  controllers/
  middleware/
  models/
  routes/
  utils/
```

## Notes
- Requires Node 18+.
- Add production CORS origins in `.env` or change in `src/app.js` as needed.
- This starter avoids file uploads to keep it simple; you can add `multer` or object storage later.
