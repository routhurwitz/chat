# chat
like telegram text message lite
**You are a Senior Full-Stack Architect & CTO with 10+ years experience building production-grade Nuxt applications. Generate a complete, flawless, production-ready, mobile-first private text-only chat application using the latest Nuxt 4 (stable release as of 2026).**

**Project Name:** pv-text-chat-nuxt4-mobile **Exact Tech Stack (Nuxt 4 best practices):**

- Nuxt 4 (latest stable) + Nitro server (latest)
- TypeScript (strict mode, full type safety)
- Tailwind CSS 4 (dark mode only, beautiful Telegram Mobile dark theme)
- Pinia (with pinia-plugin-persistedstate if needed)
- Drizzle ORM 0.3x + better-sqlite3 (single file data/db.sqlite)
- JWT authentication (httpOnly cookies + refresh token support)
- Lucide-vue-next icons only (all self-contained)
- Zod for all validation
- No external UI libraries, no CDN, everything bundled

**Project Structure (Nuxt 4 official app/ directory – mandatory):**

- Use the new Nuxt 4 default structure with app/ as root for pages, components, composables, layouts, middleware.
- Server code in server/ (api/, routes/, middleware/, utils/).
- Database in lib/db/, auth logic in lib/auth/, types in types/.

**Core Features (minimal & exactly as requested – nothing more):**

- **Authentication:**
    - Register: username (unique), password (bcrypt hashed), full name, optional referralCode (stored but no extra logic)
    - Login: username + password
    - Protected routes with Nuxt 4 middleware
    - Logout (clear cookies)
    - GET /api/auth/me
- **Database Schema (Drizzle – clean & typed):**
    - users: id, username (unique), passwordHash, name, lastSeen, referralCode, createdAt
    - chats: id, user1Id, user2Id, createdAt (private 1-to-1 only)
    - messages: id, chatId, senderId, text (string only), createdAt, seen (boolean)
- **Backend API (Nitro + Nuxt 4 best practices):**
    - Clean, typed event handlers in server/api/
    - Optional controllers in server/controllers/ for separation
    - Proper error handling with h3 and Nuxt 4 error utilities
    - Rate limiting on auth routes (using nitro)
    - All endpoints:
        - POST /api/auth/register
        - POST /api/auth/login
        - POST /api/auth/logout
        - GET /api/auth/me
        - GET /api/users/search?q=
        - GET /api/chats
        - GET /api/chats/:chatId/messages (limit 50 + simple offset pagination)
        - POST /api/chats/:chatId/messages (text only)
        - POST /api/chats/new (create or get existing PV chat)
        - PATCH /api/messages/mark-seen
- **Frontend UI (Mobile-First – Telegram Mobile style):**
    - Fully responsive, mobile-first Tailwind design.
    - On mobile: Chat list as default screen → tapping chat opens full-screen chat view (use Nuxt 4 route navigation + back button).
    - On larger screens: Optional side-by-side (sidebar + chat) but mobile experience is priority.
    - Login/Register: centered dark cards, touch-friendly.
    - Chat list: logo, search, list with avatar placeholder, name, last message, time, unread badge.
    - Chat view: header (back + name + lastSeen), scrollable bubbles (right=#2481cc for mine, left=gray for others), fixed bottom input (text only) + send.
    - User search modal/floating button to start new PV chat.
    - Optimistic sending, auto-scroll to bottom.
    - Basic seen status (double checkmark).
    - **Text messages only** – no files, images, emojis picker, reactions, groups, channels, voice, etc.

**CTO-Level Requirements (make it flawless):**

- Use Nuxt 4 new app/ directory structure and all modern patterns (auto-imports, server composables, defineNuxtConfig with routeRules).
- Full TypeScript strict typing everywhere (including API responses).
- Secure: bcrypt hashing, httpOnly cookies, Zod validation, no sensitive data in client.
- Performance: lazy loading where possible, proper caching with useAsyncData / useFetch in Nuxt 4 style.
- Clean architecture: separate lib/db, lib/auth, composables for chat logic.
- Environment variables: JWT_SECRET, DB path (with .env.example).
- Drizzle migrations + studio ready.
- Simple seeder script (4-5 demo users + sample messages) – run with npm run db:seed.
- npm scripts: dev, build, start, db:generate, db:push, db:studio, db:seed, lint, typecheck.
- Well-commented, professional, maintainable code.
- Dark theme only, pixel-perfect Telegram Mobile dark UI (colors, spacing, bubbles, typography).
- Persian RTL support prepared (but default English labels).

**Output:** Generate the **complete ready-to-run Nuxt 4 project** with every single file needed:

- package.json (with exact Nuxt 4 + Drizzle + dependencies)
- nuxt.config.ts (optimized for Nuxt 4)
- tailwind.config.ts
- drizzle.config.ts
- All schema, migrations, seed
- All API routes & controllers
- All pages, components, composables, middleware, stores
- .env.example
- README with setup instructions

Make this the highest quality, production-grade code a CTO would approve for a real startup MVP. Start generating the full codebase now.
