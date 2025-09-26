# AI-Powered Timetable Manager - Frontend

This is the frontend application for the AI-Powered Timetable Manager, built with React, TypeScript, and Vite.

## Features

- Modern React 18 with TypeScript
- Vite for fast development and building
- Tailwind CSS for styling
- Radix UI components for accessibility
- Framer Motion for animations
- Responsive design

## Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Development

The development server runs on `http://localhost:3000` by default.

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

## Deployment

This project is configured for Vercel deployment. See the main `DEPLOYMENT.md` file for detailed instructions.

### Quick Vercel Deployment

```bash
# Install Vercel CLI
npm i -g vercel

# Login to Vercel
vercel login

# Deploy
vercel --prod
```

## Project Structure

```
src/
├── components/          # React components
│   ├── ui/             # Reusable UI components
│   └── ...             # Feature components
├── assets/             # Static assets
├── styles/             # Global styles
└── main.tsx            # Application entry point
```

## Technologies Used

- **React 18** - UI framework
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Radix UI** - Accessible component primitives
- **Framer Motion** - Animation library
- **Lucide React** - Icon library

## Configuration Files

- `vite.config.ts` - Vite configuration
- `vercel.json` - Vercel deployment configuration
- `package.json` - Dependencies and scripts
- `tailwind.config.js` - Tailwind CSS configuration
- `tsconfig.json` - TypeScript configuration