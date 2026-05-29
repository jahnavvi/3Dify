# 3Dify
Turn 360° videos into realistic 3D models.

---

<div align="center">
  <img src="docs/gallery.gif" width="48%" alt="Gallery" />
  &nbsp;
  <img src="docs/model.gif" width="48%" alt="Model viewer" />
</div>

## Overview

3Dify lets you upload a 360° video of any object and get back a downloadable 3D model that is ready to preview in-browser or send straight to a 3D printer. No expensive scanners or manual setups required.

Traditional 3D modeling is tedious. Photogrammetry workflows often require uploading 100+ carefully staged photos of a single object just to get a usable model. With 3Dify, you record a short video, upload it, and your model is ready. The backend handles the reconstruction using Gaussian splatting and mesh processing, and the result is stored in Firebase for you to preview and download instantly.

---

## My Contributions

I worked as a full-stack developer on a team of three, with primary ownership of the frontend. I was involved across the entire stack. From the React UI down to the Flask API layer and cloud infrastructure.

- Architected and built the full React/Vite/Tailwind frontend including drag-and-drop upload, real-time processing state, and responsive layout
- Integrated Three.js for interactive in-browser 3D model rendering and preview
- Implemented Firebase Authentication for user accounts and model galleries
- Designed and connected the REST API interface between the React frontend and Flask backend
- Understood and worked within the Flask backend architecture, including the blueprint structure, API routing, and mock mode for local development
- Built the Projects page for tracking and managing past scans

---

## Tech Stack

### Frontend
- **React** — UI library
- **Vite** — Build tool
- **Tailwind CSS v4** — Utility-first styling
- **Three.js** — In-browser 3D model viewer

### Backend
- **Flask** — Python web framework
- **REST API** — Custom endpoints for video upload and model retrieval

### Cloud / Database
- **Firebase** — Authentication, Firestore (database), and Cloud Storage

---

## Features

- Upload a 360° video of any object
- Backend processes the video into a textured 3D model
- Preview the model interactively in-browser with Three.js
- Download the completed model as a `.zip`
- User accounts with personal model galleries
- Projects page to track and manage your scans

---

## Project Structure

```
Aztech/
├── 3Dify/                  # React + Vite frontend
│   ├── src/
│   │   ├── components/     # ModelViewer, ModelThumbnail, UploadVideo
│   │   ├── pages/          # LandingPage, CreatePage, ProjectsPage, GalleryPage
│   │   ├── services/       # Firebase scan helpers
│   │   └── context/        # AuthContext
│   └── backend/            # Flask backend
│       ├── blueprints/     # API route handlers
│       └── main.py         # App entry point
```

---

## Getting Started

### Prerequisites
- Node.js + npm
- Python 3.10+
- Firebase project with Firestore and Storage enabled

### 1. Run Frontend

```bash
cd 3Dify
npm install
npm run dev
```

### 2. Run Backend

```bash
cd 3Dify/backend
source venv/bin/activate
python3 main.py
```

> Mock mode: set `MOCK_MODE = True` in `blueprints/kiri.py` to simulate the full pipeline without making external API calls.

### 3. Firebase Setup

```bash
firebase login
firebase init
firebase deploy
```

### 4. Test Auth (Optional)

Uncomment `connectAuthEmulator(auth, "http://localhost:9099");` in the Firebase config, then:

```bash
firebase emulators:start
```

---

## Team

Built by Team Aztech — Jahnavi Panchal, Matthew Tran, Santiago Verdugo

---

## Future Plans

- Add measurement tools to scale models for 3D printing
- Support additional export formats (STL)
- Share models publicly via gallery links
