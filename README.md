<p align="center">
  <img src="[https://upload.wikimedia.org/wikipedia/en/thumb/2/23/Vasavi_College_of_Engineering_logo.png/220px-Vasavi_College_of_Engineering_logo.png" alt="Vasavi College of Engineering Logo](https://vce.ac.in/assets/img/logo.svg)" width="150" />
</p>

# Question Paper Repository

A modern full-stack web application designed to serve as a comprehensive, organized repository for university question papers. Students can browse, view, and download previous question papers split across different branches, years, and semesters. 

## 🚀 Features

### For Students
* **Organized Browsing**: Easily navigate through various engineering branches (with a dedicated section for CSE/CSE-AIML), years, and semesters.
* **Smart Search**: Quickly find specific question papers using the integrated search bar to query by subject, branch, or year.
* **Preview & Download**: View PDF question papers directly in the browser via an integrated document viewer, or download them for offline use.
* **Usage Analytics**: Real-time tracking of views and downloads for each question paper.

### For Administrators
* **Secure Dashboard**: Protected admin login ensuring only authorized personnel can manage the repository.
* **Analytics at a Glance**: View overall system analytics, including total papers, total downloads, total views, and a monthly activity chart visualized via Recharts.
* **Paper Management**: Add new question papers by providing Google Drive PDF URLs, edit existing entries, and safely perform soft deletes.

## 🛠️ Tech Stack

### Frontend
* **Framework**: React 18, built with [Vite](https://vitejs.dev/)
* **Language**: TypeScript
* **Styling**: [Tailwind CSS](https://tailwindcss.com/)
* **UI Components**: [shadcn/ui](https://ui.shadcn.com/) (Radix UI primitives)
* **Icons**: [Lucide React](https://lucide.dev/)
* **Routing**: [React Router](https://reactrouter.com/) (v6)
* **Data Fetching & State**: [TanStack Query (React Query)](https://tanstack.com/query/latest)
* **Charts**: [Recharts](https://recharts.org/)

### Backend & Database
* **BaaS**: [Supabase](https://supabase.com/)
  * Authentication for Admin routing
  * PostgreSQL Database for branches, semesters, exam types, and papers
  * Row Level Security (RLS) policies
  * Remote Procedure Calls (RPC) for atomic view and download counts

## 📦 Getting Started

### Prerequisites
* Node.js (v18 or higher recommended)
* A [Supabase](https://supabase.com/) project configured with the correct schema (`branches`, `semesters`, `exam_types`, `papers`).

### Installation

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone <repository-url>
   cd questionpaperrepository-main
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```
   *(Note: The project contains a `bun.lockb` making it compatible with Bun if you prefer a faster runtime.)*

3. **Configure Environment Variables**:
   Create a `.env` file in the root directory and add your Supabase credentials:
   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. **Run the Development Server**:
   ```bash
   npm run dev
   ```
   The application will be available at `http://localhost:5173`.

### Build for Production
To generate a production-ready build:
```bash
npm run build
```

## 📂 Project Structure

* **`/src/components`**: Reusable UI components (Navbar, Breadcrumbs, Footer) and shadcn/ui components (`ui/`).
* **`/src/pages`**: Main page views (Index, Branch selections, Exam Papers, Admin Login, Admin Dashboard).
* **`/src/integrations`**: Supabase client initialization.
* **`/src/hooks`**: Custom React hooks (`use-mobile`, `use-toast`).
* **`/src/lib`**: Utility functions (Tailwind class mergers).

## 📝 License
This project is open-source and available under the terms of the typical MIT license restrictions unless otherwise stated.
