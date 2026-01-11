# Job Listing Portal

A modern, full-featured job listing application built with React and Vite. This application demonstrates best practices in React development including component composition, state management, routing, and REST API integration.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Available Scripts](#available-scripts)
- [Usage](#usage)
- [Components Overview](#components-overview)
- [API Integration](#api-integration)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Features

- 🏠 **Home Page** - Hero section with featured job listings and quick action cards
- 📋 **Jobs Listing** - Browse all available job positions with filtering and sorting
- 🔍 **Job Details** - View detailed information about individual job postings
- ➕ **Add Job** - Create new job listings with a user-friendly form
- 🛣️ **Client-side Routing** - Seamless navigation between pages using React Router
- 🎨 **Responsive Design** - Fully responsive UI with Tailwind CSS
- ⚡ **Real-time Updates** - CRUD operations with JSON Server REST API
- 🔄 **State Management** - Efficient data fetching and state handling
- 📱 **Mobile Friendly** - Optimized for all device sizes
- 🎯 **404 Handling** - Custom not-found page for invalid routes

## Tech Stack

### Frontend
- **React** (v19.1.1) - UI framework
- **Vite** (v7.1.7) - Build tool and dev server
- **React Router DOM** (v7.9.5) - Client-side routing
- **Tailwind CSS** (v4.1.17) - Utility-first CSS framework
- **React Icons** (v5.5.0) - Icon library
- **React Spinners** (v0.17.0) - Loading spinner component

### Backend/Database
- **JSON Server** (v1.0.0-beta.3) - Mock REST API server

### Development Tools
- **ESLint** - Code quality and linting
- **Vite React Plugin** - Fast HMR for React development

## Installation

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager

### Setup

1. **Clone the repository:**
```bash
git clone <repository-url>
cd react-dev
```

2. **Install dependencies:**
```bash
npm install
```

## Getting Started

### Running the Development Environment

You'll need to run two terminals for the full development experience:

**Terminal 1 - Start the Vite dev server:**
```bash
npm run dev
```
This starts the React application at `http://localhost:3000` with hot module reloading.

**Terminal 2 - Start the JSON Server:**
```bash
npm run server
```
This starts the mock REST API server at `http://localhost:8000` serving the jobs data.

The application will automatically open in your default browser. The dev server is configured to proxy API requests from `/api/*` to the JSON Server.

### Quick Start Command
Run both servers in parallel (using a process manager or in separate terminals):
```bash
npm run dev
npm run server
```

## Project Structure

```
react-dev/
├── src/
│   ├── components/           # Reusable React components
│   │   ├── Card.jsx
│   │   ├── Hero.jsx
│   │   ├── HomeCards.jsx
│   │   ├── JobListing.jsx
│   │   ├── JobListings.jsx
│   │   ├── Navbar.jsx
│   │   ├── Spinner.jsx
│   │   └── ViewAllJobs.jsx
│   ├── layouts/              # Layout components
│   │   └── MainLayout.jsx
│   ├── pages/                # Page components (routes)
│   │   ├── HomePage.jsx
│   │   ├── JobPage.jsx
│   │   ├── JobsPage.jsx
│   │   ├── AddJobPage.jsx
│   │   └── NotFoundPage.jsx
│   ├── assets/               # Static assets
│   │   └── images/
│   ├── App.jsx               # Main App component with routing
│   ├── main.jsx              # React entry point
│   ├── index.css             # Global styles
│   └── jobs.json             # Mock database for jobs
├── public/                   # Static files
├── vite.config.js            # Vite configuration
├── eslint.config.js          # ESLint configuration
├── package.json              # Project dependencies
├── index.html                # HTML entry point
└── README.md                 # This file
```

## Available Scripts

### Development
- `npm run dev` - Start Vite development server (port 3000)
- `npm run server` - Start JSON Server with jobs data (port 8000)

### Production
- `npm run build` - Build optimized production bundle
- `npm run preview` - Preview production build locally

### Code Quality
- `npm run lint` - Run ESLint to check code quality

## Usage

### Navigating the Application

1. **Home Page** - Land on the home page to see featured jobs and quick action cards
2. **Browse Jobs** - Click "View All Jobs" or navigate to `/jobs` to see all listings
3. **View Details** - Click on any job card to see full job details and company information
4. **Add New Job** - Navigate to the "Add Job" page to create a new job listing
5. **Search & Filter** - Use the search functionality to find jobs by title or location

### Creating a Job

1. Navigate to the "Add Job" page
2. Fill in the job details:
   - Job Title
   - Job Type (Full-Time, Part-Time, etc.)
   - Description
   - Location
   - Salary Range
   - Company Information
3. Submit the form
4. The new job will appear in the listings immediately

### Editing & Deleting

- Click the edit or delete buttons on job details pages to modify or remove listings
- All changes are persisted to the JSON Server database

## Components Overview

### Layout
- **MainLayout** - Main wrapper component with navigation

### Pages
- **HomePage** - Hero section with featured jobs
- **JobsPage** - Full jobs listing with filtering
- **JobPage** - Individual job details with company information
- **AddJobPage** - Form to create new job listings
- **NotFoundPage** - 404 error page

### Components
- **Navbar** - Navigation bar with links to main pages
- **Hero** - Hero section on homepage
- **HomeCards** - Quick action cards on homepage
- **JobListings** - Grid display of job cards
- **JobListing** - Individual job card component
- **Card** - Reusable card component
- **ViewAllJobs** - Call-to-action button/component
- **Spinner** - Loading indicator component

## API Integration

The application uses JSON Server to provide a mock REST API. The server runs on `http://localhost:8000` and serves job data from `src/jobs.json`.

### API Endpoints

```
GET    /jobs           - Get all jobs
GET    /jobs/:id       - Get a specific job
POST   /jobs           - Create a new job
PUT    /jobs/:id       - Update a job
DELETE /jobs/:id       - Delete a job
```

### Vite Proxy Configuration

The Vite dev server is configured to proxy `/api/*` requests to `http://localhost:8000`:

```javascript
proxy: {
  '/api': {
    target: 'http://localhost:8000',
    changeOrigin: true,
    rewrite: (path) => path.replace(/^\/api/, ''),
  }
}
```

This allows you to call `/api/jobs` in your application, which gets forwarded to `http://localhost:8000/jobs`.

## Deployment

### Build for Production

```bash
npm run build
```

This creates an optimized production bundle in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

## Code Quality

This project uses ESLint to maintain code quality. Run the linter with:

```bash
npm run lint
```

Configuration is defined in `eslint.config.js`.

## Learning Goals

This project demonstrates:
- **React Fundamentals** - Components, hooks, and state management
- **Component Composition** - Building reusable, modular components
- **Routing** - Client-side routing with React Router
- **API Integration** - Fetching and managing API data
- **Form Handling** - Creating forms for user input
- **Styling** - Using Tailwind CSS for responsive design
- **Development Workflow** - Using Vite for fast development experience
- **Mock Backend** - Using JSON Server for API mocking during development

