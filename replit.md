# ResumeMatch AI

## Overview

ResumeMatch AI is a full-stack web application that uses artificial intelligence to match job seekers with relevant job opportunities. The platform allows users to upload their resumes, which are analyzed using OpenAI's GPT-4o model to extract skills, experience, and other relevant information. This data is then used to match candidates with suitable job postings, providing match scores and detailed explanations. The system serves both job seekers (who can upload resumes and find matching jobs) and administrators (who can post jobs and manage applications).

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **Routing**: Wouter for client-side routing with protected routes
- **State Management**: TanStack Query (React Query) for server state management
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Authentication**: Passport.js with local strategy using session-based auth
- **Session Storage**: PostgreSQL-backed sessions using connect-pg-simple
- **File Handling**: Multer for resume file uploads (PDF, DOC, DOCX)
- **API Structure**: RESTful endpoints under `/api` prefix

### Database Layer
- **Database**: PostgreSQL (configured for Neon serverless)
- **ORM**: Drizzle ORM with TypeScript-first schema definitions
- **Schema**: Separate tables for users, admins, resumes, jobs, and applications with proper relationships
- **Migrations**: Drizzle Kit for database schema management

### Authentication System
- **User Types**: Dual authentication system supporting both regular users and administrators
- **Password Security**: Scrypt-based password hashing with salt
- **Session Management**: Express sessions with PostgreSQL store
- **Route Protection**: Protected routes for authenticated users and admin-specific areas

### AI Integration
- **Provider**: OpenAI GPT-4o model for resume analysis and job matching
- **Resume Analysis**: Extracts skills, experience, education, job titles, and generates professional summaries
- **Job Matching**: Calculates match scores between resumes and job postings with explanations
- **Response Format**: Structured JSON responses for consistent data handling

### File Upload System
- **Storage**: Local file system with configurable upload directory
- **Validation**: File type restrictions (PDF, DOC, DOCX) and size limits (5MB)
- **Processing**: Resume text extraction and AI analysis pipeline
- **Metadata**: Stores file paths, extracted content, and analysis results

### Development Tools
- **Build System**: Vite for frontend with hot module replacement in development
- **Development Server**: Concurrent backend and frontend development setup
- **Code Quality**: TypeScript strict mode with comprehensive type checking
- **Environment**: Replit-optimized with development banner and error handling

## External Dependencies

### Core Services
- **Neon Database**: Serverless PostgreSQL hosting with connection pooling
- **OpenAI API**: GPT-4o model for resume analysis and job matching capabilities

### Authentication & Security
- **Passport.js**: Authentication middleware with local strategy
- **Express Session**: Session management with PostgreSQL backing

### Frontend Libraries
- **Radix UI**: Accessible component primitives for complex UI elements
- **TanStack Query**: Server state management and caching
- **React Hook Form**: Form handling with validation
- **Zod**: Runtime type validation and schema definition

### Development & Build Tools
- **Vite**: Fast build tool with HMR and optimized production builds
- **Tailwind CSS**: Utility-first CSS framework
- **TypeScript**: Type safety across the entire application stack
- **Drizzle Kit**: Database schema management and migrations
- **ESBuild**: Fast JavaScript bundler for production builds

### Utility Libraries
- **Multer**: Multipart form data handling for file uploads
- **Date-fns**: Date manipulation and formatting
- **Clsx & CVA**: Conditional CSS class management
- **Nanoid**: Unique identifier generation