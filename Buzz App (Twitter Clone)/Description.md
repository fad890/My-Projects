# 🐝 The Buzz - CSE 216 Software Engineering Project  
**Semester**: Spring 2025  
**Institution**: Lehigh University  
**Team Roles**: Project Manager, Backend Developer, Web Developer, Mobile Developer, Admin Developer  
**My Roles (Rotated)**: Web, Admin, Project Manager
---

## 🚦 Project Overview

_The Buzz_ is a social ideation platform built with a full-stack architecture supporting mobile and web interfaces. Over Phases 2 and 3, we introduced secure **OAuth-based authentication**, interactive **voting and commenting**, **profile management**, and robust **admin tooling**. The app supports **up-votes**, **down-votes**, **comments**, and **user personalization**, all accessible only to **Lehigh-authenticated users**.

---

## 📌 Phase 2 Summary – Authentication, Voting, and Profiles

### ✅ Goals

- Migrate to authenticated-only experience using Google Identity Services
- Replace “like” system with **up/down vote mechanics**
- Add **text-only comments** to posts
- Enable users to **edit profiles** (GI, SO, note fields)
- Update front-end and back-end to match

### 🔐 Authentication (OAuth 2.0)

- Implemented using **Google Identity Services (GIS)**
- Only accessible by **@lehigh.edu** accounts
- Session handling with secure random tokens (no password storage)

### 🧠 Voting State Machine

| Action                    | Result         |
|--------------------------|----------------|
| Neutral → Upvote         | Upvoted        |
| Upvote → Upvote          | Neutral        |
| Downvote → Downvote      | Neutral        |
| Upvote → Downvote        | Downvoted      |
| Downvote → Upvote        | Upvoted        |

Votes are **not publicly visible**, but users can view their own.

### 🧾 Profile Fields

- Full name  
- Email (read-only)  
- Gender Identity (GI)  
- Sexual Orientation (SO)  
- Note (editable)  

Reference: [CDC Guidance](https://www.cdc.gov/hiv/clinicians/transforming-health/health-care-providers/collecting-sexual-orientation.html)

### 📱 Web & Mobile Frontends

- GIS Login with FedCM enabled
- Voting & commenting on ideas
- Profile pages (private & public)
- Flutter for mobile
- Responsive and accessible UI

### 🛠 Admin Tools

- Create, update, delete DB tables (users, votes, ideas, comments)
- Prepopulate data for testing
- Invalidate users or ideas
- Create PostgreSQL views to simplify queries

### 🧪 Testing (Phase 2)

- Unit testing across backend routes and state transitions
- UI logic testing on mobile and web apps
- Use of Flutter test framework for mobile

---

## 🛠 Phase 3 Summary – Final Integration and Artifacts

### ✅ Phase Goals

- Polish all features from Phase 2
- Complete formal documentation and testing
- Add diagrams, ERDs, test plans, route maps, and state machines
- Prepare live or recorded demo

### 🧑‍🤝‍🧑 Authenticated User Features

- Login via Lehigh OAuth
- Post, view, edit, delete ideas
- Add/edit comments (not deletable)
- Like, dislike, neutralize vote
- View/update own profile
- Upload files and link content

### 🔐 Admin Capabilities

- Access and manipulate all tables
- Insert/update/delete records
- Search messages by keyword
- Remove inappropriate content

---

## 📡 Backend API Routes

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/users/login` | Authenticate user with OAuth |
| `GET`  | `/users/{userId}` | View user profile |
| `PUT`  | `/users/{userId}` | Update profile |
| `GET`  | `/ideas` | Get all ideas |
| `POST` | `/ideas` | Create new idea |
| `PUT`  | `/ideas/{id}` | Edit an idea |
| `DELETE` | `/ideas/{id}` | Delete an idea |
| `PUT` | `/ideas/{id}/like` | Like/dislike toggle |
| `GET` | `/likevotes/{ideaId}/{userId}` | Get vote status |
| `POST` | `/likevotes` | Cast/modify vote |
| `GET` | `/ideas/{id}/comments` | Fetch comments |
| `POST` | `/ideas/{id}/comments` | Add comment |
| `PUT` | `/comments/{id}` | Edit comment |

---

## 🗂️ Database (ER Diagram Overview)

### Entities:

- **Users**: `user_id`, `username`, `email`, `bio`, `gender`  
- **Ideas**: `idea_id`, `content`, `user_id`, `like_count`, `file`  
- **Votes**: `user_id`, `idea_id`, `isLiked`, `isDisliked`  
- **Comments**: `comment_id`, `idea_id`, `content`, `user_id`, `file`  

---

## 📈 Diagrams (Phase 3)

- ✅ System Architecture Diagram (cloud vs. local components)  
- ✅ ER Diagram  
- ✅ State Machines:
  - User interactions
  - Idea object lifecycle  
- ✅ UI Mockups for web & mobile  
- ✅ Route Mapping & JSON format descriptions

---

## 🧪 Testing Overview (Phase 3)

### Unit Tests Described for:
- Table creation & deletion  
- Prepopulating records  
- Invalidating users or ideas  
- Coverage checks for:
  - OAuth login
  - Voting logic
  - Comments
  - Profile updates

---