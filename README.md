# 🚀 AI Career Coach

> **Transform your career with AI-powered guidance, personalized coaching, and intelligent tools for professional success.**

[![Next.js](https://img.shields.io/badge/Next.js-15.1.4-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.0.0-blue?style=for-the-badge&logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Ready-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4.1-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Prisma](https://img.shields.io/badge/Prisma-6.16.1-2D3748?style=for-the-badge&logo=prisma)](https://www.prisma.io/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-316192?style=for-the-badge&logo=postgresql)](https://neon.tech/)

![AI Career Coach Banner](https://github.com/user-attachments/assets/eee79242-4056-4d19-b655-2873788979e1)

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [Installation](#-installation)
- [Environment Setup](#-environment-setup)
- [Database Setup](#-database-setup)
- [Usage](#-usage)
- [API Routes](#-api-routes)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [Deployment](#-deployment)
- [License](#-license)

## 🎯 Overview

**AI Career Coach** is a comprehensive full-stack web application that empowers job seekers and professionals to advance their careers through AI-powered tools and personalized guidance. The platform combines cutting-edge artificial intelligence with intuitive user experience to provide:

- **Smart Resume Building** with ATS optimization and AI feedback
- **Intelligent Cover Letter Generation** tailored to specific job applications
- **Interactive Interview Preparation** with mock interviews and performance analytics
- **Industry Insights** with real-time salary data and market trends
- **Career Progress Tracking** with personalized dashboards and goal setting

## ✨ Features

### 🤖 AI-Powered Tools
- **Resume Builder**: Create ATS-optimized resumes with AI suggestions and real-time feedback
- **Cover Letter Generator**: Generate personalized cover letters using Google Gemini AI
- **Interview Simulator**: Practice with AI-generated questions and receive performance insights
- **Skill Assessment**: Evaluate your technical and behavioral skills with detailed analytics

### 📊 Industry Intelligence
- **Real-time Salary Data**: Access current market rates across 50+ industries
- **Market Trends**: Stay updated with industry growth rates and demand levels
- **Skill Recommendations**: Discover trending skills and learning paths
- **Career Insights**: Get personalized recommendations based on your profile

### 🎨 User Experience
- **Modern UI**: Beautiful, responsive interface built with Tailwind CSS and Shadcn UI
- **Dark/Light Mode**: Seamless theme switching for optimal user comfort
- **Mobile-First**: Fully responsive design that works on all devices
- **Real-time Updates**: Live data synchronization and instant feedback

### 🔐 Security & Authentication
- **Secure Authentication**: Powered by Clerk with social login options
- **Data Protection**: Enterprise-grade security for user information
- **Role-based Access**: Granular permissions and user management
- **Session Management**: Secure token-based authentication

## 🛠 Tech Stack

### Frontend
- **[Next.js 15.1.4](https://nextjs.org/)** - React framework with App Router
- **[React 19.0.0](https://reactjs.org/)** - UI library with latest features
- **[Tailwind CSS 3.4.1](https://tailwindcss.com/)** - Utility-first CSS framework
- **[Shadcn UI](https://ui.shadcn.com/)** - Modern component library
- **[Lucide React](https://lucide.dev/)** - Beautiful icons
- **[React Hook Form](https://react-hook-form.com/)** - Performance forms with validation
- **[Recharts](https://recharts.org/)** - Composable charting library

### Backend
- **[Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)** - Serverless functions
- **[Prisma 6.16.1](https://www.prisma.io/)** - Next-generation ORM
- **[Neon PostgreSQL](https://neon.tech/)** - Serverless PostgreSQL database
- **[Inngest](https://www.inngest.com/)** - Background job processing

### AI & External Services
- **[Google Gemini AI](https://ai.google.dev/)** - Advanced language model for content generation
- **[Clerk](https://clerk.dev/)** - User authentication and management

### Development Tools
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe JavaScript
- **[ESLint](https://eslint.org/)** - Code linting and formatting
- **[Zod](https://zod.dev/)** - Schema validation
- **[Date-fns](https://date-fns.org/)** - Modern date utility library

## 🏗 Architecture

```mermaid
graph TB
    A[Client Browser] --> B[Next.js App Router]
    B --> C[React Components]
    C --> D[Shadcn UI]
    B --> E[API Routes]
    E --> F[Prisma ORM]
    F --> G[Neon PostgreSQL]
    E --> H[Gemini AI]
    E --> I[Inngest Jobs]
    B --> J[Clerk Auth]
    
    K[Vercel Deployment] --> B
    L[External APIs] --> E
```

### Key Design Patterns
- **Server Components**: Leveraging Next.js 15 server components for optimal performance
- **Client Components**: Strategic use of client-side rendering for interactive features
- **Atomic Design**: Modular component architecture for maintainability
- **Repository Pattern**: Clean data access layer with Prisma
- **Event-Driven**: Background processing with Inngest for heavy operations

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18.0.0 or higher)
- **npm** or **pnpm** (recommended)
- **Git**
- **PostgreSQL** (or use Neon for cloud database)

### 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/x0lg0n/ai-career-coach.git
   cd ai-career-coach
   ```

2. **Install dependencies**
   ```bash
   # Using npm
   npm install
   
   # Using pnpm (recommended)
   pnpm install
   ```

## ⚙️ Environment Setup

Create a `.env.local` file in the root directory with the following variables:

```env
# Database Configuration
DATABASE_URL="postgresql://username:password@localhost:5432/ai_career_coach"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="pk_test_your_clerk_publishable_key"
CLERK_SECRET_KEY="sk_test_your_clerk_secret_key"

# Clerk URLs
NEXT_PUBLIC_CLERK_SIGN_IN_URL="/sign-in"
NEXT_PUBLIC_CLERK_SIGN_UP_URL="/sign-up"
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL="/onboarding"
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL="/onboarding"

# Google Gemini AI
GEMINI_API_KEY="your_gemini_api_key"

# Inngest (optional for development)
INNGEST_EVENT_KEY="your_inngest_event_key"
INNGEST_SIGNING_KEY="your_inngest_signing_key"
```

### 🔑 Getting API Keys

#### Clerk Authentication
1. Sign up at [Clerk.dev](https://clerk.dev/)
2. Create a new application
3. Copy the publishable and secret keys from the dashboard

#### Google Gemini AI
1. Go to [Google AI Studio](https://makersuite.google.com/)
2. Create a new API key
3. Enable the Generative AI API

#### Neon PostgreSQL
1. Sign up at [Neon.tech](https://neon.tech/)
2. Create a new database
3. Copy the connection string

## 🗄️ Database Setup

1. **Generate Prisma Client**
   ```bash
   npx prisma generate
   ```

2. **Run database migrations**
   ```bash
   npx prisma migrate dev
   ```

3. **Seed the database (optional)**
   ```bash
   npx prisma db seed
   ```

4. **View your data with Prisma Studio**
   ```bash
   npx prisma studio
   ```

## 🎮 Usage

### Development Mode

```bash
# Start the development server
npm run dev
# or
pnpm dev

# With Turbopack (faster)
npm run dev --turbo
```

Open [http://localhost:3000](http://localhost:3000) to view the application.

### Production Build

```bash
# Build the application
npm run build

# Start the production server
npm start
```

### Key Features Walkthrough

1. **Authentication**: Sign up/in using Clerk
2. **Onboarding**: Complete your profile setup
3. **Dashboard**: View your career progress and insights
4. **Resume Builder**: Create and optimize your resume
5. **Cover Letter Generator**: Generate tailored cover letters
6. **Interview Prep**: Practice with AI-powered mock interviews
7. **Industry Insights**: Explore salary data and market trends

## 🛣 API Routes

### Authentication
- `GET /api/auth/user` - Get current user profile
- `POST /api/auth/onboard` - Complete user onboarding

### Resume Management
- `GET /api/resume` - Fetch user resume
- `POST /api/resume` - Create/update resume
- `POST /api/resume/analyze` - Get ATS score and feedback

### Cover Letters
- `GET /api/cover-letters` - List user cover letters
- `POST /api/cover-letters` - Generate new cover letter
- `PUT /api/cover-letters/[id]` - Update cover letter
- `DELETE /api/cover-letters/[id]` - Delete cover letter

### Interview Preparation
- `GET /api/interviews/questions` - Get interview questions
- `POST /api/interviews/assess` - Submit interview responses
- `GET /api/interviews/analytics` - Get performance analytics

### Industry Insights
- `GET /api/industries` - List all industries
- `GET /api/industries/[slug]` - Get industry details
- `GET /api/salary-data` - Get salary information

## 📁 Project Structure

```
ai-career-coach/
├── app/                    # Next.js App Router
│   ├── (auth)/            # Authentication routes
│   │   ├── sign-in/
│   │   └── sign-up/
│   ├── (main)/            # Main application routes
│   │   ├── dashboard/
│   │   ├── resume/
│   │   ├── ai-cover-letter/
│   │   ├── interview/
│   │   └── onboarding/
│   ├── api/               # API routes
│   │   └── inngest/
│   ├── globals.css        # Global styles
│   ├── layout.js          # Root layout
│   └── page.js            # Landing page
├── components/            # Reusable components
│   ├── ui/               # Shadcn UI components
│   ├── header.jsx
│   ├── hero.jsx
│   └── theme-provider.jsx
├── actions/              # Server actions
│   ├── cover-letter.js
│   ├── dashboard.js
│   ├── interview.js
│   ├── resume.js
│   └── user.js
├── data/                 # Static data
│   ├── faqs.js
│   ├── features.js
│   ├── industries.js
│   └── testimonial.js
├── hooks/                # Custom React hooks
│   └── use-fetch.js
├── lib/                  # Utility libraries
│   ├── inngest/
│   ├── checkUser.js
│   ├── prisma.js
│   └── utils.js
├── prisma/               # Database schema and migrations
│   ├── migrations/
│   └── schema.prisma
├── public/               # Static assets
└── package.json
```

## 🤝 Contributing

We welcome contributions to the AI Career Coach project! Here's how you can help:

### Development Workflow

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Test your changes**
   ```bash
   npm run test
   npm run lint
   ```
5. **Commit your changes**
   ```bash
   git commit -m "Add amazing feature"
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
7. **Open a Pull Request**

### Code Style Guidelines

- Use **TypeScript** for type safety
- Follow **ESLint** configuration
- Use **Prettier** for code formatting
- Write **meaningful commit messages**
- Add **tests** for new features
- Update **documentation** as needed

### Reporting Issues

If you find a bug or have a feature request:
1. Check existing issues first
2. Create a detailed issue with reproduction steps
3. Include screenshots or error messages
4. Specify your environment (OS, browser, Node.js version)

## 🚀 Deployment

### Vercel (Recommended)

1. **Connect your repository to Vercel**
2. **Add environment variables in Vercel dashboard**
3. **Deploy with zero configuration**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/your-username/ai-career-coach)

### Manual Deployment

1. **Build the application**
   ```bash
   npm run build
   ```

2. **Set up production database**
3. **Configure environment variables**
4. **Deploy to your hosting platform**

### Environment Variables for Production

Ensure all environment variables are set in your production environment:
- Database URL (production)
- Clerk keys (production)
- Gemini API key
- Inngest keys (if using background jobs)

## 📊 Performance & Monitoring

- **Core Web Vitals**: Optimized for perfect Lighthouse scores
- **Image Optimization**: Next.js Image component for optimal loading
- **Bundle Analysis**: Use `@next/bundle-analyzer` for optimization
- **Error Tracking**: Integration ready for Sentry or similar tools
- **Analytics**: Built-in support for analytics platforms

## 🔧 Troubleshooting

### Common Issues

**Database Connection Issues**
```bash
# Reset the database
npx prisma migrate reset
npx prisma generate
```

**Authentication Problems**
- Verify Clerk configuration
- Check environment variables
- Ensure redirect URLs are correct

**AI API Issues**
- Verify Gemini API key
- Check API quotas and limits
- Review error logs

### Getting Help

- 📖 [Documentation](https://github.com/x0lg0n/ai-career-coach/wiki)
- 💬 [Discussions](https://github.com/x0lg0n/ai-career-coach/discussions)
- 🐛 [Issues](https://github.com/x0lg0n/ai-career-coach/issues)
- 📧 [Email Support](mailto:support@aicarriercoach.com)

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Siddhartha** - *Full Stack Developer*
- GitHub: [@x0lg0n](https://github.com/x0lg0n)
- LinkedIn: [Siddhartha Kunwar](https://linkedin.com/in/siddhartha-kunwar)
- Twitter: [@Siddhar08958424](https://twitter.com/Siddhar08958424)

## 🙏 Acknowledgments

- **Next.js Team** for the amazing framework
- **Vercel** for seamless deployment
- **Clerk** for authentication solutions
- **Google** for Gemini AI capabilities
- **Neon** for serverless PostgreSQL
- **Shadcn** for beautiful UI components
- **Open Source Community** for inspiration and support

---

<div align="center">
  <p>Made with ❤️ by <strong>Siddhartha</strong></p>
  <p>⭐ Star this repo if you find it helpful!</p>
</div>
