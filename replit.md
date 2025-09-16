# replit.md

## Overview

Pay It Forward is a comprehensive mental health platform that connects clients with mental health professionals including licensed counselors and peer specialists. The application facilitates appointment booking, secure messaging, resource sharing, and payment processing through a full-stack web application built with modern technologies.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Components**: Shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS custom properties for theming
- **State Management**: TanStack Query for server state and local React state for UI state
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation via Hookform resolvers

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful endpoints with middleware-based architecture
- **Session Management**: Express sessions with PostgreSQL session storage
- **Middleware**: Custom logging, error handling, and authentication middleware

### Authentication & Authorization
- **Authentication Provider**: Replit OIDC (OpenID Connect) integration
- **Session Storage**: PostgreSQL-backed sessions using connect-pg-simple
- **Authorization**: Role-based access control (client, counselor, peer_specialist)
- **Security**: HTTP-only cookies, CSRF protection, and secure session configuration

### Database Architecture
- **Database**: PostgreSQL with Neon serverless driver
- **ORM**: Drizzle ORM with schema-first approach
- **Schema Management**: Drizzle migrations with TypeScript schema definitions
- **Connection**: Connection pooling via Neon serverless pool

### Key Data Models
- **Users**: Supports multiple roles with role-specific fields (specialties, licenses, rates)
- **Appointments**: Links clients with providers, includes scheduling and payment data
- **Messages**: Direct messaging system between users
- **Resources**: Content management for educational materials and coping strategies
- **Sessions**: Secure session storage for authentication state

### Payment Processing
- **Payment Provider**: Stripe integration for subscription and session-based payments
- **Client Integration**: React Stripe.js components for secure payment forms
- **Server Integration**: Stripe webhook handling and customer management

## External Dependencies

### Core Services
- **Neon Database**: PostgreSQL serverless database hosting
- **Replit Authentication**: OIDC-based user authentication and session management
- **Stripe**: Payment processing and subscription management
- **SendGrid**: Email delivery service for notifications

### Development & Deployment
- **Vite**: Frontend build tool with React plugin
- **Replit Development Tools**: Runtime error overlay, cartographer, and dev banner
- **TypeScript**: Type safety across frontend, backend, and shared code

### Third-party Libraries
- **UI Components**: Radix UI primitives for accessible component foundations
- **Icons**: Lucide React for consistent iconography
- **Styling**: Tailwind CSS with class variance authority for component variants
- **Validation**: Zod for runtime type validation and form schemas
- **WebSocket**: WebSocket support for real-time features (via ws library)

### API Integrations
- **Google Fonts**: Custom font loading for typography (Inter, DM Sans, Geist Mono)
- **External Resources**: Support for external content linking in resources system

The architecture emphasizes type safety with shared TypeScript schemas, real-time capabilities through polling and potential WebSocket integration, and a secure multi-tenant system supporting different user roles with appropriate access controls.