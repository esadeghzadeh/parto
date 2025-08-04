# Parto - Counseling Platform Application

## Overview

This is a comprehensive counseling platform called "Parto" built with a React frontend and Express.js backend. The application connects clients with professional counselors through multiple communication channels (text, voice, video), features role-based dashboards for clients, counselors, and administrators, and includes appointment scheduling, profile management, and administrative approval workflows.

## Recent Changes (January 29, 2025)

✓ Successfully migrated from in-memory storage to PostgreSQL database
✓ Implemented complete database integration with Drizzle ORM
✓ Fixed TypeScript import issues for React pages
✓ Application now running with persistent data storage
✓ Sample data initialized with test accounts for all user roles
✓ Fixed OTP field editing issue in authentication form
✓ Added comprehensive counselor registration workflow with file upload
✓ Implemented admin approval system with email notifications
✓ Created Stripe payment integration for session booking
✓ Added SendGrid email service for automated notifications
✓ Built admin panel for counselor approval with document review
✓ Added official Parto application logo to all main pages
✓ Completed session booking system with client dashboard
✓ Integrated authentication system across all user roles
✓ Fixed admin dashboard counselor information display issues
✓ Resolved counselor approval/rejection workflow functionality
✓ Implemented status-based first login messages system
✓ Added complete counselor approval workflow with profile activation
✓ Created automatic welcome/rejection/completion messages for counselors
✓ Enhanced admin panel to show complete counselor information and documents
✓ Implemented Persian solar calendar (Hijri Shamsi) conversion library for all date displays
✓ Added RTL text alignment for profile tabs and titles with back to dashboard buttons
✓ Fixed dashboard navigation to redirect to correct dashboard based on user role after login
✓ Created comprehensive counselor profile system with personal info, consultations tracking, wallet, transactions, and messages sections
✓ Developed admin profile system with users management, counselors management, consultations tracking, transactions monitoring, and settings
✓ Implemented complete privacy separation between counselor personal profile and public counselor information for clients
✓ Added detailed admin management panel with comprehensive statistics for users, counselors (all states), sessions, transactions, payments, and settings
✓ Enhanced counselor dashboard with profile access button - counselor personal profile now only accessible from counselor dashboard
✓ Created comprehensive session booking interface with three session types: text chat, voice call, and video call
✓ Implemented Persian calendar system with separate year/month selection showing Persian month names
✓ Built calendar grid displaying weekdays from Saturday to Friday with selectable available dates based on counselor schedule
✓ Added dynamic time slot selection that shows counselor's available hours when a date is selected
✓ Integrated fee display and Stripe payment gateway activation after time selection with complete booking summary
✓ Maintained full RTL (Right-to-Left) text alignment throughout the booking interface for Persian language support

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: Radix UI components with shadcn/ui styling system
- **Styling**: Tailwind CSS with RTL (Right-to-Left) support for Persian/Farsi language
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation
- **Authentication**: OTP-based authentication via SMS

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: In-memory storage for development (with PostgreSQL schema design)
- **Authentication**: OTP verification system
- **API Design**: RESTful endpoints with JSON responses
- **Role-based Access**: Multi-role system supporting clients, counselors, and administrators

### Mobile-First Design
- Responsive layout optimized for mobile devices
- RTL (Right-to-Left) layout for Persian language support
- Touch-friendly interface components
- Optimized navigation for different user roles

## Key Components

### Data Layer
- **Schema Definition**: Centralized in `shared/schema.ts` using Drizzle ORM
- **Storage Interface**: PostgreSQL database with Drizzle ORM integration
- **Database Tables**: 
  - `users`: User accounts for all roles (clients, counselors, admins)
  - `counselors`: Counselor profiles with specializations and credentials
  - `sessions`: Counseling sessions with scheduling and payment info
  - `reviews`: Client reviews and ratings for counselors
  - `transactions`: Financial transactions and wallet management
  - `notifications`: System notifications for users
  - `otpCodes`: OTP verification codes for authentication

### File Upload System
- **Document Management**: Multer-based file upload for counselor credentials
- **Document Types**: PDF and image files for education certificates
- **Storage**: Local file system with served static files
- **Security**: File type validation and size limits

### Authentication System
- **OTP-based Login**: SMS-based verification system
- **Multi-role Support**: Separate flows for clients, counselors, and administrators
- **Session Management**: Local storage-based session persistence
- **Phone Number Verification**: Primary authentication method

### User Roles & Dashboards

#### Client Dashboard
- **Counselor Discovery**: Browse and search approved counselors
- **Specialization Filtering**: Filter counselors by expertise areas
- **Session Booking**: Schedule sessions via text, voice, or video
- **Review System**: Rate and review completed sessions

#### Counselor Dashboard
- **Session Management**: View upcoming and completed sessions
- **Profile Management**: Complete counselor profile with credentials
- **Wallet System**: Track earnings and request payouts
- **Notification Center**: Receive updates about approvals and sessions

#### Admin Dashboard
- **Counselor Approval**: Review and approve counselor applications
- **Profile Verification**: Validate credentials and qualifications
- **System Statistics**: Monitor platform usage and metrics
- **Notification Management**: Send updates to users

### Profile Management
- **Counselor Profiles**: Education, specializations, work experience
- **Document Upload**: Support for credential verification
- **Availability Scheduling**: Set working hours and availability
- **Pricing Management**: Set hourly rates for different session types

## Data Flow

1. **User Registration**: OTP-based phone verification for account creation
2. **Role Assignment**: Users choose between client or counselor roles
3. **Profile Completion**: Counselors complete detailed professional profiles
4. **Admin Review**: Administrators review and approve counselor applications
5. **Session Booking**: Clients browse and book sessions with approved counselors
6. **Payment Processing**: Automated payment handling with platform fees
7. **Session Completion**: Rating and review system for quality assurance

## External Dependencies

### Core Dependencies
- **Database**: Neon Database (serverless PostgreSQL)
- **UI Components**: Radix UI primitives for accessibility
- **Styling**: Tailwind CSS for utility-first styling
- **Validation**: Zod for runtime type checking
- **HTTP Client**: Axios for external API requests
- **Web Scraping**: Cheerio for server-side DOM manipulation

### Development Tools
- **TypeScript**: Type safety across the full stack
- **ESBuild**: Fast bundling for production builds
- **Vite**: Development server with hot module replacement
- **Drizzle Kit**: Database migration and management tools

### Replit Integration
- **Development Banner**: Replit development environment integration
- **Error Overlay**: Runtime error modal for development
- **Cartographer**: Replit-specific development tools

## Deployment Strategy

### Build Process
- **Frontend**: Vite builds optimized production bundle to `dist/public`
- **Backend**: ESBuild bundles server code to `dist/index.js`
- **Database**: Drizzle migrations stored in `migrations/` directory

### Environment Configuration
- **Database URL**: Required environment variable for PostgreSQL connection
- **Development Mode**: NODE_ENV controls development-specific features
- **Production Serving**: Express serves static files and API routes

### Development Workflow
- **Hot Reload**: Vite provides instant feedback for frontend changes
- **TypeScript Checking**: Continuous type checking during development
- **Database Migrations**: `db:push` command for schema updates
- **Development Server**: Single command starts both frontend and backend

The application is designed to be easily deployable on Replit with minimal configuration, using environment variables for database connectivity and supporting both development and production modes seamlessly.