# Portfolio Website

## Overview

This is a modern, responsive portfolio website built with React, TypeScript, and Express.js for Muhammad Asim, a Data Analyst and AI Specialist. The application features a full-stack architecture with a React frontend showcasing professional experience, education, and skills, along with an Express backend handling contact form submissions and data persistence.

## Recent Changes (January 2025)

- ✓ Updated portfolio with Muhammad Asim's personal information
- ✓ Modified Hero section with name, title, and professional summary
- ✓ Updated About section with actual background and experience
- ✓ Added dedicated Education section showcasing academic qualifications
- ✓ Customized Skills section for data analysis and AI/ML focus
- ✓ Updated Professional Experience section with real projects
- ✓ Updated contact information with actual email and phone
- ✓ Modified page title and meta description for SEO
- ✓ Updated navigation to include Education section

## User Preferences

Preferred communication style: Simple, everyday language.

## Portfolio Owner Information

**Name:** Muhammad Asim
**Title:** Data Analyst | AI Specialist
**Location:** Malir Halt, Karachi, Pakistan
**Email:** m.asim.asim@outlook.com
**Phone:** +92 347 4876360

**Education:**
- MS Artificial Intelligence – NED University (2023–2024)
- BE Electronics – Iqra University (2011–2015)
- Intermediate (Pre-Engineering) – Govt. National College (2007–2010)
- Matriculation (Science) – Green House Grammar School (2007)

**Professional Experience:**
- Data Analyst – Digitechtic (Feb 2023 – Jul 2024)
- Data Analyst – Nastech (Jun 2022 – Feb 2023)
- Data Analyst – Technosys (Mar 2021 – Apr 2021)

**Key Skills:** Python, SQL, Power BI, PyTorch, BERT, Data Visualization, Statistical Analysis, Academic Writing, APA/MLA/Harvard Formatting

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **UI Components**: Radix UI components with shadcn/ui design system
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: React Query (TanStack Query) for server state management
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (@neondatabase/serverless)
- **Session Management**: In-memory storage with fallback to database
- **API**: RESTful endpoints for contact form handling

### Key Components

#### Frontend Components
- **Navigation**: Smooth scrolling navigation with active section highlighting
- **Hero Section**: Professional introduction with call-to-action buttons
- **About Section**: Personal information and downloadable resume
- **Skills Section**: Technical skills organized by category
- **Projects Section**: Featured project showcase with links
- **Contact Section**: Contact form with validation and toast notifications

#### Backend Components
- **Route Handler**: Express routes for contact form submission and retrieval
- **Storage Layer**: Abstract storage interface with in-memory implementation
- **Database Schema**: User and contact message tables with validation
- **Error Handling**: Centralized error handling with proper HTTP status codes

## Data Flow

1. **Contact Form Submission**: 
   - User fills out contact form in React frontend
   - Form data is validated client-side
   - React Query mutation sends POST request to `/api/contact`
   - Express server validates data using Zod schema
   - Data is stored in PostgreSQL database via Drizzle ORM
   - Success/error response sent back to client
   - Toast notification displays result to user

2. **Contact Messages Retrieval**:
   - Admin endpoint `/api/contact` (GET) retrieves all messages
   - Storage layer queries database and returns formatted data

## External Dependencies

### Frontend Dependencies
- **UI Framework**: React with TypeScript support
- **Styling**: Tailwind CSS for utility-first styling
- **UI Components**: Radix UI primitives for accessible components
- **Form Handling**: React Hook Form with Zod validation
- **HTTP Client**: Fetch API wrapped in React Query
- **Icons**: Lucide React icons
- **Date Handling**: date-fns for date formatting

### Backend Dependencies
- **Database**: PostgreSQL with Drizzle ORM for type-safe queries
- **Validation**: Zod for runtime type checking and validation
- **Session Storage**: connect-pg-simple for PostgreSQL session storage
- **Database Provider**: Neon Database serverless PostgreSQL

### Development Dependencies
- **Build Tool**: Vite for frontend bundling
- **TypeScript**: Full TypeScript support across the stack
- **ESBuild**: For backend bundling in production
- **Replit Integration**: Custom plugins for Replit development environment

## Deployment Strategy

### Development Environment
- **Frontend**: Vite dev server with hot module replacement
- **Backend**: tsx for TypeScript execution with auto-reload
- **Database**: Neon Database serverless connection
- **Environment**: Replit-optimized with custom plugins

### Production Build
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: ESBuild bundles TypeScript to `dist/index.js`
- **Database**: Drizzle migrations applied via `db:push` command
- **Deployment**: Single Node.js process serving both frontend and API

### Configuration
- **Environment Variables**: `DATABASE_URL` for database connection
- **Build Scripts**: Separate commands for development and production
- **TypeScript**: Shared configuration across client, server, and shared modules
- **Path Aliases**: Configured for clean imports (`@/`, `@shared/`)

The architecture follows a clean separation of concerns with shared TypeScript types, centralized error handling, and a scalable structure that can easily accommodate future features like authentication, user profiles, and content management.