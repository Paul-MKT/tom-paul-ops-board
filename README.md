Tom & Paul — Ops Board
======================

This archive contains a ready-to-deploy **Next.js** app (React + Tailwind) for the "Tom & Paul — Ops Board".
It includes:
- Kanban board, Agenda, Suppliers list, Overview (single-file main component).
- Drag & Drop (dnd-kit) prepared integration points.
- Realtime sync via Supabase (client + example hook).
- SQL schema to create tables in Supabase.
- Import script to insert the retro-planning events.
- Instructions to run locally and deploy on Vercel.

IMPORTANT: I cannot host the app for you from this chat. To run the app online you must:
1) Create a Supabase project (free tier is fine).
2) Run the SQL schema in Supabase SQL editor.
3) Copy your SUPABASE_URL and SUPABASE_ANON_KEY into `.env.local`.
4) Deploy the project to Vercel (instructions below).

Files included:
- package.json
- next.config.js
- tailwind.config.js
- postcss.config.js
- tsconfig.json
- .env.example
- /src/pages/_app.tsx
- /src/pages/index.tsx  (main app - Tom & Paul Ops Board)
- /src/lib/supabaseClient.ts
- /src/hooks/useRealtimeSync.ts
- /sql/setup.sql
- /scripts/import-retro.js (node script to import retro-planning into Supabase)
- README.md (this file)

Quick start (local)
-------------------
1. Unzip the archive.
2. `cd tom-paul-ops`
3. `npm install`
4. Create a Supabase project (https://app.supabase.com) and run the SQL in `/sql/setup.sql`.
5. Create `.env.local` with:
   NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
6. `npm run dev`
7. Open http://localhost:3000

Deploy to Vercel
----------------
1. Push the project to a GitHub repo.
2. Import the repo on Vercel (https://vercel.com/new).
3. In Vercel Project Settings -> Environment Variables, add:
   NEXT_PUBLIC_SUPABASE_URL
   NEXT_PUBLIC_SUPABASE_ANON_KEY
4. Deploy.

Security notes
--------------
- For quick testing you can use the anon key, but for production enable Supabase Auth and RLS policies.
- Do not publish your anon key in public repos.

If you'd like, I can:
- Walk you live (step-by-step) while you create the Supabase project.
- Provide the exact SQL for RLS policies and an Auth flow (magic link/email).
- Help you add user authentication for Tom & Paul only.