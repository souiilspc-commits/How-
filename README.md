# 🎵 TikShare (تيك شير)

A TikTok-inspired, mobile-first web application for sharing images and MP3 audio tracks with real-time feeds, user messaging, and profile management. Built using modern CSS styling, vanilla JavaScript, and an asynchronous REST API bridge.

---

## 🌟 Key Features

* **TikTok-Style Vertical Feed:**
  * Vertical scroll-snapping feed optimized for mobile viewports.
  * Responsive image rendering with native containment.
  * Animated spinning vinyl disc player for MP3 audio files with custom playback controls.
* **Direct Media Downloads:**
  * One-click download overlay (`⬇`) for saving both images and audio tracks directly.
* **Authentication & User Management:**
  * Modal authentication gate supporting both user Login and Registration.
  * Token-based authorization saved securely in local browser storage (`localStorage`).
* **Content Upload System:**
  * Bottom-sheet modal interface for publishing local image and MP3 files.
  * Custom media title validation.
* **Profile Management:**
  * Displays personal post counters and user information.
  * Capability to delete published posts and un-link media storage assets.
* **Direct Messaging Platform:**
  * Real-time direct chat interface with user search functionality.
  * Dynamic unread message count badges.
  * Per-user conversation tracking and auto-scrolling chat bubbles.
* **Dark Theme & Mobile Optimization:**
  * Modern dark palette styled via dynamic CSS variables.
  * Dynamic support for mobile safe area insets.

---

## 🛠️ Technology Stack

| Technology | Role |
| :--- | :--- |
| **CSS3** | Layouts, CSS Variables, Snap Scrolling, Keyframe Animations, Glassmorphism |
| **Vanilla JavaScript (ES6+)** | Dynamic state management, event polling, asynchronous API integration |
| **REST API** | Backend service handling persistent document collections and binary uploads |

---

## 🔌 API Endpoints Reference

The client application communicates with a structured JSON backend service:

### Authentication & Profiles
* `POST /api/login` — Authenticates existing user credentials.
* `POST /api/register` — Registers a new user account.
* `GET /api/me` — Retrieves current session user info.
* `GET /api/users?ids=...` — Resolves user display names by IDs.
* `GET /api/users?q=...` — Searches platform users by keyword.

### Document Collections (`/api/col` & `/api/doc`)
* `GET /api/col/posts` — Fetches global posts across all users.
* `GET /api/col/msgs` — Fetches direct message threads.
* `GET /api/doc/posts/{uid}` — Fetches posts authored by a specific user.
* `PUT /api/doc/posts/{uid}` — Updates post list state for a user.
* `GET /api/doc/msgs/{uid}` — Retrieves message history for a user.
* `PUT /api/doc/msgs/{uid}` — Appends new direct messages to conversation state.

### Media Asset Storage
* `POST /api/upload?t={mimeType}` — Uploads binary audio or image files to storage.
* `DELETE /api/file/{id}` — Permanently removes media assets from storage.

---

## 🚀 Getting Started

1. Set your backend base URL dynamically in your environment configuration:
   ```javascript
   window.API_BASE = '[https://your-backend-api.com](https://your-backend-api.com)';
   
