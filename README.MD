# Classroom Management System - Frontend

A modern, responsive, and dynamic dashboard web application built to manage daily educational operations including users, departments, subjects, and classroom enrollments.

## 🚀 Tech Stack

- **Framework**: React + [Vite](https://vitejs.dev/)
- **Language**: TypeScript
- **App Framework**: [Refine](https://refine.dev/) (Headless React Framework for enterprise apps)
- **Styling UI**: [Tailwind CSS](https://tailwindcss.com/) & [shadcn/ui](https://ui.shadcn.com/)
- **Icons**: Lucide React
- **Data Fetching**: `@better-fetch/fetch` & Refine Data Providers
- **Authentication Client**: [better-auth](https://better-auth.com/)

## ✨ Features

- **Role-Based UI**: Dynamic rendering based on the user's role (Admin, Teacher, Student). Restricts students to view-only access by automatically hiding creation, editing, and deletion tools.
- **Resource Management**: Comprehensive List, Create, Edit, and Show pages for Departments, Subjects, Classes, and Users.
- **Enrollment Handling**: Interactive UI within the Class Details view allowing teachers/admins to seamlessly view, enroll, and unenroll students.
- **Robust Searching & Filtering**: Advanced server-side pagination, searching, and filtering integrations on data tables.
- **Authentication**: Fully integrated login and registration flows via Better Auth.

## 🛠️ Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- The Classroom Management Backend running locally or deployed.

### Environment Variables

Create a `.env` file in the root of the frontend directory and add the following:

```env
# The URL where your backend server is running.
# Important: Do NOT include a trailing slash or '/api/' suffix.
VITE_BACKEND_BASE_URL="http://localhost:8000"
```

### Installation

1. Clone the repository and navigate to the frontend directory:
   ```bash
   cd classroom-fontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

### Running the Application

Start the Vite development server:
```bash
npm run dev
```

The application will be available at `http://localhost:5173`.

## 📂 Project Structure

- `src/components/`: Reusable UI components (shadcn/ui), Refine layout wrappers, and custom buttons.
- `src/lib/`: Core utilities including the `better-auth` client instance (`auth-client.ts`) and fetch wrappers.
- `src/pages/`: Page-level components organized by Refine resource (Auth, Classes, Departments, Subjects, Users).
- `src/providers/`: Custom Refine Data and Auth providers tightly coupled with the backend REST architecture.
- `src/types/`: Shared TypeScript type definitions matching the database schema.
- `src/App.tsx`: The main Refine entry point where routing, resources, and access control are configured.

## 🔐 Role-Based Access Control

The frontend uses Refine's `accessControlProvider` combined with the identity fetched from `better-auth`. If a logged-in user possesses the `student` role, the global configuration instructs the UI to suppress all administrative mutation attempts and automatically hides `<CreateButton>`, `<EditButton>`, and `<DeleteButton>` components.

Enjoy managing your digital classroom!
