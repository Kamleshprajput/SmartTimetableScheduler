# AI-Powered Timetable Manager - Backend

This is the backend API for the AI-Powered Timetable Manager, built with Node.js, Express, and Python.

## Features

- RESTful API with Express.js
- CORS enabled for cross-origin requests
- Python CP-SAT solver integration
- Health check endpoint
- Fallback mock data generation
- Static file serving for embed functionality

## Quick Start

### Prerequisites
- Node.js 18+
- Python 3.8+
- npm or yarn

### Installation

```bash
# Install Node.js dependencies
npm install

# Install Python dependencies (if needed)
pip install ortools
```

### Development

```bash
# Start development server with nodemon
npm run dev

# Start production server
npm start
```

The server runs on `http://localhost:8001` by default.

## API Endpoints

### POST /generate
Generate a timetable based on input data.

**Request Body:**
```json
{
  "college": "Example College",
  "degree": "B.Tech",
  "branches": ["CSE", "ECE"],
  "years": [1, 2, 3, 4],
  "courses": ["Data Structures", "Algorithms"],
  "batches": 2,
  "labs": ["Programming Lab"],
  "teachers": [
    {"name": "Dr. Smith", "department": "CSE"}
  ]
}
```

**Response:**
```json
{
  "success": true,
  "message": "Timetable generated successfully",
  "timetable": { /* timetable data */ },
  "metadata": {
    "totalSlots": 48,
    "conflicts": 0,
    "utilization": 85,
    "solverStatus": "optimal"
  }
}
```

### GET /health
Health check endpoint.

**Response:**
```json
{
  "status": "healthy",
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

### GET /embed
Serve the embed page for timetable display.

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
backend/
├── server.js           # Main Express server
├── solver.py          # Python CP-SAT solver
├── package.json       # Node.js dependencies
├── vercel.json        # Vercel deployment config
└── README.md          # This file
```

## Technologies Used

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **CORS** - Cross-origin resource sharing
- **Python** - Solver implementation
- **OR-Tools** - Constraint programming solver

## Configuration Files

- `package.json` - Node.js dependencies and scripts
- `vercel.json` - Vercel deployment configuration
- `server.js` - Main application file
- `solver.py` - Python constraint solver

## Environment Variables

- `PORT` - Server port (default: 8001)
- `NODE_ENV` - Environment (development/production)

## Error Handling

The API includes comprehensive error handling:
- Python solver failures fall back to mock data
- JSON parsing errors are caught and handled
- CORS is properly configured for cross-origin requests

## Development Notes

- The server serves static files from the frontend build directory
- Python solver integration uses child processes
- Mock data generation provides fallback functionality
- Health check endpoint for monitoring
