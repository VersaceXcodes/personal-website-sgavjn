# Personal Website

This is a personal website project with a React frontend and Node.js backend.

## Local Development

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Setup and Running Locally

1. Install dependencies:
   ```
   npm install
   ```

2. Start the development server:
   ```
   npm run dev
   ```
   This will start both the frontend and backend in development mode.

## Deployment

This project is configured to deploy to [Fly.io](https://fly.io) using GitHub Actions.

### First-time Deployment Setup

1. Create a Fly.io account if you don't have one: https://fly.io/signup

2. Install the Fly.io CLI:
   ```
   # On macOS:
   brew install flyctl
   
   # On Linux:
   curl -L https://fly.io/install.sh | sh
   
   # On Windows (using PowerShell):
   iwr https://fly.io/install.ps1 -useb | iex
   ```

3. Login to Fly.io:
   ```
   flyctl auth login
   ```

4. Create a new app on Fly.io (if you haven't already):
   ```
   flyctl apps create your-app-name
   ```

5. Set up GitHub repository secrets:
   - Go to your GitHub repository > Settings > Secrets > Actions
   - Click "New repository secret"
   - Add a secret with name `FLY_API_TOKEN` and value from running:
     ```
     flyctl auth token
     ```

### Deployment Process

Once the FLY_API_TOKEN secret is set up in your GitHub repository, every push to the main branch will automatically trigger a deployment through GitHub Actions.

To manually deploy:
```
flyctl deploy
```

## Project Structure

- `/vitereact` - Frontend React application
- `/backend` - Node.js backend API
- `Dockerfile` - Container configuration for deployment
- `fly.toml` - Fly.io deployment configuration