<div align="center">
  <img src="client/src/assets/logo_big.svg" alt="QuickChat Logo" width="160" />

  # QuickChat

  <p>
    <strong>Realtime messaging built for modern teams</strong>
  </p>

  <p>
    <img src="https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js" alt="Node.js" />
    <img src="https://img.shields.io/badge/Express.js-5.x-000000?logo=express" alt="Express" />
    <img src="https://img.shields.io/badge/React-18.x-61DAFB?logo=react" alt="React" />
    <img src="https://img.shields.io/badge/Vite-5.x-646CFF?logo=vite" alt="Vite" />
    <img src="https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb" alt="MongoDB" />
    <img src="https://img.shields.io/badge/Socket.io-4.x-010101?logo=socket.io" alt="Socket.io" />
    <img src="https://img.shields.io/badge/Cloudinary-Media-3448C5?logo=cloudinary" alt="Cloudinary" />
    <img src="https://img.shields.io/badge/CI%2FCD-Ready-success" alt="CI/CD Ready" />
    <img src="https://img.shields.io/badge/Status-Production%20Ready-1E90FF" alt="Status" />
  </p>
</div>

> ⚡️ **QuickChat** is a production-grade communication platform showcasing enterprise engineering practices: a hardened Express API, a performant React/Vite SPA, resilient MongoDB persistence, and realtime Socket.IO messaging enriched with Cloudinary-powered media workflows. Built to impress technical leaders evaluating architecture fluency, extensibility, and operational readiness.

---

## 📌 Table of Contents

1. [Executive Summary](#-executive-summary)
2. [Key Concepts & Differentiators](#-key-concepts--differentiators)
3. [Feature Matrix](#-feature-matrix)
4. [Technology Stack](#-technology-stack)
5. [System Architecture](#-system-architecture)
6. [Repository Layout](#-repository-layout)
7. [Environment Setup](#-environment-setup)
8. [Development Workflow](#-development-workflow)
9. [Usage Scenarios](#-usage-scenarios)
10. [API Surface](#-api-surface)
11. [.env Configuration](#env-configuration)
12. [Deployment to Vercel](#-deployment-to-vercel)
13. [Testing Strategy](#-testing-strategy)
14. [CI/CD Blueprint](#-cicd-blueprint)
15. [Contribution Standards](#-contribution-standards)
16. [Strategic Roadmap](#-strategic-roadmap)
17. [Troubleshooting Knowledge Base](#-troubleshooting-knowledge-base)
18. [License](#license)
19. [Acknowledgements](#acknowledgements)

---

## 🧭 Executive Summary

- **Mission:** Deliver a polished, realtime chat experience with secure identity flows, intuitive UI, and rock-solid infrastructure.
- **Audience:** Modern product teams and engineering leaders assessing system design maturity.
- **Value:** Demonstrates domain-driven layering, cloud-native configuration, and deployment readiness across environments.
- **Outcome:** Rapid feature iteration, predictable scaling characteristics, and exemplary developer ergonomics.

---

## 🎯 Key Concepts & Differentiators

| Concept | Description | Why It Matters |
|---------|-------------|----------------|
| **Domain-driven modularization** | Controllers, services, models, and routes isolated per domain boundary | Accelerates feature work, simplifies testing |
| **Context-centric front-end state** | Auth & Chat providers decouple concerns, memoized selectors avoid unnecessary renders | Predictable UI behaviour under load |
| **Realtime-first design** | Socket.IO layer complements REST for event-driven updates | Continuous sync without poll storms |
| **Zero-trust authentication** | JWT middleware verifies every protected call, bcrypt secures credentials | Enterprise-grade security posture |
| **Cloud-native configurability** | Environment variables govern secrets & endpoints | Enables multi-environment parity |
| **Operational visibility** | Mongo connection lifecycle logging, centralized error surfacing | Faster root-cause analysis |

---

## ✨ Feature Matrix

- ✅ Secure onboarding with encrypted credential storage.
- ✅ JWT-based login/logout with refresh-friendly patterns.
- ✅ Profile management and avatar uploads via Cloudinary CDN.
- ✅ One-to-one messaging with optimistic UI updates.
- ✅ Message editing, deletion, and server-side validation.
- ✅ Socket.IO events for instantaneous delivery and presence awareness.
- ✅ Responsive, accessibility-conscious interface ready for theming.
- ✅ Error/Loading surfaces unified through global handlers and toasts.

---

## 🛠️ Technology Stack

| Layer | Technology | Role | Highlights |
|-------|------------|------|-----------|
| Frontend | React 18, Vite, Context API | SPA rendering, routing, state orchestration | ESM-native builds, blazing dev feedback |
| Styling | CSS Modules & Global Styles | Component styling, responsive layouts | Easily swappable with Tailwind/Chakra |
| Backend | Node.js 18+, Express 5 | REST API, socket gateway | Nodemon for DX, modular routes |
| Persistence | MongoDB Atlas, Mongoose 8 | Schemas, validation, lifecycle hooks | Connection utility handles retries & logging |
| Auth | jsonwebtoken, bcryptjs | JWT issuance & verification | Hardened middleware & password hashing |
| Realtime | Socket.IO 4 | Bidirectional messaging | Room-based events, typing indicators ready |
| Media | Cloudinary SDK | Asset upload & transformation | CDN caching, signed uploads extendable |
| Tooling | ESLint (flat config), dotenv, Nodemon | Quality gates & local productivity | Extensible to Husky/Prettier |

---

## 🧩 System Architecture

![image alt](https://github.com/Koushik-Biswas/Quick-Chat/blob/main/Screenshot%202025-10-04%20210535.png?raw=true)

## 🗂️ Repository Layout

```
QuickChat/
├─ client/
│  ├─ src/
│  │  ├─ assets/            # Optimized visuals & icons
│  │  ├─ components/        # Reusable UI building blocks
│  │  ├─ context/           # Auth/Chat providers, reducers, hooks
│  │  ├─ lib/               # Frontend utilities & helpers
│  │  ├─ pages/             # Route-level screens (Home/Login/Profile)
│  │  └─ App.jsx            # Application shell & routing entry
│  ├─ public/               # Static assets served verbatim
│  ├─ vite.config.js        # Vite build & dev server setup
│  └─ package.json          # Frontend scripts & dependencies
│
├─ server/
│  ├─ controllers/          # Domain orchestration (user/message)
│  ├─ lib/
│  │  ├─ db.js              # Mongo connection lifecycle management
│  │  └─ cloudinary.js      # Cloudinary client configuration
│  ├─ middleware/           # JWT authentication guard
│  ├─ models/               # Mongoose schemas & statics
│  ├─ routes/               # REST endpoints grouped by resource
│  ├─ utils.js              # Shared backend helpers
│  ├─ server.js             # Express bootstrap + Socket.IO wiring
│  └─ package.json          # Backend scripts & dependencies
│
└─ README.md
```

---

## 🔧 Environment Setup

1. **Clone**
   ```bash
   git clone https://github.com/<your-org>/QuickChat.git
   cd QuickChat
   ```

2. **Install**
   ```bash
   cd server && npm install
   cd ../client && npm install
   ```

3. **Configure**
   - Create `server/.env` and `client/.env` as described in [.env configuration](#env-configuration).
   - Secrets stay local; `.gitignore` already protects them.

4. **Run locally**
   ```bash
   # Backend
   cd server
   npm run server

   # Frontend (new terminal)
   cd client
   npm run dev
   ```

5. **Verify**
   - API default: `http://localhost:5000`
   - SPA default: `http://localhost:5173`

---

## 🧪 Development Workflow

- **Branching:** `main` for production, short-lived feature branches (`feature/<name>`), ensure rebase before merge.
- **Code Quality:** ESLint flat config enforces consistency; extend with Prettier or custom rules.
- **Commits:** Adopt Conventional Commits to power automated changelogs (`feat:`, `fix:`, `chore:`).
- **Pull Requests:** Include context, screenshots for UI adjustments, and test evidence.
- **Reviews:** Require at least one reviewer; CI must pass before merge.

---

## 🚀 Usage Scenarios

### 1. Authentication Lifecycle
+- Register via `/api/auth/register`.
+- Login through `/api/auth/login`.
+- JWT stored client-side (HTTP-only cookie recommended in production).
+- Auth middleware ensures every protected endpoint verifies identity.

### 2. Messaging Workflow
+- Authenticated client establishes Socket.IO session.
+- Message submission hits `/api/messages` (REST) with optimistic UI updates.
+- Socket broadcasts (`message:new`, `message:update`) keep participants synchronized.

### 3. Profile & Media Management
+- Avatar uploads funnel through Cloudinary integration.
+- Cloudinary response persisted on user document, cached within `AuthContext`.
+- Assets benefit from CDN delivery & transformation pipelines.

---

## 📡 API Surface

| Endpoint | Method | Description | Auth | Controller |
|----------|--------|-------------|------|------------|
| `/api/auth/register` | POST | Create new user account | ❌ | `userController.registerUser` |
| `/api/auth/login` | POST | Authenticate credentials & issue JWT | ❌ | `userController.loginUser` |
| `/api/users/me` | GET | Retrieve authenticated user profile | ✅ | `userController.getProfile` |
| `/api/users/me` | PUT | Update profile details & avatar | ✅ | `userController.updateProfile` |
| `/api/messages` | GET | Fetch conversation by participant | ✅ | `messageController.getMessages` |
| `/api/messages` | POST | Send a new message | ✅ | `messageController.sendMessage` |
| `/api/messages/:id` | PATCH | Edit existing message | ✅ | `messageController.updateMessage` |
| `/api/messages/:id` | DELETE | Delete message | ✅ | `messageController.deleteMessage` |

**Socket Events**

| Event | Direction | Payload | Purpose |
|-------|-----------|---------|---------|
| `connection` | Client → Server | JWT token | Authenticate socket handshake |
| `message:new` | Server → Client | Message DTO | Broadcast newly created message |
| `message:update` | Server → Client | Message DTO | Reflect edits/deletions |
| `user:typing` | Bidirectional | `{ userId, roomId }` | Typing indicators |

---

## 🔐 .env Configuration

> 💡 Keep secrets out of source control. Populate platform dashboards (Vercel, Render) with identical keys for production.

### `server/.env`

```
PORT=5000
JWT_SECRET=your-secure-secret
MONGODB_URI=mongodb+srv://<user>:<password>@cluster.mongodb.net
CLOUDINARY_CLOUD_NAME=<cloud-name>
CLOUDINARY_API_KEY=<api-key>
CLOUDINARY_API_SECRET=<api-secret>
```

### `client/.env`

```
VITE_BACKEND_URL=http://localhost:5000
```

Update `VITE_BACKEND_URL` to your deployed API domain before shipping.

---

## ☁️ Deployment to Vercel

### Frontend (React/Vite)
+- **Root Directory:** `client`
+- **Build Command:** `npm install && npm run build`
+- **Output Directory:** `dist`
+- **Environment Variable:** `VITE_BACKEND_URL=https://<production-api>`

### Backend Options

| Option | Description | Key Steps |
|--------|-------------|-----------|
| **Vercel Serverless** | Wrap Express via `@vercel/node` | Create `api/index.js`, update `vercel.json`, deploy |
| **Render / Railway / Fly.io** | Dedicated Node runtime | Root: `server`, Build: `npm install`, Start: `npm start`, choose region near MongoDB Atlas |

### Post-deploy Checklist
+- Update frontend env with production API.
+- Whitelist deployment IP in MongoDB Atlas.
+- Validate Cloudinary upload from new origin.
+- Smoke-test auth & messaging flows end-to-end.

---

## 🧪 Testing Strategy

| Tier | Tooling | Coverage Goals |
|------|---------|----------------|
| Unit | Vitest / Jest | Utilities, hooks, controller logic |
| Integration | Supertest, React Testing Library | REST contracts, DOM flows |
| End-to-End | Playwright / Cypress | Critical journeys (auth, messaging, profile) |
| Performance (future) | Artillery / k6 | Socket throughput, API latency under load |

Command templates:

```bash
# Frontend tests (client/)
npm run test

# Backend tests (server/)
npm run test
```

Enhance with coverage thresholds and pre-commit hooks as suite matures.

---

## 🔄 CI/CD Blueprint

1. **GitHub Actions Pipeline**
   - Triggers on PRs & pushes to `main`.
   - Jobs: checkout → install client/server deps → lint → test → build.
   - Cache npm directories for faster runs.

2. **Quality Gates**
   - Enforce ESLint.
   - Optional: add Prettier & commit hooks via Husky.
   - Set minimum coverage (e.g., 80%).

3. **Automated Deploys**
   - Connect Vercel/Render to GitHub for zero-touch deployments.
   - Use branch protection with required reviews + green CI.

4. **Observability**
   - Integrate log aggregation (Logtail/New Relic).
   - Add error tracking (Sentry/Rollbar) & uptime monitoring.

---

## 🤝 Contribution Standards

1. Fork repository, branch from `main` (`feature/<slug>`).
2. Follow Conventional Commits and keep commits focused.
3. Update documentation and add tests when altering behaviour.
4. Submit PR with:
   - Motivation & summary.
   - Screenshots/GIFs for UI changes.
   - Test results or coverage report.
5. Address review feedback swiftly; ensure CI remains green.

---

## 🗺️ Strategic Roadmap

- [ ] Group chats, threaded conversations, and channel metadata.
- [ ] Presence indicators (online/offline, last seen) via Redis or in-memory cache.
- [ ] Full-text message search leveraging MongoDB Atlas Search.
- [ ] Push notifications through Firebase Cloud Messaging.
- [ ] Admin tooling for moderation, analytics, and usage insights.
- [ ] Analytics dashboard with engagement KPIs.

---

## 🩺 Troubleshooting Knowledge Base

| Symptom | Diagnosis | Resolution |
|---------|-----------|------------|
| Frontend 401 errors | Missing/expired JWT | Re-authenticate, check token storage & `JWT_SECRET` parity |
| MongoDB timeouts | Network/IP not whitelisted | Add deployment IP in Atlas, verify credentials |
| Cloudinary upload fail | Invalid keys or large file | Regenerate keys, adjust upload presets |
| Socket events silent | JWT missing in handshake | Ensure client passes token when connecting |
| Vite env undefined | Dev server caching old env | Restart `npm run dev`, prefix keys with `VITE_` |
| CORS errors | Backend not allowing origin | Enable `cors` with correct origin list |

---

## License

Distributed under the [MIT License](LICENSE).

Copyright (c) 2025-2026 Koushik Biswas.

---

## 🙏 Acknowledgements

- MongoDB Atlas, Cloudinary, Socket.IO communities for robust ecosystems.
- Design inspiration sourced from leading collaboration platforms.
- Crafted with care to highlight clean architecture and engineering excellence.

---

<div align="center">
  <sub>“Quality is not an act, it is a habit.” — Aristotle</sub>
</div>
