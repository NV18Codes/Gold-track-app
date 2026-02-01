# Netlify Deployment Guide

This guide will help you deploy the Digital Gold Rate Monitor application to Netlify.

## Prerequisites

1. A [Netlify account](https://app.netlify.com/signup) (free tier is sufficient)
2. A [GitHub account](https://github.com/signup) (optional, but recommended)
3. Your Supabase project credentials

## Deployment Steps

### Option 1: Deploy via Git (Recommended)

1. **Push your code to GitHub**
   ```bash
   git add .
   git commit -m "Prepare for Netlify deployment"
   git push origin main
   ```

2. **Connect to Netlify**
   - Go to [Netlify](https://app.netlify.com)
   - Click "Add new site" > "Import an existing project"
   - Choose "Deploy with GitHub"
   - Authorize Netlify to access your GitHub repositories
   - Select your repository

3. **Configure Build Settings**
   - Netlify should auto-detect the settings from `netlify.toml`
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Click "Deploy site"

4. **Add Environment Variables**
   - Go to Site settings > Environment variables
   - Add the following variables:
     ```
     VITE_SUPABASE_URL=https://hdpyzfejijcknwrtlacc.supabase.co
     VITE_SUPABASE_PUBLISHABLE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImhkcHl6ZmVqaWpja253cnRsYWNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3Njk2NjU5ODgsImV4cCI6MjA4NTI0MTk4OH0.i6Jh6rncwMn4cvYt5sYTy77y4uyYf7WwRmGCmPVuDfE
     VITE_SUPABASE_PROJECT_ID=hdpyzfejijcknwrtlacc
     ```
   - Click "Save"

5. **Trigger Redeploy**
   - Go to Deploys tab
   - Click "Trigger deploy" > "Deploy site"

### Option 2: Deploy via Netlify CLI

1. **Install Netlify CLI**
   ```bash
   npm install -g netlify-cli
   ```

2. **Login to Netlify**
   ```bash
   netlify login
   ```

3. **Initialize the site**
   ```bash
   netlify init
   ```
   - Choose "Create & configure a new site"
   - Select your team
   - Enter a site name (or leave blank for auto-generated)

4. **Deploy**
   ```bash
   netlify deploy --prod
   ```

### Option 3: Drag and Drop (Quick Test)

1. **Build the project locally**
   ```bash
   npm run build
   ```

2. **Deploy to Netlify**
   - Go to [Netlify](https://app.netlify.com)
   - Drag and drop the `dist` folder to the deploy area

3. **Add Environment Variables**
   - Follow step 4 from Option 1 above

## Post-Deployment

### Update Supabase URL Redirect

1. Go to your [Supabase Dashboard](https://supabase.com/dashboard)
2. Navigate to Authentication > URL Configuration
3. Add your Netlify URL to "Site URL" and "Redirect URLs":
   ```
   https://your-site-name.netlify.app
   ```

### Custom Domain (Optional)

1. Go to Site settings > Domain management
2. Click "Add custom domain"
3. Follow the instructions to configure your DNS

### Enable HTTPS

- HTTPS is automatically enabled by Netlify
- Your site will be available at `https://your-site-name.netlify.app`

## Continuous Deployment

Once connected via Git (Option 1), Netlify will automatically:
- Build and deploy when you push to the main branch
- Create preview deployments for pull requests
- Roll back to previous deployments if needed

## Troubleshooting

### Build Fails
- Check the deploy logs in Netlify dashboard
- Ensure all environment variables are set correctly
- Verify Node version matches (should be 18+)

### Blank Page After Deployment
- Check browser console for errors
- Verify environment variables are set
- Ensure `_redirects` file exists in the `public` folder

### Authentication Not Working
- Verify Supabase URL is added to redirect URLs
- Check that environment variables match your Supabase project

## Environment Variables Reference

| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_SUPABASE_URL` | Your Supabase project URL | `https://xxx.supabase.co` |
| `VITE_SUPABASE_PUBLISHABLE_KEY` | Supabase anonymous/public key | `eyJhbGc...` |
| `VITE_SUPABASE_PROJECT_ID` | Your Supabase project ID | `hdpyzfejijcknwrtlacc` |

## Support

For more help:
- [Netlify Documentation](https://docs.netlify.com/)
- [Vite Deployment Guide](https://vitejs.dev/guide/static-deploy.html)
- [Supabase Documentation](https://supabase.com/docs)
