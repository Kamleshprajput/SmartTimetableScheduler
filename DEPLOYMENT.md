# Vercel Deployment Guide

This project is configured for separate Vercel deployments of the frontend and backend.

## Project Structure

```
SIHproject/
├── newer/          # Frontend (React + Vite)
├── backend/        # Backend (Node.js + Express)
└── DEPLOYMENT.md   # This file
```

## Frontend Deployment (newer/)

### Prerequisites
- Vercel account
- Node.js installed locally
- Git repository

### Steps to Deploy Frontend

1. **Navigate to the frontend directory:**
   ```bash
   cd newer
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Test the build locally:**
   ```bash
   npm run build
   ```

4. **Deploy to Vercel:**
   
   **Option A: Using Vercel CLI**
   ```bash
   # Install Vercel CLI globally
   npm i -g vercel
   
   # Login to Vercel
   vercel login
   
   # Deploy
   vercel --prod
   ```
   
   **Option B: Using Vercel Dashboard**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your Git repository
   - Set Root Directory to `newer`
   - Deploy

### Frontend Configuration Files
- `vercel.json` - Vercel deployment configuration
- `.vercelignore` - Files to ignore during deployment
- `package.json` - Updated with build scripts

## Backend Deployment (backend/)

### Prerequisites
- Vercel account
- Node.js installed locally
- Python installed locally (for solver.py)

### Steps to Deploy Backend

1. **Navigate to the backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Test the server locally:**
   ```bash
   npm start
   ```

4. **Deploy to Vercel:**
   
   **Option A: Using Vercel CLI**
   ```bash
   # Install Vercel CLI globally
   npm i -g vercel
   
   # Login to Vercel
   vercel login
   
   # Deploy
   vercel --prod
   ```
   
   **Option B: Using Vercel Dashboard**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your Git repository
   - Set Root Directory to `backend`
   - Deploy

### Backend Configuration Files
- `vercel.json` - Vercel deployment configuration
- `.vercelignore` - Files to ignore during deployment
- `package.json` - Updated with build scripts

## Environment Variables

### Frontend Environment Variables
No environment variables required for basic deployment.

### Backend Environment Variables
- `NODE_ENV=production` (automatically set by Vercel)

## API Endpoints

After backend deployment, your API will be available at:
- `https://your-backend-domain.vercel.app/generate` - Timetable generation
- `https://your-backend-domain.vercel.app/health` - Health check
- `https://your-backend-domain.vercel.app/api/*` - API routes

## Connecting Frontend to Backend

Update your frontend code to use the deployed backend URL:

```javascript
// In your frontend code, replace localhost with your Vercel backend URL
const API_BASE_URL = 'https://your-backend-domain.vercel.app';

// Example API call
fetch(`${API_BASE_URL}/generate`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(data)
});
```

## Troubleshooting

### Frontend Issues
- Ensure `npm run build` works locally before deploying
- Check that all dependencies are in `package.json`
- Verify `vercel.json` configuration

### Backend Issues
- Ensure `npm start` works locally before deploying
- Check that Python dependencies are available for `solver.py`
- Verify API routes in `vercel.json`

### Common Solutions
1. **Build failures**: Check Node.js version compatibility
2. **API not working**: Verify CORS settings and endpoint URLs
3. **Python solver issues**: Ensure Python runtime is available in Vercel

## Deployment URLs

After successful deployment:
- Frontend: `https://your-frontend-project.vercel.app`
- Backend: `https://your-backend-project.vercel.app`

## Next Steps

1. Deploy both frontend and backend separately
2. Update frontend to use backend URL
3. Test the complete application
4. Set up custom domains if needed
5. Configure environment variables for production

## Support

For Vercel-specific issues:
- [Vercel Documentation](https://vercel.com/docs)
- [Vercel Community](https://github.com/vercel/vercel/discussions)
