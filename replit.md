# LeaveManager

## Overview

LeaveManager is a full-stack employee leave management system that allows employees to submit leave requests and administrators to approve or reject them. The application features role-based access control with separate interfaces for employees and admins, along with real-time status tracking of leave requests.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript, built using Vite
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack React Query for server state and caching
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Typography**: Custom fonts (Outfit for display, Plus Jakarta Sans for body text)

### Backend Architecture
- **Primary Server**: Express.js (TypeScript) in `/server` directory - serves as a reverse proxy
- **API Backend**: Flask (Python) in `/backend` directory - handles all business logic and database operations
- **API Pattern**: RESTful API with `/api` prefix for all routes
- **Build System**: esbuild for server bundling, Vite for client bundling
- **Proxy Setup**: Express proxies all `/api/*` requests to Flask running on port 5001. Flask is started as a child process from Express.

### Data Layer
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema Location**: `/shared/schema.ts` - shared between frontend and backend
- **Validation**: Zod schemas generated from Drizzle schemas using drizzle-zod
- **Tables**: 
  - `users` - stores user accounts with roles (admin/employee)
  - `leaves` - stores leave requests with status tracking

### Authentication & Authorization
- **Session Management**: Express session with connect-pg-simple for PostgreSQL session storage
- **Role-Based Access**: Two roles - "admin" and "employee"
- **Protected Routes**: Client-side route protection via `ProtectedRoute` component
- **Auth Context**: React context (`AuthProvider`) for global auth state

### API Design
- **Contract Definition**: Shared route definitions in `/shared/routes.ts` using Zod schemas
- **Type Safety**: Full TypeScript types shared between client and server
- **Error Handling**: Standardized error schemas for validation, not found, and internal errors

### Storage Abstraction
- **Interface**: `IStorage` interface in `/server/storage.ts`
- **Implementation**: Currently uses in-memory storage (`MemStorage`)
- **Design**: Ready for database implementation swap

## External Dependencies

### Database
- **PostgreSQL**: Primary database (configured via `DATABASE_URL` environment variable)
- **Drizzle Kit**: Database migrations and schema push (`npm run db:push`)

### UI Libraries
- **Radix UI**: Headless accessible components (dialog, dropdown, tabs, etc.)
- **Embla Carousel**: Carousel component
- **react-day-picker**: Calendar date selection
- **date-fns**: Date formatting and manipulation
- **Lucide React**: Icon library

### Development Tools
- **Replit Plugins**: 
  - `@replit/vite-plugin-runtime-error-modal` for error display
  - `@replit/vite-plugin-cartographer` for development
  - `@replit/vite-plugin-dev-banner` for development environment indicator

## Future Enhancements

### Email Notifications (Not Yet Implemented)
- **Status**: Skipped for now - user chose to add later
- **Purpose**: Send email notifications when leave requests are approved or rejected
- **Recommended Integration**: SendGrid or Resend
- **Implementation Notes**: 
  - Add email service integration (SendGrid/Resend API key required)
  - Update `useUpdateLeaveStatus` hook to trigger email on status change
  - Create email templates for approval and rejection notifications