# Remote Interview Platform 🚀

<div align="center">
  <strong>A full-stack, real-time collaborative platform for conducting remote technical interviews. Featuring high-quality video conferencing, a shared code editor, and robust scheduling capabilities to streamline the hiring process.</strong>
</div>

<br/>

<!-- Badges -->
<div align="center">
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Convex-1A1A1A?style=for-the-badge&logo=convex&logoColor=white" alt="Convex">
  <img src="https://img.shields.io/badge/Clerk-6C47FF?style=for-the-badge&logo=clerk&logoColor=white" alt="Clerk">
  <img src="https://img.shields.io/badge/Stream-005FFF?style=for-the-badge&logo=stream&logoColor=white" alt="Stream">
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
</div>

---

## 📋 Table of Contents

- [About The Project](#-about-the-project)
- [Key Features](#-key-features)
- [How It Works](#-how-it-works)
- [Technologies Used](#️-technologies-used)
- [Getting Started](#-getting-started)
- [Environment Setup](#-environment-setup)
- [File Structure](#-file-structure)
- [Contributing](#-contributing)

---

## 🌟 About The Project

The **Remote Interview Platform** is a comprehensive solution designed to address the challenges of modern technical hiring. It provides an all-in-one environment where interviewers and candidates can connect, communicate, and collaborate in real-time. The platform seamlessly integrates video conferencing, a shared code editor, and interview scheduling to create an experience that is both efficient and effective.

Built on a modern, serverless technology stack, this application ensures real-time data synchronization, low latency, and a high degree of reliability. The frontend is crafted with **Next.js** and **TypeScript**, offering a type-safe and performant user experience. The backend is powered by **Convex**, a serverless platform that handles the database, server functions, and real-time updates. User authentication is managed by **Clerk**, and the real-time video/audio capabilities are powered by **Stream**.

---

## ✨ Key Features

- **📹 High-Quality Video Conferencing**: Real-time, low-latency video and audio powered by Stream, allowing for clear and effective communication.
- **💻 Collaborative Code Editor**: A shared code editor where both the interviewer and candidate can write, edit, and run code simultaneously.
- **🗓️ Interview Scheduling**: A dedicated interface for scheduling interviews, with the ability to set dates, times, and invite participants.
- **🔐 Secure Authentication**: Robust and secure user management and authentication handled by Clerk.
- **🔄 Real-time Database**: All data, including code changes and comments, is synchronized in real-time for all participants, thanks to Convex.
- **⏺️ Session Recording**: Functionality to record interview sessions for later review and feedback.
- **💬 Commenting System**: A feature allowing for comments and feedback to be added during or after the interview.
- **🎨 Modern & Themed UI**: A sleek, professional user interface built with Tailwind CSS and Shadcn/UI, including light and dark mode support.
- **👨‍💼 Role-Based Access**: Differentiated views and capabilities for regular users and administrators.

---

## ⚙️ How It Works

1.  **Authentication**: Users sign up or log in using Clerk's secure authentication flow.
2.  **Dashboard**: After logging in, users are directed to their dashboard, where they can see upcoming interviews and access key actions.
3.  **Scheduling**: Users can navigate to the "Schedule" page to create a new interview, setting the date, time, and programming language.
4.  **Joining a Meeting**: When it's time for the interview, participants can join the meeting room via a unique link.
5.  **The Interview Room**:
    -   The main interface features a video conferencing layout powered by Stream.
    -   A resizable panel contains the collaborative code editor.
    -   Participants can communicate via video/audio and code together in real-time.
6.  **Post-Interview**:
    -   Recordings of the session are available for review on the "Recordings" page.
    -   Interviewers can leave comments and feedback.

---

## 🛠️ Technologies Used

This project is built with a powerful and modern technology stack designed for real-time, full-stack applications.

### Frontend

- **Next.js**: A React framework for building server-side rendered and statically generated web applications.
- **React**: A JavaScript library for building user interfaces.
- **TypeScript**: A statically typed superset of JavaScript that adds type safety.
- **Tailwind CSS**: A utility-first CSS framework for rapid UI development.
- **Shadcn/UI**: A collection of beautifully designed, reusable components.

### Backend & Real-time

- **Convex**: A serverless platform providing a real-time database and server functions (mutations and queries).
- **Clerk**: A complete user management and authentication service.
- **Stream**: An API platform for building real-time chat and video functionalities.

---

## 🚀 Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

- **Node.js & npm**: Ensure you have Node.js (v18.0 or higher) and npm installed.
- **Clerk Account**: You will need a Clerk account and a project set up. Get your API keys from the [Clerk Dashboard](https://dashboard.clerk.com/).
- **Convex Account**: You'll need a Convex account and a new project. Install the Convex CLI: `npm install -g convex`.
- **Stream Account**: You will need a Stream account to get your API key and secret for the video conferencing features.

### Environment Setup

Create a file named `.env.local` in the root of the project and add the following environment variables with your credentials:

```env
# Clerk Keys
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=<YOUR_CLERK_PUBLISHABLE_KEY>
CLERK_SECRET_KEY=<YOUR_CLERK_SECRET_KEY>

# Convex URL (get this after deploying your Convex backend)
NEXT_PUBLIC_CONVEX_URL=<YOUR_CONVEX_DEPLOYMENT_URL>

# Stream Keys
NEXT_PUBLIC_STREAM_API_KEY=<YOUR_STREAM_API_KEY>
STREAM_SECRET_KEY=<YOUR_STREAM_SECRET_KEY>

# Clerk Webhook Secret
CLERK_WEBHOOK_SECRET=<YOUR_CLERK_WEBHOOK_SECRET>
```

## 📂 File Structure

```
.
├── convex/
│   ├── _generated/     # Auto-generated Convex API files
│   ├── auth.config.ts  # Clerk authentication configuration for Convex
│   ├── comments.ts     # Convex functions for comments
│   ├── interviews.ts   # Convex functions for interviews
│   ├── schema.ts       # Database schema definition
│   └── users.ts        # Convex functions for users
├── public/
│   └── ...             # Public assets like images
├── src/
│   ├── actions/
│   │   └── stream.actions.ts # Server actions for Stream
│   ├── app/
│   │   ├── (admin)/      # Routes for admin users
│   │   ├── (root)/       # Main application routes
│   │   ├── layout.tsx    # Root layout
│   │   └── globals.css   # Global styles
│   ├── components/
│   │   ├── providers/    # Context providers (Theme, Convex, Stream)
│   │   ├── ui/           # Shadcn/UI components
│   │   ├── CodeEditor.tsx
│   │   └── MeetingRoom.tsx
│   ├── hooks/            # Custom React hooks
│   ├── lib/              # Utility functions
│   └── middleware.ts     # Authentication middleware with Clerk
├── .env.local          # Environment variables
├── next.config.mjs     # Next.js configuration
└── tailwind.config.ts  # Tailwind CSS configuration
```

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

Don't forget to give the project a star! Thanks again!

1.  **Fork the Project**
2.  **Create your Feature Branch** (`git checkout -b feature/AmazingFeature`)
3.  **Commit your Changes** (`git commit -m 'Add some AmazingFeature'`)
4.  **Push to the Branch** (`git push origin feature/AmazingFeature`)
5.  **Open a Pull Request**
